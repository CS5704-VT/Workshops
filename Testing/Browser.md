# Browser Automation

User interfaces are one of the most difficult parts of software to test due to a variety of issues (different hardware for use, browsers for viewing, avoiding production data, etc.). One technique to help with testing basic UI functionality is browser automation, which scripts the usage of web browsers. Browser automation systems, such as [Selenium](https://www.selenium.dev/) and [puppeteer](https://pptr.dev/) are useful for automating most things that users can do manually in browsers, saving time and effort for developers and testers to validate all possible interactions with a system. These platfors can also be integrated with continuous integration systems, such as Jenkins, to verify software changes in an automated build system.

### Browser Automation Concepts

A **driver** provides a unified interface for automating interaction with a browser. For example, WebDriver is an abstract interface that allows you to open a browser window and navigate, or drive, through the page to get to the desired page or perform the requested action, such as entering values in a form and clicking buttons. Further, you read the page and verify that it contains the correct values and properties.

There are several concrete drivers available, such as [FirefoxDriver](https://www.selenium.dev/selenium/docs/api/dotnet/html/T_OpenQA_Selenium_Firefox_FirefoxDriver.htm), and [ChromeDriver](https://chromedriver.chromium.org/), which will drive Firefox and Chrome, respectively. Using these drivers, you can see the browser perform the actions in real-time. While this can be useful for debugging, for testing purposes, this would create too much performance overhead. Instead, it is common to use light-weight versions of the web driver for faster tests. For example, [HtmlUnitDriver](https://github.com/SeleniumHQ/selenium/wiki/HtmlUnitDriver) provides a fast driver; however, it is still generally effective for rendering pages with Javascript. Alternatively, it is possible to use headless versions of browsers, such as the recent headless version of Chrome. This is what we'll be using for this workshop.

In a browser, an html page is represented by **DOM**, a _document model_ consisting of a tree of elements, attributes, and values.

**Testing**
Browser automation tests generally do the following:
1. Load a web page
2. Locate a target item (using a resource id or xpath) and perform an action
3. Verify the resulting DOM properties with assertions

**Loading**

Unfortunately, due to the dynamic nature of HTML and Javascript, pages loads and actions can take place asynchronously, which we need to wait for the page to reach the correct state before interacting with it.

There are generally two strategies for waiting.

1. Implicit Waits

An _implicit wait_ will wait for a set limit of time before timing out if an element has not appeared on the page. For example:

```driver.manage().timeouts().implicitlyWait( 10, TimeUnit.SECONDS );```

2. Explicit Waits

An _explicit wait_ will wait until a defined condition(s) occurs before continuing to the next step. For example, this will wait until the desired `span` element is visible on the page.

```
 WebDriverWait wait = new WebDriverWait(driver, 30);
 wait.until(ExpectedConditions.visibilityOfElementLocated(By.xpath("//span[@id='currentCoffee']")));
```

**Note:** Particularly for Javascript-based applications, explicit waits result in more reliable tests.

* **Expired Objects:** When a page changes, you may receive a StaleElementReferenceException. This occurs when an element no longer appears in the page's DOM, but you're still trying to iteract with it. One way to avoid this problem is to store the raw value (String/int) you need from the WebElement before performing an action that changes the page.

## 📝 Activity

In this activity, you will gain basic experience with browser automation testing using puppeteer. Additionally, you will briefly interact with two Javascript testing tools, the [Mocha](https://mochajs.org/) Node.js test framework and [chai](https://www.chaijs.com/) assertion library, which can be combined to automate test cases, implement assert statements for validating output, and facilitate [BDD](https://medium.com/@connecttokc/behaviour-driven-testing-in-node-js-using-mocha-chai-5e0c85258bbe) by describing test cases based on user behavior.

_Prerequisites_
* Unfortunately browser automation will not work in Docable, so at least one partner needs install `npm` and `node` on your system
    * You should have a package manager installed on your system from a previous workshop
* Basic knowledge of Javascript is helpful, but not required

### Steps
1. Clone the [activity repository](https://github.com/CS5704-VT/BrowserAutomation). Navigate into the project directory and run `npm install` to add all the dependencies.
2. Run `node duckduckgo.js` to observe the browser automation at work. The browser should automatically search for a keyword.
    * Close the browser when completed, or uncomment the `browser.close();` command to automatically exit.
3. Browser automation is also useful for testing UIs in different application. Edit the `duckduckgo.js` file to uncomment the `await` commands on lines 39-40 to emulate the test in an iPhone interface.
4. Extend the code to perform another action on the website (i.e. another search).
5. Run the unit tests using `npm test` and inspect the results. Can you fix the failing test cases?
    * In the repository, see `test/search.js`
6. Discuss with your partner how the test frameworks used in this activity can support behavior-driven development. Then, pick one _advocate_ and one _detractor_ to discuss why BDD can improve or inhibit software engineering processes.

### [Advanced Testing ⏭️](Mutants.md)

> This workshop is based on the [Integration Testing](https://github.com/CSC-510/IntegrationTesting) workshop by [Dr. Chris Parnin](https://chrisparnin.me) at NC State.
