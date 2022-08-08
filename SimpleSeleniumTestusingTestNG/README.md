### Simple Selenium Test using TestNG

### Source Code
```Java
package codingDojo;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.Assert;
import org.testng.annotations.Test;

public class CodingDojo {

	public WebDriver driver;

	@Test
	public void codingDojo() throws InterruptedException {

		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");

		driver = new ChromeDriver();
		// driver.manage().window().maximize();
		driver.navigate().to("https://login.codingdojo.com/login");

		// Contains "mai"
		String userNameTextBox = "input[name*='mai']";
		// starts-with "pass"
		String passTextBox = "input[name^='pass']";
		// ends-with "mit"
		String submitButton = "button[type$='mit']";
		String errParagraf = "/html/body/div[2]/div[2]/div[1]/form/div[1]/p";

		WebElement userName = driver.findElement(By.cssSelector(userNameTextBox));
		WebElement password = driver.findElement(By.cssSelector(passTextBox));
		WebElement submit = driver.findElement(By.cssSelector(submitButton));

		userName.sendKeys("user@user.com");
		password.sendKeys("1234");
		submit.click();
		Thread.sleep(2000);
		
		WebElement errMsg = driver.findElement(By.xpath("/html/body/div[2]/div[2]/div[1]/form/div[1]/p"));
		String result = errMsg.getText();
		Assert.assertEquals(result, "User not found in our database. Make sure your application was accepted.");
		driver.close();
	}
}

```

### The Result
<img src="img/img1.gif" />