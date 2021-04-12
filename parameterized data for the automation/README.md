##  Implement the parameterized data for the automation script build in starting

## Script =>

1. Script for calling Parameter.

```
package dataprov;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.*;
import org.testng.annotations.BeforeTest;
import org.testng.annotations.Test;

import dataprov.Two;


public class One {
	
	String baseurl = "https://www.amazon.in/";
	WebDriver chromeDriver ;
	
	@BeforeTest
	public void launchbrowser() {
	
		String driverpath = "C:\\Users\\Dell\\Desktop\\New\\Semester-6\\Test Automation\\Chrome_Driver_89\\chromedriver.exe";
		System.setProperty("webdriver.chrome.driver", driverpath);
		chromeDriver = new ChromeDriver();
		
	}
	
	
	
	
	@Test(dataProviderClass = Two.class, dataProvider= "sample")
	public void fa(String name, String value) {	
		
		chromeDriver.get(baseurl);
		chromeDriver.manage().window().maximize();	
		WebElement signinbutton1 = chromeDriver.findElement(By.id("nav-link-accountList-nav-line-1"));
		
		signinbutton1.click();
		WebElement email = chromeDriver.findElement(By.id("ap_email"));
		email.sendKeys(name);
		email.submit();
		
		WebElement password = chromeDriver.findElement(By.id("ap_password"));
		password.sendKeys(value);
		password.submit();
		

		WebElement All = chromeDriver.findElement(By.xpath("//*[@id=\"nav-hamburger-menu\"]/span"));
		All.click();
		
		WebElement Sign_Out = chromeDriver.findElement(By.xpath("//*[@id=\"hmenu-content\"]/ul[1]/li[29]/a"));
		Sign_Out.click();
	 

		System.out.println("Name   "  +  name);		
		System.out.println("Value  "  +  value);
	  }

//	@AfterSuite
//	public void Endsession() {
//		
//		chromeDriver.close();
//	}
	
	
}
```

2. Script for Passing parameter =>

```
package dataprov;
import org.testng.annotations.Test;
import org.testng.annotations.DataProvider;
public class Two {  
  private static String name;
  private static String value;

@DataProvider(name="sample")
  public static Object[][] dp() {
	  
    Object[][] data = new Object[2][2];
  data[0][0] = "dpskus8074@gmail.com";
  data[0][1] = "Aaaaaaaa@121";
 
  data[1][0] = "8954232111";
  data[1][1] = "Manju@121";
  
return data;
}
@DataProvider(name="sample1") 
public static Object[][] negativedp(){
	Object data2[][] = new Object[2][2];
	return data2;
}
}
```

## A. By First Parameter

![image](https://user-images.githubusercontent.com/46487696/114360430-a3c41800-9b92-11eb-8f6e-25c62bceca87.png)

![image](https://user-images.githubusercontent.com/46487696/114360438-a6267200-9b92-11eb-9688-3e7ad56ccb8f.png)

![image](https://user-images.githubusercontent.com/46487696/114360473-b2aaca80-9b92-11eb-9d45-a07381670ca8.png)

![image](https://user-images.githubusercontent.com/46487696/114360488-b50d2480-9b92-11eb-8332-98efd963c7d4.png)



# B. By Second Parameter

![image](https://user-images.githubusercontent.com/46487696/114360552-c7875e00-9b92-11eb-9384-a263802770df.png)

![image](https://user-images.githubusercontent.com/46487696/114360561-ca824e80-9b92-11eb-811b-b1d821152081.png)

![image](https://user-images.githubusercontent.com/46487696/114360569-cd7d3f00-9b92-11eb-9087-752f589e5972.png)

