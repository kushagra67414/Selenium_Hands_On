## Basic Struture to start a Automated script

Code:

```
package test_Auto_1;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class Test2 {

public static void main(String[] args) {

// System Property for Chrome Driver
System.setProperty("webdriver.chrome.driver", "C:\\Users\\Dell\\Desktop\\New\\Semester-6\\Test Automation\\Chrome_Driver_89\\chromedriver.exe");
WebDriver driver=new ChromeDriver();
// Launch Website
driver.manage().window().maximize();
System.out.println("1");

driver.get("https://www.amazon.in/");
WebElement element2 = driver.findElement(By.id("twotabsearchtextbox"));
element2.sendKeys("bjanks");

WebElement searchbutton = driver.findElement(By.id("nav-search-submit-button"));
searchbutton.click();

 }
}

```
