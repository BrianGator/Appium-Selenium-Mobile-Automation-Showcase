# Appium Selenium Mobile Automation Showcase

**Written by Brian McCarthy**

This repository is a complete Appium and Selenium mobile automation guide covering Android, iOS, native apps, hybrid apps, mobile web, TestNG, Maven, Jenkins, Page Object Model, reporting, cloud execution, database integration, login testing, API testing, and interview preparation.

The README consolidates the uploaded module lists into one non-duplicated learning path. Similar topics from the course outlines were merged into single modules so the table of contents stays clean while still covering every major topic.

---

## Table of Contents

| # | Module | What This Module Covers |
|---:|---|---|
| 1 | [Course Overview and Appium Basics](#1-course-overview-and-appium-basics) | Appium purpose, Appium vs Selendroid, architecture, supported app types, Selenium relationship, and course agenda. |
| 2 | [Installation and Environment Setup](#2-installation-and-environment-setup) | Java, Android Studio, Node.js, Appium Server, Appium Inspector, Eclipse/IDE setup, environment variables, Android SDK paths, Windows/Mac setup, APK installation, and emulator setup. |
| 3 | [Launching Appium Sessions and Desired Capabilities](#3-launching-appium-sessions-and-desired-capabilities) | App package/activity, platform settings, device settings, app path, AndroidDriver initialization, native/web/hybrid context basics, and first Appium program. |
| 4 | [Inspecting Mobile Elements and Locator Strategy](#4-inspecting-mobile-elements-and-locator-strategy) | UIAutomatorViewer, Appium Inspector, IDs, resource IDs, class names, XPath, text attributes, Android UiSelector, nested elements, multiple elements, and locator best practices. |
| 5 | [Native Android App Automation](#5-native-android-app-automation) | Native app automation, tapping, entering text, reading text, buttons, checkboxes, radio buttons, toggles, Android key events, screenshots, orientation, and app-specific examples. |
| 6 | [Mobile Gestures and Touch Actions](#6-mobile-gestures-and-touch-actions) | Tap, long press, press/release, swipe, scroll, drag-and-drop, pinch, zoom, multi-touch, coordinate gestures, element gestures, and gesture debugging. |
| 7 | [Real Android Devices and Emulator Testing](#7-real-android-devices-and-emulator-testing) | Emulator vs simulator, AVD setup, real device configuration, USB debugging, adb commands, Wi-Fi connection, APK deployment, and real-device execution rules. |
| 8 | [Real-Time Ecommerce End-to-End App Automation](#8-real-time-ecommerce-end-to-end-app-automation) | Ecommerce test cases, form validation, toast messages, product scrolling, dynamic product selection, checkout validation, total amount validation, and utility refactoring. |
| 9 | [Hybrid App and Mobile Browser Automation](#9-hybrid-app-and-mobile-browser-automation) | Native/webview context switching, hybrid apps, mobile Chrome, Android browser capabilities, Chrome locators, browser scrolling, mobile web assertions, and responsive testing. |
| 10 | [iOS Automation with Appium](#10-ios-automation-with-appium) | Xcode, iPhone simulator, iOS desired capabilities, Appium Inspector for iOS, picker wheels, sliders, scrolling, tap, long press, app download, real iOS devices, UDID, XcodeOrgId, and bundle IDs. |
| 11 | [Selenium WebDriver Basics for Appium Engineers](#11-selenium-webdriver-basics-for-appium-engineers) | Selenium purpose, WebDriver setup, first Selenium program, browser automation, XPath, web locators, findElement/findElements, and Selenium concepts reused by Appium. |
| 12 | [Java OOP Basics for Appium and Selenium](#12-java-oop-basics-for-appium-and-selenium) | Java program structure, classes, objects, strings, arrays, interfaces, inheritance, polymorphism, constructors, access modifiers, Date/Calendar, and coding interview examples. |
| 13 | [TestNG Framework](#13-testng-framework) | TestNG installation, annotations, testng.xml, priority, dependencies, groups, parameters, DataProvider, listeners, pass/fail/skip, parallel execution, and reports. |
| 14 | [Maven Build Management](#14-maven-build-management) | Maven installation, project structure, pom.xml, dependencies, surefire plugin, TestNG integration, Maven profiles, and command-line execution. |
| 15 | [Page Object Model and Page Factory](#15-page-object-model-and-page-factory) | POM purpose, PageFactory, FindBy annotations, page classes, reusable page actions, test readability, and maintainable mobile automation design. |
| 16 | [Hybrid Appium Framework Design](#16-hybrid-appium-framework-design) | Maven template, base driver class, config properties, global properties, Appium server utilities, emulator startup, object independence, utility classes, and debugging framework bugs. |
| 17 | [Automation Framework Utilities](#17-automation-framework-utilities) | Excel test data, Apache POI, properties files, Log4j logging, screenshots, reusable helper classes, and framework-level test data management. |
| 18 | [Reporting and Failure Evidence](#18-reporting-and-failure-evidence) | TestNG listeners, screenshots on failure, HTML reports, XSLT reports, client reports, logs, Maven-compatible reporting, and CI artifacts. |
| 19 | [Jenkins CI/CD and Build Automation](#19-jenkins-cicd-and-build-automation) | Jenkins installation, freestyle jobs, Maven jobs, Ant jobs, Git/GitHub integration, scheduled builds, email notifications, workspaces, and CI execution. |
| 20 | [Cloud Mobile Execution and Parallel Testing](#20-cloud-mobile-execution-and-parallel-testing) | BrowserStack, Sauce Labs, cloud capabilities, Android/iOS cloud execution, parallel TestNG XML, generic capability utilities, and scalable execution. |
| 21 | [Git and GitHub Version Control](#21-git-and-github-version-control) | Git config, repository creation, staging, commits, remotes, push, branching, merge conflicts, GitHub usage, and Jenkins/Git integration. |
| 22 | [Database Testing with JDBC](#22-database-testing-with-jdbc) | MySQL setup, database/table creation, JDBC connection, SQL queries from tests, and integrating database validation into Selenium/Appium test cases. |
| 23 | [API Testing for Mobile Automation Projects](#23-api-testing-for-mobile-automation-projects) | REST API testing strategy, Rest Assured setup, GET/POST/PUT/DELETE, status code validation, response body assertions, auth tokens, and API setup/cleanup for mobile tests. |
| 24 | [Login Testing Strategy](#24-login-testing-strategy) | Valid login, invalid login, empty fields, locked user, logout, session validation, role-based login, API-assisted login setup, and secure credential handling. |
| 25 | [End-to-End Framework Execution Flow](#25-end-to-end-framework-execution-flow) | How Appium, TestNG, Maven, Page Objects, utilities, reporting, Jenkins, cloud execution, database checks, and API tests work together in one framework. |
| 26 | [Top Appium Selenium Mobile Automation Interview Questions and Answers](#26-top-appium-selenium-mobile-automation-interview-questions-and-answers) | Interview Q&A covering Appium architecture, capabilities, locators, gestures, contexts, Android/iOS setup, TestNG, Maven, Jenkins, cloud, API, login, and framework design. |

---

## 1. Course Overview and Appium Basics

Appium is an open-source mobile automation framework for testing Android and iOS applications. It supports native apps, hybrid apps, and mobile web apps. Appium uses the WebDriver protocol model, which makes it familiar to Selenium engineers moving into mobile automation.

### Key Concepts

- **Native app:** Installed mobile app built for Android or iOS.
- **Hybrid app:** Native app shell that contains one or more webviews.
- **Mobile web app:** Website opened in a mobile browser such as Chrome or Safari.
- **Appium Server:** Receives automation commands from the test code and forwards them to the mobile platform automation engine.
- **Android automation engine:** UIAutomator2 for modern Android automation.
- **iOS automation engine:** XCUITest for iOS automation.
- **Selendroid:** Older Android automation option for older Android API levels; Appium is preferred for modern Android versions.

### Architecture Flow

```text
TestNG / Java Test Code
        ↓
Appium Java Client
        ↓
Appium Server
        ↓
Android UIAutomator2 or iOS XCUITest
        ↓
Real Device / Emulator / Simulator
        ↓
Application Under Test
```

### Expected Result

A working Appium setup can launch an app, locate mobile elements, perform interactions, validate expected behavior, capture screenshots, and report test results.

---

## 2. Installation and Environment Setup

A stable Appium setup requires Java, Android tooling, Node.js, Appium Server, Appium Inspector, and an IDE such as Eclipse or IntelliJ IDEA.

### Required Tools

| Tool | Purpose |
|---|---|
| Java JDK | Runs Java test code and Maven/TestNG projects |
| Android Studio | Provides Android SDK, emulator, platform tools, and device manager |
| Node.js / npm | Installs Appium Server and Appium drivers |
| Appium Server | Receives WebDriver commands and controls mobile devices |
| Appium Inspector | Inspects mobile app UI elements and locators |
| Eclipse / IntelliJ IDEA | Java IDE for writing and running tests |
| Maven | Build and dependency management |
| TestNG | Java test framework |
| adb | Android Debug Bridge for device/emulator commands |

### Windows Environment Variables

```text
JAVA_HOME=C:\Program Files\Java\jdk-17
ANDROID_HOME=C:\Users\<user>\AppData\Local\Android\Sdk
PATH=%JAVA_HOME%\bin;%ANDROID_HOME%\platform-tools;%ANDROID_HOME%\emulator;%ANDROID_HOME%\tools;%ANDROID_HOME%\tools\bin
```

### Mac Environment Variables

```bash
export JAVA_HOME=$(/usr/libexec/java_home)
export ANDROID_HOME=$HOME/Library/Android/sdk
export PATH=$PATH:$ANDROID_HOME/platform-tools:$ANDROID_HOME/emulator:$ANDROID_HOME/tools:$ANDROID_HOME/tools/bin
```

### Appium Installation Commands

```bash
node --version
npm --version
npm install -g appium
appium driver install uiautomator2
appium driver install xcuitest
appium --version
appium
```

### Android Emulator Setup

1. Open Android Studio.
2. Open Device Manager.
3. Create a virtual device.
4. Select a phone profile such as Pixel or Nexus.
5. Select an Android system image.
6. Launch the emulator.
7. Confirm adb detects it.

```bash
adb devices
```

**Expected Result:**

```text
List of devices attached
emulator-5554 device
```

---

## 3. Launching Appium Sessions and Desired Capabilities

Desired capabilities tell Appium what platform, device, app, and automation engine to use.

### Android Native App Example

```java
import io.appium.java_client.android.AndroidDriver;
import io.appium.java_client.android.options.UiAutomator2Options;
import java.net.URL;

public class LaunchAndroidApp {
    public static void main(String[] args) throws Exception {
        UiAutomator2Options options = new UiAutomator2Options()
                .setPlatformName("Android")
                .setDeviceName("Pixel_Emulator")
                .setAutomationName("UiAutomator2")
                .setApp("C:/apps/General-Store.apk");

        AndroidDriver driver = new AndroidDriver(
                new URL("http://127.0.0.1:4723"), options);

        System.out.println("App launched successfully");
        driver.quit();
    }
}
```

**Expected Result:** The Android app launches on the emulator or device, prints a success message, and closes the session.

### Launch Installed App by Package and Activity

```java
UiAutomator2Options options = new UiAutomator2Options()
        .setDeviceName("Pixel_Emulator")
        .setAppPackage("com.android.calculator2")
        .setAppActivity("com.android.calculator2.Calculator")
        .setAutomationName("UiAutomator2");
```

**Expected Result:** Appium starts the installed Calculator app without reinstalling an APK.

### adb Commands to Find Package and Activity

```bash
adb shell dumpsys window | grep -E 'mCurrentFocus|mFocusedApp'
adb shell pm list packages
```

---

## 4. Inspecting Mobile Elements and Locator Strategy

Element inspection is critical in mobile automation. Use Appium Inspector or UIAutomatorViewer to inspect IDs, text, class names, bounds, content descriptions, and hierarchy.

### Locator Priority

| Priority | Locator Strategy | Notes |
|---:|---|---|
| 1 | Accessibility ID | Best when available and stable |
| 2 | Resource ID | Strong for Android native apps |
| 3 | iOS Predicate / Class Chain | Strong for iOS native apps |
| 4 | Android UiSelector | Useful for text and scrollable selectors |
| 5 | Class Name | Useful but often returns multiple elements |
| 6 | XPath | Use when necessary, but avoid brittle absolute XPath |

### Android Locator Examples

```java
// By resource ID
driver.findElement(AppiumBy.id("com.example:id/loginButton")).click();

// By accessibility ID
driver.findElement(AppiumBy.accessibilityId("Login")).click();

// By text using Android UiSelector
driver.findElement(AppiumBy.androidUIAutomator(
        "new UiSelector().text(\"Login\")")).click();

// By class name list
List<WebElement> buttons = driver.findElements(AppiumBy.className("android.widget.Button"));
for (WebElement button : buttons) {
    System.out.println(button.getText());
}
```

**Expected Result:** The test locates target elements, clicks the login button, and prints button text values.

### Nested Element Example

```java
WebElement form = driver.findElement(AppiumBy.id("com.example:id/loginForm"));
form.findElement(AppiumBy.className("android.widget.EditText")).sendKeys("user@example.com");
```

**Expected Result:** The search is scoped inside the form container instead of the whole screen.

---

## 5. Native Android App Automation

Native Android automation validates installed Android apps using Appium APIs.

### Basic UI Interaction

```java
WebElement nameField = driver.findElement(AppiumBy.id("com.androidsample.generalstore:id/nameField"));
nameField.sendKeys("Brian");

driver.hideKeyboard();
driver.findElement(AppiumBy.id("com.androidsample.generalstore:id/radioMale")).click();
driver.findElement(AppiumBy.id("com.androidsample.generalstore:id/btnLetsShop")).click();
```

**Expected Result:** The form is filled, the keyboard is hidden, a radio button is selected, and the app advances to the shopping screen.

### Toast Message Validation

```java
String toastMessage = driver.findElement(
        AppiumBy.xpath("//android.widget.Toast[1]")).getAttribute("name");

Assert.assertEquals(toastMessage, "Please enter your name");
```

**Expected Result:** The test validates the toast error message when required form data is missing.

### Android Key Event Example

```java
import io.appium.java_client.android.nativekey.AndroidKey;
import io.appium.java_client.android.nativekey.KeyEvent;

driver.pressKey(new KeyEvent(AndroidKey.BACK));
driver.pressKey(new KeyEvent(AndroidKey.HOME));
```

**Expected Result:** The test sends Android hardware/software key commands.

### Screenshot Example

```java
File source = ((TakesScreenshot) driver).getScreenshotAs(OutputType.FILE);
File destination = new File("screenshots/home.png");
FileUtils.copyFile(source, destination);
```

**Expected Result:** A screenshot file is saved for reporting or debugging.

---

## 6. Mobile Gestures and Touch Actions

Mobile automation requires realistic gestures beyond simple clicks.

### Tap Gesture

```java
PointerInput finger = new PointerInput(PointerInput.Kind.TOUCH, "finger");
Sequence tap = new Sequence(finger, 1);
tap.addAction(finger.createPointerMove(Duration.ZERO, PointerInput.Origin.viewport(), 500, 900));
tap.addAction(finger.createPointerDown(PointerInput.MouseButton.LEFT.asArg()));
tap.addAction(finger.createPointerUp(PointerInput.MouseButton.LEFT.asArg()));
driver.perform(Arrays.asList(tap));
```

**Expected Result:** Appium taps the screen at the provided coordinates.

### Long Press Gesture

```java
WebElement element = driver.findElement(AppiumBy.accessibilityId("Long Press"));
PointerInput finger = new PointerInput(PointerInput.Kind.TOUCH, "finger");
Sequence longPress = new Sequence(finger, 1);
Point center = element.getRect().getPoint();
longPress.addAction(finger.createPointerMove(Duration.ZERO, PointerInput.Origin.viewport(), center.x, center.y));
longPress.addAction(finger.createPointerDown(PointerInput.MouseButton.LEFT.asArg()));
longPress.addAction(new Pause(finger, Duration.ofSeconds(2)));
longPress.addAction(finger.createPointerUp(PointerInput.MouseButton.LEFT.asArg()));
driver.perform(Arrays.asList(longPress));
```

**Expected Result:** A long-press menu or long-press behavior is triggered.

### Scroll Using Android UiScrollable

```java
WebElement product = driver.findElement(AppiumBy.androidUIAutomator(
        "new UiScrollable(new UiSelector().scrollable(true))" +
        ".scrollIntoView(new UiSelector().text(\"Air Jordan 4 Retro\"));"));
product.click();
```

**Expected Result:** The app scrolls until the product text is visible, then selects it.

### Drag and Drop

```java
WebElement source = driver.findElement(AppiumBy.id("drag_item"));
WebElement target = driver.findElement(AppiumBy.id("drop_zone"));
new Actions(driver).dragAndDrop(source, target).perform();
```

**Expected Result:** The source element is moved to the target drop area.

---

## 7. Real Android Devices and Emulator Testing

### Real Device Setup

1. Enable Developer Options.
2. Enable USB Debugging.
3. Connect the device by USB.
4. Accept the RSA debugging prompt.
5. Confirm device connection.

```bash
adb devices
adb install path/to/app.apk
adb shell getprop ro.build.version.release
```

**Expected Result:** The real Android device appears as `device`, and APK installation succeeds.

### Wi-Fi Connection

```bash
adb tcpip 5555
adb shell ip addr show wlan0
adb connect <device-ip>:5555
adb devices
```

**Expected Result:** The device can run Appium tests over Wi-Fi after initial USB setup.

### Emulator vs Simulator

| Type | Platform | Notes |
|---|---|---|
| Emulator | Android | Emulates Android hardware/software and supports APK testing |
| Simulator | iOS | Simulates iOS behavior on macOS with Xcode |
| Real Device | Android/iOS | Best for final compatibility, hardware, camera, network, gestures, and performance checks |

---

## 8. Real-Time Ecommerce End-to-End App Automation

This module validates a realistic shopping workflow.

### Test Coverage

| Test Case | Validation |
|---|---|
| Fill form details | User enters name, gender, country, and starts shopping |
| Empty form validation | Toast message appears when name is missing |
| Scroll product list | App scrolls until target product is visible |
| Select product dynamically | Product selected by visible text instead of hardcoded index |
| Validate checkout | Selected products appear in cart |
| Validate total amount | Sum of item prices equals displayed total |

### Dynamic Product Selection

```java
public void addProductToCart(String productName) {
    driver.findElement(AppiumBy.androidUIAutomator(
            "new UiScrollable(new UiSelector().scrollable(true))" +
            ".scrollIntoView(new UiSelector().text(\"" + productName + "\"));"));

    int count = driver.findElements(AppiumBy.id("com.androidsample.generalstore:id/productName")).size();
    for (int i = 0; i < count; i++) {
        String name = driver.findElements(AppiumBy.id("com.androidsample.generalstore:id/productName")).get(i).getText();
        if (name.equalsIgnoreCase(productName)) {
            driver.findElements(AppiumBy.id("com.androidsample.generalstore:id/productAddCart")).get(i).click();
            break;
        }
    }
}
```

**Expected Result:** The requested product is located dynamically and added to the cart.

### Total Amount Validation

```java
List<WebElement> prices = driver.findElements(AppiumBy.id("com.androidsample.generalstore:id/productPrice"));
double sum = 0;

for (WebElement price : prices) {
    sum += Double.parseDouble(price.getText().replace("$", ""));
}

String totalText = driver.findElement(AppiumBy.id("com.androidsample.generalstore:id/totalAmountLbl")).getText();
double displayedTotal = Double.parseDouble(totalText.replace("$", ""));

Assert.assertEquals(displayedTotal, sum, 0.01);
```

**Expected Result:** The displayed total equals the calculated sum of product prices.

---

## 9. Hybrid App and Mobile Browser Automation

Hybrid apps require context switching between native views and webviews.

### Print Contexts and Switch to WebView

```java
Set<String> contexts = driver.getContextHandles();
for (String context : contexts) {
    System.out.println(context);
}

driver.context("WEBVIEW_com.example");
driver.findElement(By.cssSelector("input[name='q']")).sendKeys("Appium hybrid testing");
driver.context("NATIVE_APP");
```

**Expected Result:** The test interacts with web elements inside a webview, then returns to native app automation.

### Mobile Chrome Capabilities

```java
UiAutomator2Options options = new UiAutomator2Options()
        .setDeviceName("Pixel_Emulator")
        .setPlatformName("Android")
        .setAutomationName("UiAutomator2")
        .withBrowserName("Chrome");

AndroidDriver driver = new AndroidDriver(new URL("http://127.0.0.1:4723"), options);
driver.get("https://www.google.com");
```

**Expected Result:** Appium opens Chrome on the Android device and navigates to Google.

---

## 10. iOS Automation with Appium

iOS automation requires macOS, Xcode, Appium, and XCUITest.

### iOS Simulator Capabilities

```java
import io.appium.java_client.ios.IOSDriver;
import io.appium.java_client.ios.options.XCUITestOptions;

XCUITestOptions options = new XCUITestOptions()
        .setPlatformName("iOS")
        .setDeviceName("iPhone 12")
        .setPlatformVersion("16.0")
        .setAutomationName("XCUITest")
        .setApp("/path/to/MyApp.app");

IOSDriver driver = new IOSDriver(new URL("http://127.0.0.1:4723"), options);
```

**Expected Result:** The iOS simulator starts and launches the specified app.

### iOS Picker Wheel

```java
WebElement picker = driver.findElement(AppiumBy.iOSClassChain("**/XCUIElementTypePickerWheel[1]"));
picker.sendKeys("Canada");
```

**Expected Result:** The picker wheel changes to the requested value.

### iOS Real Device Required Capabilities

| Capability | Purpose |
|---|---|
| `udid` | Identifies the real iOS device |
| `xcodeOrgId` | Apple Developer Team ID |
| `xcodeSigningId` | Usually `iPhone Developer` |
| `bundleId` | Installed iOS app identifier |
| `automationName` | `XCUITest` |

---

## 11. Selenium WebDriver Basics for Appium Engineers

Appium uses Selenium-style WebDriver concepts, so Selenium fundamentals are useful.

### Selenium Browser Example

```java
WebDriver driver = new ChromeDriver();
driver.get("https://example.com");
driver.manage().window().maximize();
String heading = driver.findElement(By.tagName("h1")).getText();
Assert.assertTrue(heading.length() > 0);
driver.quit();
```

**Expected Result:** Chrome opens a website, reads the page heading, validates it, and closes.

### Common Selenium Locators

```java
driver.findElement(By.id("username"));
driver.findElement(By.name("email"));
driver.findElement(By.className("btn-primary"));
driver.findElement(By.linkText("Login"));
driver.findElement(By.xpath("//button[text()='Submit']"));
driver.findElements(By.tagName("a"));
```

---

## 12. Java OOP Basics for Appium and Selenium

Java OOP helps build reusable Appium frameworks.

### Class and Object

```java
public class User {
    private String email;

    public User(String email) {
        this.email = email;
    }

    public String getEmail() {
        return email;
    }
}
```

### Interface and Polymorphism

```java
public interface DriverFactory {
    WebDriver createDriver();
}

public class AndroidDriverFactory implements DriverFactory {
    public WebDriver createDriver() {
        // return AndroidDriver instance
        return null;
    }
}
```

**Expected Result:** Framework code can depend on `DriverFactory` instead of a specific driver implementation.

### Reverse String Interview Example

```java
String input = "Appium";
String reversed = new StringBuilder(input).reverse().toString();
Assert.assertEquals(reversed, "muippA");
```

---

## 13. TestNG Framework

TestNG controls test execution, grouping, data, reports, and parallelism.

### Basic TestNG Test

```java
import org.testng.Assert;
import org.testng.annotations.Test;

public class LoginTests {
    @Test(priority = 1, groups = {"smoke"})
    public void validLoginTest() {
        Assert.assertTrue(true);
    }
}
```

### TestNG DataProvider

```java
@DataProvider(name = "loginData")
public Object[][] loginData() {
    return new Object[][] {
            {"valid@example.com", "Password123", true},
            {"invalid@example.com", "wrong", false}
    };
}

@Test(dataProvider = "loginData")
public void loginTest(String email, String password, boolean expectedSuccess) {
    Assert.assertNotNull(email);
    Assert.assertNotNull(password);
}
```

### testng.xml

```xml
<suite name="Mobile Automation Suite" parallel="tests" thread-count="2">
    <test name="Android Smoke Tests">
        <groups>
            <run>
                <include name="smoke"/>
            </run>
        </groups>
        <classes>
            <class name="tests.LoginTests"/>
        </classes>
    </test>
</suite>
```

**Expected Result:** TestNG runs selected tests, supports grouping, generates reports, and can execute tests in parallel.

---

## 14. Maven Build Management

Maven manages dependencies, build lifecycle, and command-line execution.

### pom.xml Dependencies

```xml
<dependencies>
    <dependency>
        <groupId>io.appium</groupId>
        <artifactId>java-client</artifactId>
        <version>9.2.2</version>
    </dependency>
    <dependency>
        <groupId>org.testng</groupId>
        <artifactId>testng</artifactId>
        <version>7.10.2</version>
        <scope>test</scope>
    </dependency>
</dependencies>
```

### Surefire Plugin

```xml
<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-surefire-plugin</artifactId>
            <version>3.2.5</version>
            <configuration>
                <suiteXmlFiles>
                    <suiteXmlFile>testng.xml</suiteXmlFile>
                </suiteXmlFiles>
            </configuration>
        </plugin>
    </plugins>
</build>
```

### Maven Commands

```bash
mvn clean test
mvn test -Dplatform=android
mvn test -DsuiteXmlFile=testng.xml
```

**Expected Result:** Maven downloads dependencies, compiles the project, and executes TestNG tests.

---

## 15. Page Object Model and Page Factory

Page Object Model separates locators and UI actions from test classes.

### Page Factory Example

```java
public class LoginPage {
    private AndroidDriver driver;

    @AndroidFindBy(id = "com.example:id/email")
    private WebElement emailField;

    @AndroidFindBy(id = "com.example:id/password")
    private WebElement passwordField;

    @AndroidFindBy(id = "com.example:id/login")
    private WebElement loginButton;

    public LoginPage(AndroidDriver driver) {
        this.driver = driver;
        PageFactory.initElements(new AppiumFieldDecorator(driver), this);
    }

    public void login(String email, String password) {
        emailField.sendKeys(email);
        passwordField.sendKeys(password);
        loginButton.click();
    }
}
```

### Test Using Page Object

```java
@Test
public void validLoginTest() {
    LoginPage loginPage = new LoginPage(driver);
    loginPage.login("user@example.com", "Password123");
    Assert.assertTrue(driver.findElement(AppiumBy.id("com.example:id/dashboard")).isDisplayed());
}
```

**Expected Result:** The test remains readable and page locator changes are isolated inside the page class.

---

## 16. Hybrid Appium Framework Design

A robust framework includes reusable driver setup, configuration, utilities, page objects, and reporting.

### Base Driver Class

```java
public class BaseTest {
    protected AndroidDriver driver;

    @BeforeMethod
    public void setUp() throws Exception {
        UiAutomator2Options options = new UiAutomator2Options()
                .setDeviceName(System.getProperty("deviceName", "Pixel_Emulator"))
                .setApp(System.getProperty("appPath", "apps/app.apk"))
                .setAutomationName("UiAutomator2");

        driver = new AndroidDriver(new URL("http://127.0.0.1:4723"), options);
    }

    @AfterMethod
    public void tearDown() {
        if (driver != null) {
            driver.quit();
        }
    }
}
```

### Config Properties

```properties
platformName=Android
deviceName=Pixel_Emulator
appPath=apps/General-Store.apk
appiumServerUrl=http://127.0.0.1:4723
```

**Expected Result:** The framework can run tests with configurable device, app, and server values.

### Start Appium Server Programmatically

```java
AppiumDriverLocalService service = new AppiumServiceBuilder()
        .withIPAddress("127.0.0.1")
        .usingPort(4723)
        .build();

service.start();
// run tests
service.stop();
```

---

## 17. Automation Framework Utilities

### Excel Test Data with Apache POI

```java
FileInputStream fis = new FileInputStream("testdata/LoginData.xlsx");
Workbook workbook = WorkbookFactory.create(fis);
Sheet sheet = workbook.getSheet("Login");
String email = sheet.getRow(1).getCell(0).getStringCellValue();
String password = sheet.getRow(1).getCell(1).getStringCellValue();
workbook.close();
```

**Expected Result:** Test data is read from Excel and can be passed into TestNG tests.

### Properties File Utility

```java
Properties properties = new Properties();
FileInputStream fis = new FileInputStream("config.properties");
properties.load(fis);
String deviceName = properties.getProperty("deviceName");
```

### Log4j Logging

```java
private static final Logger logger = LogManager.getLogger(LoginTests.class);
logger.info("Starting login test");
logger.error("Login failed");
```

**Expected Result:** Framework execution has reusable data access, configuration, and logs.

---

## 18. Reporting and Failure Evidence

### TestNG Listener Screenshot on Failure

```java
public class ScreenshotListener implements ITestListener {
    public void onTestFailure(ITestResult result) {
        Object testClass = result.getInstance();
        AndroidDriver driver = ((BaseTest) testClass).driver;
        File source = driver.getScreenshotAs(OutputType.FILE);
        try {
            FileUtils.copyFile(source, new File("screenshots/" + result.getName() + ".png"));
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### Attach Listener

```xml
<listeners>
    <listener class-name="listeners.ScreenshotListener"/>
</listeners>
```

**Expected Result:** Failed tests automatically capture screenshots for debugging and reporting.

---

## 19. Jenkins CI/CD and Build Automation

Jenkins automates framework execution after code changes or on a schedule.

### Jenkins Freestyle Build Steps

```bash
mvn clean test -DsuiteXmlFile=testng.xml
```

### Jenkins Pipeline Example

```groovy
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps { git 'https://github.com/BrianGator/Appium-Selenium-Mobile-Automation-Showcase.git' }
        }
        stage('Install and Test') {
            steps { sh 'mvn clean test' }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: 'screenshots/**/*, target/surefire-reports/**/*', allowEmptyArchive: true
            junit 'target/surefire-reports/*.xml'
        }
    }
}
```

**Expected Result:** Jenkins checks out the project, runs Maven tests, archives reports/screenshots, and publishes JUnit results.

### CI/CD Best Practices

- Use stable test devices or cloud devices.
- Keep smoke tests short for every commit.
- Run full regression nightly or before release.
- Store credentials as Jenkins credentials or environment variables.
- Archive screenshots, logs, and HTML reports.
- Use Maven profiles for Android, iOS, local, and cloud execution.

---

## 20. Cloud Mobile Execution and Parallel Testing

Cloud providers such as BrowserStack and Sauce Labs allow execution on many real and virtual devices.

### Cloud Capability Example

```java
MutableCapabilities capabilities = new MutableCapabilities();
capabilities.setCapability("platformName", "Android");
capabilities.setCapability("appium:deviceName", "Samsung Galaxy S22");
capabilities.setCapability("appium:platformVersion", "12.0");
capabilities.setCapability("appium:app", "bs://uploaded-app-id");
capabilities.setCapability("appium:automationName", "UiAutomator2");

AndroidDriver driver = new AndroidDriver(
        new URL("https://USERNAME:ACCESS_KEY@hub-cloud.browserstack.com/wd/hub"),
        capabilities);
```

**Expected Result:** Tests run on a cloud-hosted Android device.

### Parallel TestNG Cloud Execution

```xml
<suite name="Cloud Mobile Suite" parallel="tests" thread-count="2">
    <test name="Android 12 Samsung">
        <parameter name="deviceName" value="Samsung Galaxy S22"/>
        <classes><class name="tests.LoginTests"/></classes>
    </test>
    <test name="Android 13 Pixel">
        <parameter name="deviceName" value="Google Pixel 7"/>
        <classes><class name="tests.LoginTests"/></classes>
    </test>
</suite>
```

**Expected Result:** The same tests run across multiple devices in parallel.

---

## 21. Git and GitHub Version Control

### Common Git Commands

```bash
git config --global user.name "Brian McCarthy"
git config --global user.email "briansmc@gmail.com"
git init
git status
git add .
git commit -m "Add Appium framework"
git remote add origin https://github.com/BrianGator/Appium-Selenium-Mobile-Automation-Showcase.git
git push -u origin master
```

### Branching and Merge Conflicts

```bash
git checkout -b feature/login-tests
git add .
git commit -m "Add login tests"
git checkout master
git merge feature/login-tests
```

**Expected Result:** Test framework changes are versioned, shared, branched, merged, and integrated into CI.

---

## 22. Database Testing with JDBC

Database validation can confirm that UI or API actions created correct backend records.

### JDBC Connection Example

```java
Connection connection = DriverManager.getConnection(
        "jdbc:mysql://localhost:3306/mobileqa", "root", "password");

Statement statement = connection.createStatement();
ResultSet resultSet = statement.executeQuery(
        "SELECT status FROM orders WHERE order_id = 1001");

if (resultSet.next()) {
    String status = resultSet.getString("status");
    Assert.assertEquals(status, "PLACED");
}

connection.close();
```

**Expected Result:** The test confirms that the database order status is `PLACED`.

### Database Testing Use Cases

- Validate user registration records.
- Validate order creation.
- Confirm payment status.
- Confirm inventory updates.
- Prepare test data before UI tests.
- Clean up generated test data after automation.

---

## 23. API Testing for Mobile Automation Projects

API tests are useful for validating backend services and preparing mobile test data.

### Rest Assured Dependency

```xml
<dependency>
    <groupId>io.rest-assured</groupId>
    <artifactId>rest-assured</artifactId>
    <version>5.4.0</version>
    <scope>test</scope>
</dependency>
```

### GET API Test

```java
import static io.restassured.RestAssured.*;
import static org.hamcrest.Matchers.*;

@Test
public void getUserProfileTest() {
    given()
        .baseUri("https://api.example.com")
        .header("Authorization", "Bearer token")
    .when()
        .get("/users/123")
    .then()
        .statusCode(200)
        .body("id", equalTo(123))
        .body("email", containsString("@"));
}
```

**Expected Result:** The API returns HTTP 200 and the expected user profile fields.

### POST API Setup for UI Test

```java
String orderId = given()
        .baseUri("https://api.example.com")
        .contentType("application/json")
        .body("{\"productId\":101,\"quantity\":1}")
.when()
        .post("/orders")
.then()
        .statusCode(201)
        .extract()
        .path("id");

System.out.println("Created order: " + orderId);
```

**Expected Result:** API creates an order that can be opened and validated in the mobile app.

### API Checklist

| Area | Validation |
|---|---|
| Status codes | 200, 201, 204, 400, 401, 403, 404, 409, 422 |
| Headers | Auth, content type, caching, correlation IDs |
| Body | Required fields, values, data types, arrays |
| Negative tests | Missing fields, invalid IDs, bad tokens |
| Auth | Valid token, invalid token, expired token |
| Cleanup | Delete test data after test execution |

---

## 24. Login Testing Strategy

Login is a critical mobile workflow because it gates protected app functionality.

### Login Test Coverage

| Scenario | Expected Result |
|---|---|
| Valid login | User reaches home/dashboard screen |
| Invalid password | Error message appears and user remains logged out |
| Invalid username | Error message appears |
| Empty email/password | Required field validation appears |
| Locked user | Locked account message appears |
| Logout | User returns to login screen and session ends |
| Role-based login | Correct menus/features appear for role |
| Session expiration | App redirects to login or displays session-expired message |

### Login Page Object

```java
public class LoginPage {
    private AndroidDriver driver;

    private By email = AppiumBy.id("com.example:id/email");
    private By password = AppiumBy.id("com.example:id/password");
    private By loginButton = AppiumBy.id("com.example:id/login");
    private By errorMessage = AppiumBy.id("com.example:id/error");

    public LoginPage(AndroidDriver driver) {
        this.driver = driver;
    }

    public void login(String userEmail, String userPassword) {
        driver.findElement(email).sendKeys(userEmail);
        driver.findElement(password).sendKeys(userPassword);
        driver.findElement(loginButton).click();
    }

    public String getErrorMessage() {
        return driver.findElement(errorMessage).getText();
    }
}
```

### Valid and Invalid Login Tests

```java
@Test
public void validLoginTest() {
    LoginPage loginPage = new LoginPage(driver);
    loginPage.login("valid@example.com", "Password123");
    Assert.assertTrue(driver.findElement(AppiumBy.id("com.example:id/homeScreen")).isDisplayed());
}

@Test
public void invalidLoginTest() {
    LoginPage loginPage = new LoginPage(driver);
    loginPage.login("bad@example.com", "wrong");
    Assert.assertEquals(loginPage.getErrorMessage(), "Invalid username or password");
}
```

**Expected Result:** Valid credentials open the home screen. Invalid credentials show an error message.

### Secure Credential Handling

```java
String email = System.getenv("TEST_USER_EMAIL");
String password = System.getenv("TEST_USER_PASSWORD");
```

**Expected Result:** Credentials are loaded from environment variables instead of being hardcoded in source code.

---

## 25. End-to-End Framework Execution Flow

```text
GitHub Repository
      ↓
Jenkins CI/CD Job or Local Maven Command
      ↓
Maven Downloads Dependencies
      ↓
TestNG Reads testng.xml
      ↓
BaseTest Starts Appium Driver
      ↓
Page Objects Execute Mobile Workflows
      ↓
Utilities Read Config, Test Data, Logs, Screenshots
      ↓
API/JDBC Helpers Prepare or Validate Backend Data
      ↓
Assertions Validate Expected Results
      ↓
Listeners Capture Failure Evidence
      ↓
Reports and Artifacts Are Published
```

### Example Command

```bash
mvn clean test -Dplatform=android -DdeviceName=Pixel_Emulator -DsuiteXmlFile=testng.xml
```

**Expected Result:** The framework runs the requested Android suite, produces TestNG/Maven reports, and captures failure evidence.

---

## 26. Top Appium Selenium Mobile Automation Interview Questions and Answers

### 1. What is Appium?

Appium is an open-source mobile automation framework used to test Android and iOS native, hybrid, and mobile web applications using WebDriver-style commands.

### 2. How is Appium related to Selenium?

Appium extends the Selenium WebDriver protocol model to mobile automation. Test code sends commands to Appium Server, which forwards them to Android or iOS automation engines.

### 3. What are desired capabilities?

Desired capabilities are configuration values that define the platform, device, app, automation engine, and session behavior.

```java
UiAutomator2Options options = new UiAutomator2Options()
        .setDeviceName("Pixel_Emulator")
        .setApp("apps/app.apk")
        .setAutomationName("UiAutomator2");
```

### 4. What is the difference between native, hybrid, and mobile web apps?

Native apps are installed platform-specific apps. Hybrid apps contain webviews inside native apps. Mobile web apps run in a browser such as Chrome or Safari.

### 5. What is UIAutomatorViewer or Appium Inspector used for?

They inspect mobile UI hierarchy and help identify locators such as resource ID, text, class name, accessibility ID, and XPath.

### 6. Which locator strategy is preferred in Appium?

Accessibility ID and resource ID are usually preferred because they are more stable than XPath.

### 7. Why should XPath be avoided when possible?

XPath can be slow and brittle in native mobile apps because UI hierarchies change frequently.

### 8. How do you scroll to text in Android?

Use Android UiScrollable.

```java
driver.findElement(AppiumBy.androidUIAutomator(
    "new UiScrollable(new UiSelector().scrollable(true)).scrollIntoView(new UiSelector().text(\"Text\"));"));
```

### 9. How do you switch from native app to webview?

Use `getContextHandles()` and `context()`.

```java
for (String context : driver.getContextHandles()) {
    System.out.println(context);
}
driver.context("WEBVIEW_com.example");
```

### 10. How do you automate mobile gestures?

Use W3C actions, Appium gestures, or platform-specific commands for tap, long press, swipe, scroll, drag-and-drop, pinch, and zoom.

### 11. How do you run tests on a real Android device?

Enable USB debugging, connect the device, verify it with `adb devices`, and run Appium with capabilities pointing to that device.

### 12. What is needed for iOS real device testing?

A Mac, Xcode, Apple signing credentials, device UDID, `xcodeOrgId`, `xcodeSigningId`, Appium XCUITest driver, and a valid app bundle ID.

### 13. What is TestNG used for?

TestNG manages test execution, annotations, grouping, parameters, data providers, listeners, reports, and parallel execution.

### 14. Why is Maven used in Appium frameworks?

Maven manages dependencies, builds the project, runs tests, and integrates with CI tools such as Jenkins.

### 15. What is Page Object Model?

POM stores locators and page actions in page classes so tests are readable and easier to maintain.

### 16. How do you capture screenshots on failure?

Use a TestNG listener and `TakesScreenshot` when `onTestFailure()` runs.

### 17. How do you run Appium tests in Jenkins?

Configure Jenkins to check out code from GitHub and execute `mvn clean test`, then publish reports and archive artifacts.

### 18. How do BrowserStack or Sauce Labs help Appium testing?

They provide cloud-hosted real and virtual devices so teams can run tests across multiple OS/device combinations without maintaining a local device lab.

### 19. How can API testing support mobile automation?

APIs can create test data, validate backend behavior, authenticate users, and clean up records before or after UI tests.

### 20. What login scenarios should mobile automation cover?

Valid login, invalid credentials, empty fields, locked users, logout, session expiration, role-based access, and secure credential handling.

---

## Summary

This project documents a complete Appium/Selenium mobile automation learning path and framework strategy. It covers Android, iOS, native apps, hybrid apps, mobile browsers, gestures, TestNG, Maven, Jenkins, Page Object Model, reporting, cloud execution, Git, JDBC database checks, API testing, login testing, and interview preparation.
