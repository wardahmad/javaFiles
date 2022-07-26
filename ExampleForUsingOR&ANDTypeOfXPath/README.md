### Example for 'Using OR & AND' Type of XPath

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
		
		// Example for 'Using OR & AND' Type of XPath
		WebElement iElement = driver.findElement(By.xpath("//i[@id='program_courses' or @class='fas fa-chevron-down']"));
		System.out.println(iElement.getText());
		Thread.sleep(1000);
		
		WebElement divElement = driver.findElement(By.xpath("//div[@id='admissions_list' and @class='dropdown_menu']"));
		System.out.println(divElement.getText());
		Thread.sleep(1000);
		
		WebElement divTwolement = driver.findElement(By.xpath("//div[@id='about_list' and @class='dropdown_menu']"));
		System.out.println(divTwolement.getText());

		Thread.sleep(1000);
		driver.close();
	}
}

```

### The Result
<img src="img/img0.png" />
<img src="img/img1.png" />
<img src="img/img2.png" />
<img src="img/img3.png" />