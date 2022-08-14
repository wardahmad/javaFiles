### Cross Browser Testing using NG

### Source Code

### `TestNGParameters.java` File
```Java
package testNGParameters;

import org.testng.annotations.Parameters;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;

public class TestNGParameters {

	public WebDriver driver;

	@Parameters({ "browser" })
	@BeforeTest
	public void before(String browser) {

		System.out.println("Running browser is: " + browser);

		if (browser.equals("firefox")) {
			System.setProperty("webdriver.gecko.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\geckodriver.exe");
			driver = new FirefoxDriver();

		}

		else if (browser.equals("chrome")) {
			System.setProperty("webdriver.chrome.driver",
					"C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver14\\chromedriver.exe");
			driver = new ChromeDriver();

		}

	}

	@Test(priority = -1)
	public void mytest()

	{
		driver.get("https://www.codingdojo.com/");

	}

	@Test(priority = 1)
	public void secondTest()

	{
		driver.get("https://www.google.com.sa/");
	}
}

```

### `testing.xml` File
```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE suite SYSTEM "https://testng.org/testng-1.0.dtd">
<suite name="Suite">

	<test name="facebook FirefoxTest">

		<parameter name="browser" value="firefox" />
		<classes>
			<class name="testNGParameters.TestNGParameters" />
		</classes>
	</test> <!-- Test -->
	<test name="facebook ChromeTest">
		<parameter name="browser" value="chrome" />
		<classes>
			<class name="testNGParameters.TestNGParameters" />
		</classes>
	</test>
</suite> <!-- Suite -->
```

### The Result
<img src="img/img1.gif" />