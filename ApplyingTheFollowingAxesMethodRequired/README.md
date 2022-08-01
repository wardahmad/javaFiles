### Applying the 'Following' axes method-Required

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
		WebElement inputEle = driver.findElement(By.xpath("//*[@id='link_parent']//following::input[1]"));
		WebElement divEle = driver.findElement(By.xpath("//*[@id='featured_press']//following::div[1]"));
		WebElement anotherDivEle = driver.findElement(By.xpath("(//*[@id='video_modal']//following::*)[1]"));
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