### Failing Scenarios in Relative XPath

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
import org.testng.annotations.Test;

public class CodingDojo {
	
public WebDriver driver;
	
	@Test
	public void codingDojo() throws InterruptedException { 
		
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");
				
		driver = new ChromeDriver();
		//driver.manage().window().maximize();
		driver.navigate().to("https://www.codingdojo.com/"); 
		WebElement textEle = driver.findElement(By.xpath("//h2[contains(text(),'Land Your Dream Job in Tech')]"));
		WebElement headEle = driver.findElement(By.xpath("//h2[contains(text(),'Redefine Possible')]"));
		WebElement anchEle = driver.findElement(By.xpath("//a[contains(text(),'Meet Our Alumni')]"));
		WebElement listEle = driver.findElement(By.xpath("//li[contains(text(),'CAMPUSES')]"));
		Thread.sleep(5000);
		driver.close();
	}
}

```

### The Result
<img src="img/img1.png" />
<img src="img/img2.png" />
<img src="img/img3.png" />
<img src="img/img4.png" />
<img src="img/img5.png" />