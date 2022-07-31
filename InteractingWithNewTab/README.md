### Interacting with New Tab

### Source Code
### Open a new tab, a new window, and a private incognito window

* New Tab
```Java
package codingDojo;

import java.util.ArrayList;
import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.testng.annotations.Test;

public class CodingDojo {
	
public WebDriver driver;
	
	@Test
	public void codingDojo() throws InterruptedException { 
		
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");
				
		driver = new ChromeDriver();
		//driver.manage().window().maximize();
		driver.navigate().to("https://www.codingdojo.com/");
		
		JavascriptExecutor js = (JavascriptExecutor)driver;
		js.executeScript("window.open()");
		ArrayList<String> tabs = new ArrayList<String>(driver.getWindowHandles());
		Thread.sleep(5000);

		//Switch to a new tab
		driver.switchTo().window(tabs.get(1));
		driver.get("http://google.com");Thread.sleep(5000);

		//switch back control to old tab
		driver.switchTo().window(tabs.get(0));
		Thread.sleep(5000);	
		driver.close();
	}
}
```
### The Result
<img src="img/img1.png" />

* New window
```Java

```
<img src="img/" />

* Private incognito window
```Java

```
<img src="img/" />
