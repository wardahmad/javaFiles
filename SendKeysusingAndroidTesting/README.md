### SendKeys using Android Testing

### Source Code
```Java
package Appium.FirstAppiumProject;

import java.net.MalformedURLException;
import java.net.URL;
import java.time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.remote.DesiredCapabilities;
import org.testng.Assert;
import org.testng.annotations.Test;

import io.appium.java_client.AppiumBy;
import io.appium.java_client.android.AndroidDriver;
import io.appium.java_client.android.options.UiAutomator2Options;
import io.appium.java_client.remote.MobileCapabilityType;

public class FirstTestingAppuim {

	public AndroidDriver driver;

	@Test
	public void firstTestingAppuim() throws MalformedURLException, InterruptedException {
//		// Setting up desire caps using DesireCapabilities class
		DesiredCapabilities desireCaps = new DesiredCapabilities();
//
		desireCaps.setCapability(MobileCapabilityType.AUTOMATION_NAME, "UIAutomator2");
		desireCaps.setCapability(MobileCapabilityType.APP,
				"C:\\Users\\white\\eclipse-workspace\\FirstAppiumProject\\src\\main\\java\\utils\\ApiDemos-debug.apk");
		desireCaps.setCapability(MobileCapabilityType.PLATFORM_NAME, "Android");
		desireCaps.setCapability(MobileCapabilityType.DEVICE_NAME, "Pixel API 29");

		// Setting up desire capability using UiAutomator
		UiAutomator2Options options = new UiAutomator2Options();
		// Set capabilities
		options.setDeviceName("Pixel API 29");
		options.setApp(
				"C:\\Users\\white\\eclipse-workspace\\FirstAppiumProject\\src\\main\\java\\utils\\ApiDemos-debug.apk");

		Thread.sleep(2000);

		AndroidDriver driver = new AndroidDriver(new URL("http://127.0.0.1:4723"), desireCaps);
//		AndroidDriver driver = new AndroidDriver(new URL("http://127.0.0.1:4723"), options);
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));
//
		driver.findElement(AppiumBy.accessibilityId("Preference")).click();
		
		//driver.findElement(By.xpath("//android.widget.TextView[@content-desc='6. Advanced preferences']")).click();
		
		driver.findElement(AppiumBy.accessibilityId("3. Preference dependencies")).click();
		driver.findElement(AppiumBy.id("android:id/checkbox")).click();
		
		driver.findElement(By.xpath("(//android.widget.RelativeLayout)[2]")).click();
		String alertText = driver.findElement(AppiumBy.id("android:id/alertTitle")).getText();
//
//		// Pass value to edit text
		driver.findElement(By.id("android:id/edit")).sendKeys("Ward");
		driver.findElements(AppiumBy.className("android.widget.Button")).get(1).click();
		Assert.assertEquals(alertText, "WiFi settings");
		System.out.println(alertText);
//		
	}

}

```

### The Result
<img src="img/img1.gif" />