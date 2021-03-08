## Login Page Script

### Code:

```
package test_Auto_1;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class test1 {

	public static void main(String[] args) {

		// System Property for Chrome Driver
		System.setProperty("webdriver.chrome.driver", "C:\\Users\\Dell\\Desktop\\New\\Semester-6\\Test Automation\\Chrome_Driver_89\\chromedriver.exe");
		WebDriver driver=new ChromeDriver();

		
	driver.manage().window().maximize();
	
		
	driver.get("https://www.amazon.in/");
	
	WebElement signinbutton = driver.findElement(By.id("nav-link-accountList-nav-line-1"));
	
	signinbutton.click();
	

	
	WebElement emialbutton = driver.findElement(By.id("ap_email"));
	emialbutton.sendKeys("dpskus8074@gmail.com");
	emialbutton.submit();

	driver.findElement(By.className("a-checkbox"));
	
	WebElement pssbutton = driver.findElement(By.id("ap_password"));
	pssbutton.sendKeys("Aaaaaaaa@121");
	pssbutton.submit();
}
	
}

```

