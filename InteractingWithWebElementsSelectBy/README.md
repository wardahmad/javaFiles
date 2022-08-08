### Interacting with Web Elements - SelectBy

### Source Code
```Java
package codingDojo;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.Select;
import org.testng.Assert;
import org.testng.annotations.Test;

public class CodingDojo {

	public WebDriver driver;

	@Test
	public void codingDojo() throws InterruptedException {

		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");
		
		driver = new ChromeDriver();
		JavascriptExecutor js = (JavascriptExecutor) driver;
		 driver.manage().window().maximize();
		driver.navigate().to("https://www.codingdojo.com/");
		
		Select drplocation = new Select(driver.findElement(By.name("location")));
		js.executeScript("window.scrollBy(0,1000)");
		Thread.sleep(2000);
		drplocation.selectByVisibleText("Los Angeles, CA");
		Thread.sleep(4000);		
		driver.close();
	}
}

```

### The Result
<img src="img/img1.gif" />