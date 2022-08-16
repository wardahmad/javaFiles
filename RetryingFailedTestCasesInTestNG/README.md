### Retrying Failed Test Cases in TestNG

### Source Code

### `ListenerTest` File
```Java
package iTestListenerANDIReportListener;

import org.testng.ITestContext;
import org.testng.ITestListener;
import org.testng.ITestResult;

public class ListenerTest implements ITestListener {
	@Override
	public void onFinish(ITestContext arg0) {
		// TODO Auto-generated method stub
	}

	@Override
	public void onStart(ITestContext arg0) {
		// TODO Auto-generated method stub
	}

	@Override
	public void onTestFailedButWithinSuccessPercentage(ITestResult arg0) {
		// TODO Auto-generated method stub
	}

	// When Test case get failed, this method is called.
	@Override
	public void onTestFailure(ITestResult Result) {
		System.out.println("The name of the testcase failed is :" + Result.getName());
	}

	// When Test case get Skipped, this method is called.
	@Override
	public void onTestSkipped(ITestResult Result) {
		System.out.println("The name of the testcase Skipped is :" + Result.getName());
	}

	// When Test case get Started, this method is called.
	@Override
	public void onTestStart(ITestResult Result) {
		System.out.println(Result.getName() + " test case started");
	}

	// When Test case get passed, this method is called.
	@Override
	public void onTestSuccess(ITestResult Result) {
		System.out.println("The name of the testcase passed is :" + Result.getName());
	}

}
```

### `TestCases` File
```Java
package iTestListenerANDIReportListener;

import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.edge.EdgeDriver;
import org.testng.Assert;
import org.testng.Reporter;
import org.testng.annotations.Listeners;
import org.testng.annotations.Test;

@Listeners(ListenerTest.class)
public class TestCases {

//Test to pass as to verify listeners.        
	@Test
	public void Login() {
		Reporter.log("Launching Edge Driver", true);
		System.setProperty("webdriver.chrome.driver",
				"C:\\Users\\white\\Desktop\\QA\\Auto\\chromedriver14\\chromedriver.exe");

		WebDriver driver = new ChromeDriver();
		driver.manage().window().maximize();
		driver.get("http://google.com");
		String title = driver.getTitle();
//		System.out.println(title);
		Assert.assertEquals(title, "Google");
		Reporter.log("Asserted the title of Google", true);
		driver.close();
	}

//Forcefully failed this test as verify listener.        
	@Test
	public void TestToFail() {
		System.out.println("This method to test fail");
		Assert.assertTrue(false);
	}
}
```

### `testng.xml` File
```Java
<!DOCTYPE suite SYSTEM "https://testng.org/testng-1.0.dtd">
<suite name="Test-NGSuite">
	<test name="TestNG">
		<classes>
			<class name="iTestListenerANDIReportListener.TestCases" />
		</classes>
	</test>
</suite>
```

### The Result
<img src="img/img1.gif" />