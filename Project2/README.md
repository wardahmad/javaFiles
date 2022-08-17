### Project 2

### Source Code
```Java
Actions actions = new Actions(driver);
		JavascriptExecutor js = (JavascriptExecutor) driver;
		Thread.sleep(2000);

		// ----search---- //
		// Type "Stars" in the search bar
		driver.findElement(By.xpath("//input[@aria-hidden='false']")).sendKeys("Stars");
		Thread.sleep(2000);

		// Click on the search button
		driver.findElement(By.xpath("//input[@value='Search']")).click();
		Thread.sleep(2000);

		// Click on the "Stars" Anchor Tag
		driver.findElement(By.xpath("//a[@href='https://www.nasa.gov/content/stars-and-galaxies/']")).click();
		Thread.sleep(2000);

		// Click on "The Sun" Anchor Tag
		driver.findElement(By.xpath("//a[@href='/sun']")).click();
		Thread.sleep(2000);

		// Declare WebElement - sun IMG
		WebElement divEle = driver.findElement(By.xpath("//div[@id='ember164']"));

		// Scroll Element into View
		actions.moveToElement(divEle).perform();
		Thread.sleep(2000);

		// New Window
		js.executeScript("window.open()");
		ArrayList<String> tabs = new ArrayList<String>(driver.getWindowHandles());
		Thread.sleep(5000);

		// Switch to a new tab
		driver.switchTo().window(tabs.get(1));
		String urlEle = "https://www.esa.int/Science_Exploration/Space_Science/Solar_Orbiter/The_Sun_as_you_ve_never_seen_it_before";
		driver.get(urlEle);
		Thread.sleep(2000);
		driver.findElement(By.xpath("//*[@id='cookie_loc']/div/a[1]")).click();
		Thread.sleep(2000);
		driver.close();

		// switch back control to old tab
		driver.switchTo().window(tabs.get(0));
		Thread.sleep(5000);

//		///////////////////////////////////////////////////////////////////////////////

		// ------------------------------------E-books--------------------------------------------

		/// Mai ///
		// Downloads
		driver.findElement(By.xpath("//span[contains(.,'Downloads')]")).click();
		Thread.sleep(2000);

		// E-book
		driver.findElement(By.xpath("//a[@href='/connect/ebooks/index.html']")).click();
		Thread.sleep(2000);

		// scroll down
		js.executeScript("scrollBy(0, 200)");

		// <div/> in the books Page
		driver.findElement(By.xpath("(//div[@class='bg-card-canvas'])[4]")).click();
		Thread.sleep(2000);

		// Nasalogo
		driver.findElement(By.xpath("//img[@src=\"/sites/all/themes/custom/nasatwo/images/nasa-logo.svg\"]")).click();
		Thread.sleep(2000);

		// ----------------------------------image------------------------------------------------

		// Galleries
		driver.findElement(By.xpath("//span[contains(.,'Galleries')]")).click();
		Thread.sleep(2000);

		// image of the day
		driver.findElement(By.xpath("//a[contains(.,'Image of the Day')]")).click();
		Thread.sleep(2000);

		// scroll down
		js.executeScript("scrollBy(0,5000)");

		// More image
		driver.findElement(By.xpath("//div[contains(@id,'trending')]")).click();
		Thread.sleep(2000);

		// Nasalogo
		driver.findElement(By.xpath("//img[@src=\"/sites/all/themes/custom/nasatwo/images/nasa-logo.svg\"]")).click();
		Thread.sleep(2000);

		// -------------------------------------------sound-------------------------------------------
		// Downloads
		driver.findElement(By.xpath("//span[contains(.,'Downloads')]")).click();
		Thread.sleep(2000);

		// AudioandRingtones
		driver.findElement(By.xpath("//a[@href='/connect/sounds/index.html']")).click();
		Thread.sleep(2000);

		// scroll down
		js.executeScript("scrollBy(0, 3550)");

		// sound
		WebElement sound = driver
				.findElement(By.xpath("//a[@href='http://www.nasa.gov/mp3/581097main_STS-1_Dust-it-Off.mp3']"));
		String soundURL = sound.getAttribute("href");
		Thread.sleep(2000);

		// New Window
		js.executeScript("window.open()");
		ArrayList<String> tabOne = new ArrayList<String>(driver.getWindowHandles());
		Thread.sleep(5000);

		// Switch to a new tab
		driver.switchTo().window(tabOne.get(1));
		driver.get(soundURL);
		Thread.sleep(10000);
		driver.close();

		// switch back control to old tab
		driver.switchTo().window(tabOne.get(0));
		Thread.sleep(2000);

		// Nasalogo
		driver.findElement(By.xpath("//img[@src='/sites/all/themes/custom/nasatwo/images/nasa-logo.svg']")).click();
		Thread.sleep(2000);

		// NASA Audiences
		driver.findElement(By.xpath("//span[contains(.,'NASA Audiences')]")).click();
		Thread.sleep(2000);

		// For Media
		driver.findElement(By.xpath("//a[@href='/news/media/info/index.html']")).click();
		Thread.sleep(2000);

		// NASA Live
		WebElement nasaLive = driver.findElement(By.xpath("(//a[contains(.,'NASA Live')])[2]"));
		actions.moveToElement(nasaLive).perform();
		Thread.sleep(8000);
```