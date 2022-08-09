### Use "draganddropby" in any HTML Page

### Source Code
```Java
package dragnDrop;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.testng.annotations.Test;

public class DragnDrop {

	protected WebDriver driver;

	@Test
	public void dragnDrop() throws InterruptedException {

		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");

		driver = new ChromeDriver();

		driver.get("http://omayo.blogspot.com/p/page3.html");

		// Store draggable location into webelement
		WebElement draggable = driver
				.findElement(By.xpath("(//a[@class='ui-slider-handle ui-btn ui-shadow ui-btn-null'])[1]"));

		// Using DragAndDrop method release draggable webelement into offset.
		new Actions(driver).dragAndDropBy(draggable, 200, 10).build().perform();
		driver.quit();
	}
}

```

### The Result
<img src="img/img1.gif" />