### Copy and Paste a Web Element Value

### Source Code
```Java
package chrome;

import java.sql.Date;
import java.text.SimpleDateFormat;
import java.time.Duration;
import java.util.Calendar;
import java.util.TimeZone;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.Test;

public class InvokeChromePage {

	protected WebDriver driver;

	@Test
	public void chromepage() throws InterruptedException {
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");

		driver = new ChromeDriver();
		Actions act = new Actions(driver);

		driver.navigate().to("https://www.google.com.sa/");

		WebElement inputEle = driver.findElement(By.xpath("//input[@class='gLFyf gsfi']"));
		Thread.sleep(2000);
		inputEle.sendKeys("JAVA");

		Thread.sleep(2000);
		act.moveToElement(inputEle).doubleClick().build().perform();

		// apply copy command
		inputEle.sendKeys(Keys.chord(Keys.CONTROL, "c"));
		Thread.sleep(2000);
		// apply the command to paste
		inputEle.sendKeys(Keys.chord(Keys.CONTROL, "v"));

		Thread.sleep(4000);
		driver.close();
	}
}

```

### The Result
<img src="img/img1.png" />