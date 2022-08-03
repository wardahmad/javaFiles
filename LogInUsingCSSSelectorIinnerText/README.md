### Log in using CSSSelector innerText

### Source Code
```Java
package instagram;

import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.Keys;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.support.ui.ExpectedConditions;
import org.openqa.selenium.support.ui.WebDriverWait;
import org.testng.annotations.Test;

public class Instagram {

	public WebDriver driver;

	@Test
	public void instagrampage() throws InterruptedException {
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver.exe");

		driver = new ChromeDriver();
		driver.navigate().to("https://www.instagram.com/");
		// Contains "username"
		String userNameTextBox = "input[name*='username']";
		// Contains "password"
		String passTextBox = "input[name*='password']";
		// Contains "submit"
		String submitButton = "button[type*='submit']";

		// Waiting 10 seconds, until the user name <input> element is available.
		WebElement userName = (new WebDriverWait(driver, Duration.ofSeconds(10)))
				.until(ExpectedConditions.elementToBeClickable(By.cssSelector(userNameTextBox)));

		WebElement password = driver.findElement(By.cssSelector(passTextBox));
		WebElement submit = driver.findElement(By.cssSelector(submitButton));

		try {
			Thread.sleep(2000);
			userName.sendKeys("user@user.com");
			Thread.sleep(2000);
			password.sendKeys("fakePassword");
			Thread.sleep(2000);
			submit.click();
			// password.sendKeys(Keys.RETURN);
		} catch (InterruptedException e) {
			e.printStackTrace();
		}

		Thread.sleep(4000);
		driver.close();
	}
}

```

### The Result
<img src="img/img1.gif" />
<img src="img/img2.png" />
<img src="img/img3.png" />
<img src="img/img4.png" />