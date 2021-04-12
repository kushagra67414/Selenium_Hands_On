## Integrate automation scripts with Jenkins for execution on build deployment.

### Script =>

```
package MAHI;

import static org.testng.Assert.assertNotNull;
import static org.testng.Assert.assertTrue;
import java.util.ArrayList;
import java.util.Set;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.AfterClass;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.Test;


public class NewTest1 {
	
WebDriver driver;

@BeforeClass
public void setUp() {
	System.out.println("*******************");
	System.out.println("launching chrome browser");
	
	System.setProperty("webdriver.chrome.driver", " C:\\\\\\\\Users\\\\\\\\Dell\\\\\\\\Desktop\\\\\\\\New\\\\\\\\Semester-6\\\\\\\\Test Automation\\\\\\\\Chrome_Driver_89\\\\\\\\chromedriver.exe");
	driver = new ChromeDriver();
	driver.get("https://www.amazon.in/");
	driver.manage().window().maximize();
}

@Test(priority=0)
public void Search_Field() {
	WebElement Search_field = driver.findElement(By.id("twotabsearchtextbox"));
	Search_field.sendKeys("Cricket leather bat");
	System.out.println("Test 1");
  
}

@Test(priority=1)
public void Click_Search() {
	
	WebElement Submit_search = driver.findElement(By.id("nav-search-submit-button"));
	Submit_search.click();
	System.out.println("Test 2");

}

@Test(priority=2)
public void Click_product() {
	
	JavascriptExecutor js1 = (JavascriptExecutor) driver;
	js1.executeScript("window.scrollBy(0,400)");
	
	WebElement Click_on_product = driver.findElement(By.xpath("//*[@id=\"search\"]/div[1]/div/div[1]/div/span[3]/div[2]/div[7]/div/span/div/div/span/a"));
	Click_on_product.click(); 
	System.out.println("Test 3");

}

@Test(priority=4)
public void switch_Validate()
{
	Set<String> listOfTabs = driver.getWindowHandles();
	  
	  ArrayList<String> arr = new ArrayList<String>(listOfTabs);
	  
	  driver.switchTo().window(arr.get(1));
	  
	  System.out.println("\nIn another window\n");
	  
	  WebElement Product_Description = driver.findElement(By.id("productTitle"));
	  String check = Product_Description.getText();
	  System.out.println("check " + check);
	  
	  assertNotNull(check);
	  assertTrue(check.contains("Kashmir Willow"));
	  
	  System.out.println("Validate successfully!");

	  
}

@AfterClass
public void tearDown() {
		System.out.println("Closing chrome browser");
		driver.quit();
}

}

```

## testng.xml

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE suite SYSTEM "https://testng.org/testng-1.0.dtd" >	
<suite name="sample" parallel="false">
<test name ="test">
<classes>
<class name="test_Auto_1.Myntra_Extent_Report"/>
</classes>
</test>
</suite>

```

### run.bat file 

```
set projectLocation=C:\Users\Dell\eclipse-workspace\test_Auto_1

cd %projectLocation%

set classpath=%projectLocation%\bin;%projectLocation%\lib\*

java org.testng.TestNG %projectLocation%\testng.xml

pause
```


### Location where to store the run.bat and testng.xml file

* Both file must be inside the project not inside any specific package name or folder.

![image](https://user-images.githubusercontent.com/46487696/114362808-61e8a100-9b95-11eb-9d86-e9c17dc84d46.png)



### Outputs

![image](https://user-images.githubusercontent.com/46487696/114362884-762c9e00-9b95-11eb-9339-b23b7d615c5f.png)


* Configure the jenkins by following below output =>


![image](https://user-images.githubusercontent.com/46487696/114362899-788ef800-9b95-11eb-8acc-7d982d64730f.png)

![image](https://user-images.githubusercontent.com/46487696/114362906-7a58bb80-9b95-11eb-9dc3-63748aee47fb.png)

![image](https://user-images.githubusercontent.com/46487696/114362922-7c227f00-9b95-11eb-9778-678fc499a130.png)
