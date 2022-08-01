### Working with Checkboxes Using a Button Click

### Source Code
```Java
package dealFourLoans;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.Test;

public class DealFourLoans {
public WebDriver driver;
	
	@Test
	public void dealFourLoans() throws InterruptedException { 
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");
				
		driver = new ChromeDriver();
		driver.navigate().to("https://www.deal4loans.com/apply-home-loans.php");
		
		// Close the ads	
		WebElement element = (new WebDriverWait(driver,Duration.ofSeconds(10)))
				.until(ExpectedConditions.elementToBeClickable(By.xpath("//img[@src='https://www.deal4loans.com/images/close-btn.svg']")));
		element.click();
		
		//Identifying an Element Using ID Attribute
		WebElement chkBox = driver.findElement(By.xpath("//input[@id='accept']"));
		
		for (int i = 0; i < 2; i++) {
			  if (!(chkBox.isSelected())) {
				  chkBox.click();
				  Thread.sleep(2000);
				  continue;
			  }
			  chkBox.click();
		}
				
		Thread.sleep(2000);
		driver.quit();
	}
}
```

### The Result
![alt text](https://github.com/wardahmad/javaFiles/blob/master/WorkingWithCheckboxesUsingButtonClick/img/img1.gif)

<!-- <img src="img/" /> -->