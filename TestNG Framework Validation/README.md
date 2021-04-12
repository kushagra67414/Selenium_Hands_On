## Build an automation script for navigating to the article details page and validate all the details for an article using Test-NG framework


## Script =>

```
package test_Auto_1;

import org.testng.annotations.Test;
import org.testng.annotations.Test;
import org.testng.annotations.Test;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.*;
import org.testng.Assert;

public class Test8{
	
	
	String baseurl = "https://www.amazon.in/";
	String driverpath = "C:\\Users\\Dell\\Desktop\\New\\Semester-6\\Test Automation\\Chrome_Driver_89\\chromedriver.exe";
	WebDriver chromeDriver ;
	
	@BeforeTest
	public void launchbrowser() {
	
		System.setProperty("webdriver.chrome.driver", driverpath);
		chromeDriver = new ChromeDriver();
		chromeDriver.get(baseurl);
		chromeDriver.manage().window().maximize();	
	}
	
	@Test(priority=0)
	public void ClickonSearch() {
		
		WebElement searcharticle = chromeDriver.findElement(By.id("twotabsearchtextbox"));
		searcharticle.sendKeys("Iphone 12 pro");
		searcharticle.submit();
		WebElement clickable = chromeDriver.findElement(By.id("nav-search-submit-button"));
		clickable.click();
	}
	
	@Test(priority=1)
	public void verifytitleofsearch() {
		
		WebElement articletitle = chromeDriver.findElement(By.xpath("/html/body/div[1]/div[2]/div[1]/div/div[1]/div/span[3]/div[2]/div[2]/div/span/div/div/div/div/div[2]/div[2]/div/div[1]/div/div/div[1]/h2/a/span"));	
		String str = articletitle.getText();
		System.out.println(str);
		Assert.assertTrue(str.contains("New Apple iPhone 12 Pro (128GB) - Pacific Blue"));
	}
	
	@Test(priority=2)
	public void verifyPrice() {
		
		WebElement Price = chromeDriver.findElement(By.xpath("/html/body/div[1]/div[2]/div[1]/div/div[1]/div/span[3]/div[2]/div[2]/div/span/div/div/div/div/div[2]/div[2]/div/div[2]/div[1]/div/div[1]/div[1]/div/div/a/span/span[2]/span[2]"));
		String Inr = Price.getText();
		System.out.println(Inr);
		Assert.assertTrue(Inr.contains("1,19,990.00"));
	}

	
	
}

```

![image](https://user-images.githubusercontent.com/46487696/114359652-d3beeb80-9b91-11eb-9a80-452a6bdf01c3.png)

![image](https://user-images.githubusercontent.com/46487696/114359685-dae5f980-9b91-11eb-8d49-1d3f789547df.png)
