### Working with the Scrollbar

### Source Code
```Java
package codingDojo;

import java.util.ArrayList;
import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.WindowType;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.Select;
import org.testng.annotations.Test;

public class CodingDojo {
	
public WebDriver driver;
	
	@Test
	public void codingDojo() throws InterruptedException { 
		
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");
				
		driver = new ChromeDriver();
		driver.manage().window().maximize();
		driver.navigate().to("https://www.codingdojo.com/");

		Thread.sleep(2000);
		driver.findElement(By.tagName("body")).sendKeys(Keys.PAGE_DOWN); 

		Thread.sleep(2000);
		driver.close();
	}
}

```

### The Result
<img src="img/img1.gif" />