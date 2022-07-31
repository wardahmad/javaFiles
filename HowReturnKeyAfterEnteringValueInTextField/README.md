### How to Return Key after Entering a Value in Text Field

### Source Code
```Java
package codingDojo;

import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.Test;

public class CodingDojo {
	
public WebDriver driver;
	
	@Test
	public void codingDojo() throws InterruptedException { 
		
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");
				
		driver = new ChromeDriver();
		//driver.manage().window().maximize();
		driver.navigate().to("https://www.codingdojo.com/");
		
		WebElement inputElement = driver.findElement(By.xpath("//input[@name='email_address']"));
		inputElement.sendKeys("user@user.com");
		Thread.sleep(7000);
		inputElement.sendKeys(Keys.RETURN);
		//textField.submit();	
		driver.close();
	}
}

```

### The Result
<img src="img/img1.png" />
<img src="img/img2.png" />