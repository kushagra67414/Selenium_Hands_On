## Execute automation script developed on Chrome and Firefox browsers

### Script for Chrome Browser =?

```
package test_Auto_1;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class Exp_7 {

    public static void main(String[] args) {

          System.setProperty("webdriver.chrome.driver", "C:\\Users\\Dell\\Desktop\\New\\Semester-6\\Test Automation\\Chrome_Driver_89\\chromedriver.exe");

          WebDriver driver=new ChromeDriver();  

          driver.navigate().to("https://www.amazon.in/");  

          WebElement helloSignIn = driver.findElement(By.id("nav-link-accountList-nav-line-1"));
          helloSignIn.click();
          
          WebElement loginID = driver.findElement(By.id("ap_email"));
          loginID.sendKeys("8755210395");
          loginID.submit();
          
          WebElement password = driver.findElement(By.id("ap_password"));
          password.sendKeys("********");
          password.submit();
          

    }

}

```

### Output

![image](https://user-images.githubusercontent.com/46487696/114360941-39f83e00-9b93-11eb-8b7f-08de02cab67a.png)

![image](https://user-images.githubusercontent.com/46487696/114360950-3cf32e80-9b93-11eb-8dc6-1cb50bb59a5f.png)

![image](https://user-images.githubusercontent.com/46487696/114360957-3fee1f00-9b93-11eb-9410-e3765624c159.png)

![image](https://user-images.githubusercontent.com/46487696/114360967-42e90f80-9b93-11eb-8a6c-9f4749d39ae6.png)

![image](https://user-images.githubusercontent.com/46487696/114360977-454b6980-9b93-11eb-88cf-06591e16a9c6.png)

![image](https://user-images.githubusercontent.com/46487696/114360984-47adc380-9b93-11eb-9afa-e82b77cd08b6.png)



## B. Script for FireFox Browser 

```
package test_Auto_1;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.firefox.FirefoxDriver;

public class Exp_7 {

    public static void main(String[] args) {

          System.setProperty("webdriver.gecko.driver", "C:\\Users\\Dell\\Desktop\\New\\Semester-6\\Test Automation\\Firefox_Driver\\geckodriver.exe");

          WebDriver driver=new FirefoxDriver();  

          driver.navigate().to("https://www.amazon.in/");  

          WebElement helloSignIn = driver.findElement(By.id("nav-link-accountList-nav-line-1"));
          helloSignIn.click();
          
          WebElement loginID = driver.findElement(By.id("ap_email"));
          loginID.sendKeys("8755210395");
          loginID.submit();
          
          WebElement password = driver.findElement(By.name("password"));
          password.sendKeys("Aaaaaaaa@121");
          password.submit();
          
          WebElement password1 = driver.findElement(By.id("signInSubmit"));
          password1.click();
          	
          

    }

}

```

### Outputs

![image](https://user-images.githubusercontent.com/46487696/114361090-66ac5580-9b93-11eb-8be9-96cf9fe678b1.png)

![image](https://user-images.githubusercontent.com/46487696/114361106-69a74600-9b93-11eb-9b86-4d4062a2c852.png)

![image](https://user-images.githubusercontent.com/46487696/114361124-6ca23680-9b93-11eb-98ec-279b35b71008.png)
