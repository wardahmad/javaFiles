### XPath for a Web Element with Multiple Attributes

### Source Code
```Java
package chrome;

import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.Test;

public class InvokeChromePage {
	
public WebDriver driver;
	
	@Test
	public void chromepage() throws InterruptedException { 
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");
				
		driver = new ChromeDriver();
		driver.navigate().to("https://www.amazon.com/");
		
		List <WebElement> formElem = driver.findElements(By.xpath("//*[@name='site-search'][@id='nav-search-bar-form']"));
		for (WebElement eachLink:formElem) {
			System.out.println(eachLink.getText());
		}

		Thread.sleep(4000);
		driver.close();
	}
}

```

### The Result
<img src="img/img1.png" />
<img src="img/img2.png" />
<img src="img/img3.png" />