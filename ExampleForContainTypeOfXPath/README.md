### Example for 'Contain' Type of XPath

### Source Code
```Java
package codingDojo;

import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
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
		
		// Example for 'Contain' Type of XPath		
		WebElement button = driver.findElement(By.xpath("//button[contains(text(),'Alumni Testimonials')]"));
		String buttonResult = button.getText();
		System.out.println(buttonResult);
        
		Thread.sleep(1000);
		driver.close();
	}
}

```

### The Result
<img src="img/img1.png" />
<img src="img/img2.png" />