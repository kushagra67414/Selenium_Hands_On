### Build an automation script for searching the article and validate the searching of the article

## Script:

```
package test_Auto_1;

import java.util.ArrayList;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class Test4 {

	
	public static void main(String[] args) {

		// System Property for Chrome Driver
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\Dell\\Desktop\\New\\Semester-6\\Test Automation\\Chrome_Driver_89\\chromedriver.exe");
		WebDriver driver=new ChromeDriver();
		// Launch Website
		driver.manage().window().maximize();
		System.out.println("1");
		driver.get("https://www.amazon.in/");
		
		WebElement searchbox = driver.findElement(By.id("twotabsearchtextbox"));
		searchbox .sendKeys("Samsung M21");
		WebElement searchbutton = driver.findElement(By.id("nav-search-submit-button"));
		searchbutton.click();
		
		
		driver.findElement(By.partialLinkText("Samsung Galaxy M21 (Raven Black, 4GB RAM, 64GB Storage)")).click();
		
		ArrayList<String> noOftabs = new 	ArrayList<String>(driver.getWindowHandles());
		System.out.println("No of tbs" +  noOftabs);
		
		driver.switchTo().window(noOftabs.get(1));
		
		WebElement store = driver.findElement(By.id("bylineInfo"));
		System.out.println(store.isDisplayed());
		
		WebElement store1= driver.findElement(By.id("AMAZON_DELIVERED"));
		System.out.println(store1.isDisplayed());
//		
		driver.switchTo().window(noOftabs.get(0));
		WebElement searchbox1 = driver.findElement(By.id("twotabsearchtextbox"));
		searchbox1.sendKeys("Samsung A21");
		WebElement searchbutton1 = driver.findElement(By.id("nav-search-submit-button"));
		searchbutton1.click();
		
		
		driver.close();	
		
	
	}
}

```

## Output: 

```
1
No of tbs[CDwindow-623FA3920FD2494633EFBBD9F68119B8, CDwindow-543367E871BAC92070240E5D493F8F20]
true
true

```
