### Pick a Date in any Online Date Widget

### Source Code
```Java
package chrome;

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
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.Test;

public class InvokeChromePage {

//public WebDriver driver;
	protected WebDriver driver;

	@Test
	public void chromepage() throws InterruptedException {
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");

		driver = new ChromeDriver();
		// implicit wait
		driver.manage().timeouts().implicitlyWait(5, TimeUnit.SECONDS);
		// URL launch
		driver.get("https://jqueryui.com/datepicker");
		// switch to frame
		WebElement frameEle = driver.findElement(By.xpath("//iframe[@class='demo-frame']"));
		driver.switchTo().frame(frameEle);
		// identify element within frame
		WebElement inputEle = driver.findElement(By.id("datepicker"));
		inputEle.click();
		// identify all td elements in list
		List<WebElement> t = driver.findElements(By.xpath("//table/tbody/tr/td"));
		// list traversal
		for (int k = 0; k < t.size(); k++) {
			// check date
			String dt = t.get(k).getText();
			if (dt.equals("28")) {
				t.get(k).click();
				break;
			}
		}
		// obtain selected date
		String val = inputEle.getAttribute("value");
		System.out.print("Date selected by date picker: " + val);
		Thread.sleep(4000);
		// close browser
		driver.close();
	}
}

```

### The Result
<img src="img/img1.gif" />