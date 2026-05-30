# Appium(Selenium)-Mobile Automation Testing from Scratch

**Written by Brian McCarthy**

This is the code repository for Appium(Selenium)-Mobile Automation Testing from Scratch. It contains all the supporting project files necessary to work through the video course from start to finish.

## About the Course

Learn everything you need to know about Mobile Automation (Android + iOS) even if you've never programmed before! This course teaches the concepts from scratch, assuming students are new to automation testing.

---

## Table of Contents

- [Languages Used](#languages-used)
- [Methodologies Used](#methodologies-used)
- [File Structure](#file-structure)
- [Core Functions & Methods](#core-functions--methods)
- [Key Features](#key-features)
- [Getting Started](#getting-started)
- [Code Methodologies with Examples](#code-methodologies-with-examples)
- [REST API Automation Guide](#rest-api-automation-guide)
- [Installation & Setup](#installation--setup)
- [Tutorials & Tips](#tutorials--tips)
- [Related Resources](#related-resources)

---

## Languages Used

- **Java** - Primary language for test automation scripts
- **XML** - Configuration files and test data management
- **JSON** - REST API requests and responses handling
- **Markdown** - Documentation

---

## Methodologies Used

### 1. **Page Object Model (POM)**
Organizes test code by separating page elements and business logic from test cases, improving maintainability.

### 2. **Test-Driven Development (TDD)**
Write test cases before implementing features to ensure code quality.

### 3. **BDD (Behavior-Driven Development)**
Uses human-readable test scenarios to bridge communication between technical and non-technical stakeholders.

### 4. **Data-Driven Testing**
Parameterize tests with multiple data sets to increase test coverage with minimal code duplication.

### 5. **Continuous Integration/Continuous Deployment (CI/CD)**
Automated testing pipeline for rapid feedback on code quality.

### 6. **Keyword-Driven Testing**
Use keywords/tags to define test actions independently from automation code.

### 7. **API Testing**
REST and SOAP API testing with request/response validation.

---

## File Structure

```
Appium-Selenium-Mobile-Automation/
│
├── README.md                          # Project documentation
│
├── Section 1 Resources/               # Appium fundamentals & architecture
│   ├── 1.2 Why-Appium.docx
│   └── 1.3 Architecture.png
│
├── Section 3 - Resources/             # Selenium WebDriver basics
│
├── Section 5 Resources/               # Test frameworks & setup
│
├── Section 6 Resources/               # Locators & element identification
│
├── Section 8 Resources/               # Mobile gestures & interactions
│
├── Section 9 Resources/               # Advanced test scenarios
│
├── Section 10 Resources/              # iOS automation specifics
│
├── Section 12 Resources/              # Android automation specifics
│
├── Section 14 Resources/              # Page Object Model implementation
│
├── Section 15 Resources/              # Data-driven testing
│
├── Section 20 Resources/              # API testing & REST automation
│
└── Section 24 Resources/              # CI/CD integration & reporting
```

---

## Core Functions & Methods

### Common Test Automation Functions

| Function | Description | Example Usage |
|----------|-------------|---------------|
| `findElement()` | Locates UI elements on mobile screen | `driver.findElement(By.id("elementId"))` |
| `click()` | Performs click action on elements | `element.click()` |
| `sendKeys()` | Enters text into input fields | `element.sendKeys("test@example.com")` |
| `tap()` | Mobile-specific tap gesture | `driver.tap(1, x, y, 1)` |
| `swipe()` | Swipe gesture for mobile navigation | `driver.swipe(startX, startY, endX, endY, duration)` |
| `waitFor()` | Explicit waits for elements | `WebDriverWait(driver, 10).until(presence_of_element)` |
| `assertEquals()` | Assertion for validation | `Assert.assertEquals(expected, actual)` |
| `captureScreenshot()` | Screenshot capture for reporting | `((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE)` |

---

## Key Features

- ✅ Mobile automation for Android and iOS platforms
- ✅ Appium and Selenium WebDriver integration
- ✅ Page Object Model design pattern
- ✅ Data-driven test execution
- ✅ API automation for REST services
- ✅ CI/CD pipeline integration
- ✅ Comprehensive reporting and logging
- ✅ Gesture and touch action automation
- ✅ Cross-platform testing capabilities

---

## Code Methodologies with Examples

### 1. Page Object Model (POM) Pattern

**Purpose:** Encapsulate page elements and interactions in separate classes for better maintainability.

**Sample Code Structure:**
```java
// LoginPage.java - Page Object Class
public class LoginPage {
    private WebDriver driver;
    
    // Locators
    private By usernameField = By.id("username");
    private By passwordField = By.id("password");
    private By loginButton = By.xpath("//button[@text='Login']");
    
    // Constructor
    public LoginPage(WebDriver driver) {
        this.driver = driver;
    }
    
    // Page Methods
    public void enterUsername(String username) {
        driver.findElement(usernameField).sendKeys(username);
    }
    
    public void enterPassword(String password) {
        driver.findElement(passwordField).sendKeys(password);
    }
    
    public void clickLogin() {
        driver.findElement(loginButton).click();
    }
    
    public void login(String username, String password) {
        enterUsername(username);
        enterPassword(password);
        clickLogin();
    }
}

// LoginTest.java - Test Case using POM
@Test
public void testValidLogin() {
    LoginPage loginPage = new LoginPage(driver);
    loginPage.login("user@example.com", "password123");
    Assert.assertTrue(driver.findElement(By.id("dashboard")).isDisplayed());
}
```

**Benefits:**
- Reduces code duplication
- Easy to maintain and update
- Improves readability and scalability

---

### 2. Data-Driven Testing

**Purpose:** Run same test with multiple data sets to maximize test coverage.

**Sample Code:**
```java
// Test Data Provider
@DataProvider(name = "loginData")
public Object[][] provideLoginData() {
    return new Object[][] {
        {"user1@test.com", "password123", true},
        {"user2@test.com", "password456", true},
        {"invalid@test.com", "wrongpass", false},
        {"", "", false}
    };
}

// Parameterized Test
@Test(dataProvider = "loginData")
public void testLoginWithMultipleData(String email, String password, boolean shouldSucceed) {
    LoginPage loginPage = new LoginPage(driver);
    loginPage.login(email, password);
    
    if (shouldSucceed) {
        Assert.assertTrue(driver.findElement(By.id("dashboard")).isDisplayed());
    } else {
        Assert.assertTrue(driver.findElement(By.id("errorMessage")).isDisplayed());
    }
}
```

**Benefits:**
- Single test executes with multiple data sets
- Reduces code duplication
- Improves test coverage efficiency

---

### 3. Explicit Waits (Element Synchronization)

**Purpose:** Wait for specific conditions before proceeding to avoid flaky tests.

**Sample Code:**
```java
// Wait for element to be visible
WebDriverWait wait = new WebDriverWait(driver, 10);
WebElement element = wait.until(ExpectedConditions.visibilityOfElementLocated(By.id("confirmButton")));
element.click();

// Wait for element to be clickable
wait.until(ExpectedConditions.elementToBeClickable(By.id("submitBtn"))).click();

// Custom wait condition
wait.until(driver -> {
    WebElement statusElement = driver.findElement(By.id("status"));
    return statusElement.getText().contains("Success");
});
```

**Benefits:**
- Handles dynamic content loading
- Reduces flaky tests
- Better test reliability

---

### 4. Mobile Gesture Automation

**Purpose:** Automate touch gestures specific to mobile devices.

**Sample Code:**
```java
import io.appium.java_client.TouchAction;
import io.appium.java_client.touch.offset.PointOption;

// Tap Action
TouchAction action = new TouchAction(driver);
action.tap(PointOption.point(100, 200)).perform();

// Swipe Action
action.press(PointOption.point(50, 500))
      .waitAction()
      .moveTo(PointOption.point(50, 100))
      .release()
      .perform();

// Long Press
action.longPress(PointOption.point(100, 200))
      .waitAction()
      .release()
      .perform();

// Multi-touch (Pinch to Zoom)
TouchAction touch1 = new TouchAction(driver);
TouchAction touch2 = new TouchAction(driver);

touch1.press(PointOption.point(100, 100))
      .waitAction()
      .moveTo(PointOption.point(50, 50))
      .release();

touch2.press(PointOption.point(300, 300))
      .waitAction()
      .moveTo(PointOption.point(350, 350))
      .release();

MultiTouchAction multiTouch = new MultiTouchAction(driver);
multiTouch.add(touch1).add(touch2).perform();
```

---

### 5. Test Reporting & Logging

**Purpose:** Generate comprehensive test reports and logs for analysis.

**Sample Code:**
```java
import org.apache.log4j.Logger;

public class TestBase {
    protected static Logger logger = Logger.getLogger(TestBase.class);
    
    @Before
    public void setUp() {
        logger.info("Test execution started");
        initializeDriver();
    }
    
    @After
    public void tearDown() {
        logger.info("Test execution completed");
        captureScreenshot();
        driver.quit();
    }
    
    public void captureScreenshot() {
        try {
            File screenshot = ((TakesScreenshot)driver).getScreenshotAs(OutputType.FILE);
            FileUtils.copyFile(screenshot, new File("screenshots/" + System.currentTimeMillis() + ".png"));
            logger.info("Screenshot captured");
        } catch (IOException e) {
            logger.error("Failed to capture screenshot: " + e.getMessage());
        }
    }
}
```

---

## How Everything Works

### Test Execution Flow

```
1. Setup Phase
   ├─ Initialize driver (Appium/Selenium)
   ├─ Load configuration files
   └─ Connect to mobile device

2. Test Execution
   ├─ Locate UI elements
   ├─ Perform interactions (click, type, swipe)
   ├─ Validate results with assertions
   └─ Capture screenshots on failure

3. Reporting
   ├─ Generate test reports (HTML, XML)
   ├─ Log results
   └─ Attach screenshots/videos

4. Teardown Phase
   ├─ Close applications
   ├─ Disconnect from device
   └─ Clean up resources
```

---

## REST API Automation Guide

### Overview

REST API automation tests validate web services endpoints without UI interaction. This guide covers common API testing scenarios.

### 1. Basic API Request & Response Validation

**Purpose:** Test GET endpoints and validate response data.

**Tools:** RestAssured library for Java

**Setup:**
```xml
<!-- pom.xml -->
<dependency>
    <groupId>io.rest-assured</groupId>
    <artifactId>rest-assured</artifactId>
    <version>5.3.1</version>
</dependency>
```

**Sample Code:**
```java
import static io.restassured.RestAssured.*;
import static org.hamcrest.Matchers.*;

@Test
public void testGetUserById() {
    given()
        .baseUri("https://api.example.com")
        .basePath("/users")
        .queryParam("id", "123")
    .when()
        .get()
    .then()
        .statusCode(200)
        .body("id", equalTo(123))
        .body("name", notNullValue())
        .body("email", matchesPattern("^[A-Za-z0-9+_.-]+@(.+)$"));
}
```

---

### 2. POST Request with Request Body

**Purpose:** Create resources via API and validate creation.

**Sample Code:**
```java
@Test
public void testCreateNewUser() {
    String requestBody = "{\n" +
        "  \"name\": \"John Doe\",\n" +
        "  \"email\": \"john@example.com\",\n" +
        "  \"age\": 30\n" +
        "}";
    
    given()
        .baseUri("https://api.example.com")
        .contentType(ContentType.JSON)
        .body(requestBody)
    .when()
        .post("/users")
    .then()
        .statusCode(201)
        .body("id", notNullValue())
        .body("name", equalTo("John Doe"))
        .extract()
        .response();
}
```

---

### 3. Authentication in API Tests

**Purpose:** Handle various authentication mechanisms (Bearer, Basic, API Key).

**Sample Code:**
```java
@Test
public void testWithBearerToken() {
    String token = "your_bearer_token_here";
    
    given()
        .baseUri("https://api.example.com")
        .header("Authorization", "Bearer " + token)
    .when()
        .get("/protected-endpoint")
    .then()
        .statusCode(200);
}

@Test
public void testWithBasicAuth() {
    given()
        .baseUri("https://api.example.com")
        .auth().basic("username", "password")
    .when()
        .get("/users")
    .then()
        .statusCode(200);
}

@Test
public void testWithAPIKey() {
    given()
        .baseUri("https://api.example.com")
        .queryParam("apiKey", "your_api_key_here")
    .when()
        .get("/data")
    .then()
        .statusCode(200);
}
```

---

### 4. JSON Path Extraction & Assertion

**Purpose:** Extract specific values from API responses for validation or use in subsequent requests.

**Sample Code:**
```java
@Test
public void testExtractAndAssertJSON() {
    Response response = given()
        .baseUri("https://api.example.com")
    .when()
        .get("/users/123");
    
    // Extract values
    String userName = response.jsonPath().getString("name");
    int userId = response.jsonPath().getInt("id");
    List<String> emailList = response.jsonPath().getList("emails");
    
    // Assertions
    Assert.assertEquals("John Doe", userName);
    Assert.assertEquals(123, userId);
    Assert.assertTrue(emailList.contains("john@example.com"));
}
```

---

### 5. Testing API Error Scenarios

**Purpose:** Validate proper error handling and status codes.

**Sample Code:**
```java
@Test
public void testInvalidUserIdReturns404() {
    given()
        .baseUri("https://api.example.com")
    .when()
        .get("/users/99999")
    .then()
        .statusCode(404)
        .body("error", equalTo("User not found"));
}

@Test
public void testMissingAuthenticationReturns401() {
    given()
        .baseUri("https://api.example.com")
    .when()
        .get("/protected-data")
    .then()
        .statusCode(401)
        .body("message", containsString("Unauthorized"));
}

@Test
public void testInvalidPayloadReturns400() {
    String invalidBody = "{\"name\": \"\"}"; // Empty name
    
    given()
        .baseUri("https://api.example.com")
        .contentType(ContentType.JSON)
        .body(invalidBody)
    .when()
        .post("/users")
    .then()
        .statusCode(400)
        .body("errors", hasItem("Name is required"));
}
```

---

### 6. API Chain Testing (Sequential Requests)

**Purpose:** Execute multiple API calls in sequence, using response data from one request in the next.

**Sample Code:**
```java
@Test
public void testCreateUserThenFetchUser() {
    // Create user
    String createResponse = given()
        .baseUri("https://api.example.com")
        .contentType(ContentType.JSON)
        .body("{\"name\": \"Jane Doe\", \"email\": \"jane@example.com\"}")
    .when()
        .post("/users")
    .then()
        .statusCode(201)
        .extract()
        .asString();
    
    // Extract user ID from create response
    int userId = JsonPath.from(createResponse).getInt("id");
    
    // Fetch the created user
    given()
        .baseUri("https://api.example.com")
    .when()
        .get("/users/" + userId)
    .then()
        .statusCode(200)
        .body("name", equalTo("Jane Doe"));
}
```

---

### 7. API Performance Testing

**Purpose:** Measure API response times and ensure performance requirements.

**Sample Code:**
```java
@Test
public void testAPIResponseTime() {
    long startTime = System.currentTimeMillis();
    
    given()
        .baseUri("https://api.example.com")
    .when()
        .get("/users/123")
    .then()
        .statusCode(200)
        .time(lessThan(2000L)); // Response time < 2 seconds
    
    long endTime = System.currentTimeMillis();
    long responseTime = endTime - startTime;
    System.out.println("API Response Time: " + responseTime + "ms");
}
```

---

### 8. API Testing Best Practices

| Practice | Description |
|----------|-------------|
| **Use Base URLs** | Define base URIs in configuration for easy maintenance |
| **Parameterize Data** | Use data providers for multiple test scenarios |
| **Validate Status Codes** | Always verify HTTP status codes (200, 201, 400, 401, 404, 500) |
| **Check Content Type** | Ensure responses have correct content-type headers |
| **Validate Response Schema** | Use JSON Schema validation for response structure |
| **Handle Timeouts** | Set appropriate timeout values for network requests |
| **Log Requests/Responses** | Enable detailed logging for debugging |
| **Test Error Cases** | Include negative test cases for error scenarios |

---

## Installation & Setup

### Prerequisites
- Java JDK 8 or higher
- Android SDK (for Android testing)
- Xcode (for iOS testing on Mac)
- Appium Server
- Maven or Gradle

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/BrianGator/Appium-Selenium-Mobile-Automation.git
   cd Appium-Selenium-Mobile-Automation
   ```

2. **Install dependencies**
   ```bash
   mvn install
   ```

3. **Configure Appium capabilities** in your test configuration file:
   ```java
   DesiredCapabilities caps = new DesiredCapabilities();
   caps.setCapability("platformName", "Android");
   caps.setCapability("deviceName", "emulator-5554");
   caps.setCapability("app", "/path/to/app.apk");
   
   AppiumDriver driver = new AndroidDriver(new URL("http://127.0.0.1:4723"), caps);
   ```

4. **Run tests**
   ```bash
   mvn test
   ```

---

## Tutorials & Tips

### Tip 1: Handle Dynamic Elements
```java
// Retry mechanism for flaky elements
public WebElement findElementWithRetry(By locator, int maxRetries) {
    int retries = 0;
    while (retries < maxRetries) {
        try {
            return driver.findElement(locator);
        } catch (NoSuchElementException e) {
            retries++;
            if (retries == maxRetries) throw e;
            try { Thread.sleep(500); } catch (InterruptedException ie) {}
        }
    }
    return null;
}
```

### Tip 2: Mobile-Specific Waits
```java
// Wait for app to settle on Android
driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));

// Wait for specific text on screen
wait.until(ExpectedConditions.textToBePresentInElement(By.id("status"), "Ready"));
```

### Tip 3: Cross-Platform Test Design
```java
// Abstract platform differences
public abstract class BasePage {
    protected WebDriver driver;
    
    protected By getLocator(String ios, String android) {
        if (isPlatform("iOS")) {
            return By.xpath(ios);
        } else {
            return By.xpath(android);
        }
    }
}
```

### Tip 4: Effective Logging
```java
logger.info("Starting login test");
logger.debug("Entering username: " + username);
logger.warn("Element not immediately visible, using explicit wait");
logger.error("Test failed: " + exception.getMessage());
```

### Tip 5: Screenshot on Failure
```java
@After
public void tearDown() {
    if (testResult.getStatus() == ITestResult.FAILURE) {
        captureScreenshot("failure_" + testResult.getName());
    }
}
```

---

## What You Will Learn

- ✅ Deploy powerful automation solutions for mobile applications (Android & iOS)
- ✅ Design efficient and scalable test frameworks using Page Object Model
- ✅ Implement data-driven testing for comprehensive coverage
- ✅ Master Appium and Selenium WebDriver fundamentals
- ✅ Automate mobile gestures and touch interactions
- ✅ Test REST APIs and validate web services
- ✅ Integrate tests with CI/CD pipelines
- ✅ Create robust, maintainable, and reusable test code
- ✅ Generate comprehensive test reports and logs
- ✅ Handle advanced scenarios like authentication and error handling

---

## Assumed Knowledge

This course is for:
- Manual testers interested in learning automation
- Non-programming testers who want to get started
- Web automation testers familiar with Selenium WebDriver
- Software engineers looking to add mobile testing skills
- QA professionals wanting to advance their career

**Note:** No prior programming experience required! The course teaches concepts from scratch.

---

## Related Products

- [Building Microservices from Scratch [Video]](https://www.packtpub.com/)
- [Mobile App Testing Fundamentals [Video]](https://www.packtpub.com/)
- [Test Automation with Java [Video]](https://www.packtpub.com/)

---

## Additional Resources

- [Appium Official Documentation](http://appium.io/)
- [Selenium WebDriver Documentation](https://www.selenium.dev/documentation/)
- [RestAssured Documentation](https://rest-assured.io/)
- [TestNG Framework](https://testng.org/)
- [Maven Repository](https://mvnrepository.com/)

---

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## Contact & Support

For questions, issues, or contributions, please reach out to:

**Brian McCarthy**

- GitHub: [@BrianGator](https://github.com/BrianGator)
- Repository: [Appium-Selenium-Mobile-Automation](https://github.com/BrianGator/Appium-Selenium-Mobile-Automation)

---

**Last Updated:** May 30, 2026

**Happy Testing! 🚀**
