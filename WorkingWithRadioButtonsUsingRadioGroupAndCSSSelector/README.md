### Working with RadioButtons using RadioGroup and CSSSelector

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
		JavascriptExecutor js = (JavascriptExecutor) driver;
		driver.navigate().to("https://www.deal4loans.com/personal-loan.php");
		
		// Close the ads	
		WebElement element = (new WebDriverWait(driver,Duration.ofSeconds(10)))
				.until(ExpectedConditions.elementToBeClickable(By.xpath("//img[@src='https://www.deal4loans.com/images/close-btn.svg']")));
		element.click();

		js.executeScript("window.scrollBy(0,500)");
		Thread.sleep(1000);
		WebElement radioButton = driver.findElement(By.xpath("(//span[@class='outer employementStatus'])[2]"));

		try
        {
            Thread.sleep(1000);
            radioButton.click();
        }
        catch (InterruptedException e)
        {
            e.printStackTrace();
        }
        
        Thread.sleep(2000);
        driver.quit();
    }
}

```

### The Result
<img src="img/img1.gif" />