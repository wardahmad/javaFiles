### Applying 'text() function' type of XPath

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
		
		// Applying 'text() function' type of XPath
		driver.findElement(By.xpath("(//*[text() = 'Learn More'])[1]"));
		driver.findElement(By.xpath("(//*[text() = 'Online Part-Time Flex'])[2]"));
		driver.findElement(By.xpath("//*[text() = 'For Enterprise']"));
		driver.findElement(By.xpath("//*[text() = 'Land Your Dream Job in Tech']"));

		driver.close();
	}
}

```

### The Result
<img src="img/img1.png" />
<img src="img/img2.png" />
<img src="img/img3.png" />
<img src="img/img4.png" />