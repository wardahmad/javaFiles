### Simple program in Java using Selenium to evoke the Firefox browser

### Source Code
```Java
package firefox;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;

public class InvokeFirefoxPage {
	
public static void main(String[] args) throws InterruptedException {
        
        //Creating a driver object referencing WebDriver interface
        WebDriver driver;
        
        //Setting webdriver.gecko.driver property
        System.setProperty("webdriver.gecko.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\geckodriver.exe" );
        
        //Instantiating driver object and launching browser
        driver = new FirefoxDriver();
        
        //Using get() method to open a web page
        driver.get("https://www.tutorialspoint.com/index.htm");
        
        //identify element
        WebElement element = driver.findElement(By.name("key"));
        
        element.sendKeys("Java");
        
        // press ENTER
        //element.sendKeys(Keys.RETURN);
        
        // Or use this command to click on the button
		WebElement button = driver.findElement(By.xpath("//body/main[1]/section[1]/div[1]/div[1]/div[1]/div[1]/form[1]/button[1]/i[1]"));
		button.click();
		Thread.sleep(7000);
		
        //Closing the browser
        driver.quit();
    }
}

```

### The Result
<img src="img/FirefoxResult.png" />