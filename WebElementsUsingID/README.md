### Follow the below steps to locate web elements using Chrome’s Developer tool:

* Step #1: launch the Google Chrome’s Developer tool.
<img src="img/img1.png" />

* Step #2: locate the desired object within the web page. Right-click on the desired web element and inspect. 
<img src="img/img2.png" />

* Step #3: Click on Ctrl+F, and type 'localize-active-lang'
### Source Code
```Java
package codingDojo;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.Test;

public class CodingDojo {
	
public WebDriver driver;
	
	@Test
	public void codingDojo() throws InterruptedException { 
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");
				
		driver = new ChromeDriver();
		driver.manage().window().maximize();
		driver.navigate().to("https://www.codingdojo.com/");
		JavascriptExecutor js = (JavascriptExecutor)driver;
		js.executeScript("scrollBy(0, 7000)");
		driver.findElement(By.id("localize-active-lang")).click();
		Thread.sleep(2000);
		driver.close();
	}
}
```