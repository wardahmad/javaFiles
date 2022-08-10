### Simple Test Case in the Selenium Grid
### First: Setting Up Selenium Grid in the Command Line
<a href = 'https://docs.google.com/document/d/1Bu2wVp7NUdT5N4fgLIvKbcC21700lTL3ZYhek37LuE4/edit?usp=sharing'>Here</a>

### Source Code
```Java
package chrome;

import java.net.MalformedURLException;
import java.net.URL;
import java.sql.Date;
import java.text.SimpleDateFormat;
import java.time.Duration;
import java.util.Calendar;
import java.util.List;
import java.util.TimeZone;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.Platform;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.chrome.ChromeOptions;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.remote.DesiredCapabilities;
import org.openqa.selenium.remote.RemoteWebDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.Assert;
import org.testng.annotations.AfterTest;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;

public class InvokeChromePage {

//	public WebDriver driver;
	WebDriver driver;

	@Test
	public void chromepage() throws InterruptedException, MalformedURLException {
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");

		ChromeOptions chromeOptions = new ChromeOptions();
//		chromeOptions.setCapability("browserVersion", "100");
		chromeOptions.setCapability("platformName", "Windows");
		chromeOptions.setCapability("se:name", "My simple test"); 

		chromeOptions.setCapability("se:sampleMetadata", "Sample metadata value"); 
		WebDriver driver = new RemoteWebDriver(new URL("http://192.168.8.100:4444"), chromeOptions);
		driver.get("http://www.google.com");
		System.out.println("Title is- "+ driver.getTitle());
		driver.quit();
	}

}

```

### The Result
<img src="img/img1.gif" />