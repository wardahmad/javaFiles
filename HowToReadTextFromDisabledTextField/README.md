### How to Read a Text from a Disabled Text Field

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
		
		// How to Read a Text from a Text Field
		// I can't find any disabled Text Field, So I used an enabled text field
		WebElement inputElement = driver.findElement(By.xpath("(//input[@name='full_name'])[1]"));
		inputElement.sendKeys("Wardah");
		String inputAttr = inputElement.getDomAttribute("placeholder");
		System.out.println("Value of placeholder attribute: "+inputAttr);
		driver.close();
	}
}

```

### The Result
<img src="img/img1.png" />
<img src="img/img2.png" />
<img src="img/img3.png" />