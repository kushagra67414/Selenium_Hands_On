## Integrate extent report with automation scripts for result reporting.

Script =>

```
package test_Auto_1;

import org.testng.annotations.Test;
import java.lang.reflect.Method;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.BeforeClass;
import org.testng.annotations.BeforeMethod;
import org.testng.annotations.*;
import org.testng.annotations.Test;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.chrome.ChromeDriver;
import com.relevantcodes.extentreports.ExtentReports;
import com.relevantcodes.extentreports.ExtentTest;
import com.relevantcodes.extentreports.LogStatus;


public class Report2 {

	static ExtentReports report;
	static ExtentTest test;
	
	WebDriver driver;
	String baseurl="https://www.amazon.in/";
	String driverpath="C:\\\\Users\\\\Dell\\\\Desktop\\\\New\\\\Semester-6\\\\Test Automation\\\\Chrome_Driver_89\\\\chromedriver.exe";
	
	@BeforeClass
	public void initReport(){
		report = new ExtentReports("C:\\\\Users\\\\Dell\\\\Desktop\\\\New\\\\Semester-6\\\\Test Automation\\\\Report Results\\\\result.html");
	}
	
	@BeforeTest
	public void launchBrowser(){
		System.setProperty("webdriver.chrome.driver",driverpath);
		driver=new ChromeDriver();
		driver.get(baseurl);
		driver.manage().window().maximize();
	}
	
	@BeforeMethod
	public static void startReport(Method result){
		test = report.startTest("Extent Report - "+result.getName());
	}
	
	@AfterMethod
	public void endReport(){
		report.endTest(test);
		report.flush();
	}
	
	@Test(priority=0)
	public void clickSignin(){
		driver.findElement(By.id("nav-link-accountList-nav-line-1")).click();
		
		test.log(LogStatus.INFO, "Starting login");
		
		if(driver.findElement(By.id("ap_email"))!=null){
			test.log(LogStatus.PASS, "Email input box present");
		}
		else{
			test.log(LogStatus.FAIL, "Email input box absent");
		}
		
		
		test.log(LogStatus.WARNING, "Moving to next step");
	}
	
	@Test(priority=1)
	public void enterUsername(){
		
		driver.findElement(By.id("ap_email")).sendKeys("dpskus8074@gmail.com");
		
		if(driver.findElement(By.id("ap_email")).getAttribute("value").equals("dpskus8074@gmail.com")){
			test.log(LogStatus.PASS, "Entered email successfully");
		}
		else{
			test.log(LogStatus.FAIL, "Couldn't enter email");
		}
		test.log(LogStatus.WARNING, "Moving to next step");
		
		System.out.println(test.log(LogStatus.WARNING, "Moving to next step"));
	}
	
	@Test(priority=2)
	public void clickContinue(){
		
		WebElement btn=driver.findElement(By.id("continue"));
		if(btn!=null && btn.isEnabled()){
			test.log(LogStatus.PASS, "Email submit button present and Enabled");
			driver.findElement(By.id("continue")).click();
		}
		else{
			test.log(LogStatus.FAIL, "Email submit button absent or Disabled");
		}
		
		test.log(LogStatus.WARNING, "Moving to next step");
	}
	
	@Test(priority=3)
	public void enterPassword(){
		
		driver.findElement(By.id("ap_password")).sendKeys("Aaaaaaaa@121");
		
		if(!driver.findElement(By.id("ap_password")).getAttribute("value").equals("")){
			test.log(LogStatus.PASS, "Entered password successfully");
		}
		else{
			test.log(LogStatus.FAIL, "Couldn't enter password");
		}
		test.log(LogStatus.WARNING, "Moving to next step");
	}
	
	@Test(priority=4)
	public void clickLogin(){
		WebElement btn=driver.findElement(By.id("signInSubmit"));
		
		if(btn!=null && btn.isEnabled()){
			test.log(LogStatus.PASS, "Email submit button present and Enabled");
			driver.findElement(By.id("signInSubmit")).click();
		}
		else{
			test.log(LogStatus.FAIL, "Email submit button absent or Disabled");
		}
		
		test.log(LogStatus.WARNING, "Login Successful");
	}
//	
//	@AfterTest	
//	public void destroySession(){
//		driver.close();
//	}
}

```

### Outputs =>

![image](https://user-images.githubusercontent.com/46487696/114362266-c48d6d00-9b94-11eb-85e5-a86c8114f6fa.png)

![image](https://user-images.githubusercontent.com/46487696/114362269-c7885d80-9b94-11eb-8960-881db5759e15.png)

![image](https://user-images.githubusercontent.com/46487696/114362281-c9eab780-9b94-11eb-91c0-38ecd23643ef.png)

![image](https://user-images.githubusercontent.com/46487696/114362289-cc4d1180-9b94-11eb-97b6-ed16dc4194d6.png)

![image](https://user-images.githubusercontent.com/46487696/114362301-ceaf6b80-9b94-11eb-8c33-10be44ee3fdc.png)

![image](https://user-images.githubusercontent.com/46487696/114362312-d0792f00-9b94-11eb-8fc5-fe1ee6cf4289.png)
