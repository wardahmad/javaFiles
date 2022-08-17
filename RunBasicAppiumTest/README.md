### Run a Basic Appium Test

### Steps for installation and configuration :

* Download and install Appium-Server-GUI(appium-esktop)
* Download and install android studio
* Download Eclipse
* Download and install -inspector-main
* Download and install java jdk
* Setup System Environment variables
	* Java home sdk
	* Android Home
	* Platform tool
	* Build tool
	* tool
* Check setup via below commands
	* Java -version
	* adb devices

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
		// Setting up desire capability using UiAutomator
		UiAutomator2Options options = new UiAutomator2Options();
		// Set capabilities
		options.setDeviceName("Pixel API 29");
		options.setApp(
				"C:\\Users\\white\\eclipse-workspace\\FirstAppiumProject\\src\\main\\java\\utils\\ApiDemos-debug.apk");

		Thread.sleep(2000);
		AndroidDriver driver = new AndroidDriver(new URL("http://127.0.0.1:4723"), options);	
	}

}

```

### The Result
<img src="img/img1.gif" />