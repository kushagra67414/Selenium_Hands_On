## Search Product And Validate


### Code =>
```
package test_Auto_1;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;


public class Test3 {

public static void main(String[] args) {

// System Property for Chrome Driver
	System.setProperty("webdriver.chrome.driver", "C:\\Users\\Dell\\Desktop\\New\\Semester-6\\Test Automation\\Chrome_Driver_89\\chromedriver.exe");
	WebDriver driver=new ChromeDriver();
// Launch Website
	driver.navigate().to("https://www.amazon.in/");
	driver.manage().window().maximize();


	WebElement element2 = driver.findElement(By.id("twotabsearchtextbox"));
	element2.sendKeys("mobile under 15000");
	element2.submit();
	
//	element2.sendKeys("mobile under 15000").submit();
	
	
//	driver.findElement(By.tagName("Oppo A31 (Fantasy White, 6GB RAM, 128GB Storage) with No Cost EMI/Additional Exchange Offers")).click();
	
	//*[@id="search"]/div[1]/div[2]/div/span[3]/div[2]/div[3]/div/span/div/div/div[2]/div[2]/div/div[1]/div/div/div[1]/h2/a/span/text()
	   
// driver.findElement(By.tagName("//*[@id=\"search\"]/div[1]/div[2]/div/span[3]/div[2]/div[3]/div/span/div/div/div[2]/div[2]/div/div[1]/div/div/div[1]/h2/a/span/text()"));
	driver.findElement(By.partialLinkText("Oppo A31 (Fantasy White, 6GB RAM, 128GB Storage)")).click();
	
  }
}

```
