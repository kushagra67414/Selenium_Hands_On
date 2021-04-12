## Use the data driven test automation framework to parameterize the data using data from an Excel Sheet.

### Script =>

```
package parameters;

import java.io.FileInputStream;
import java.io.IOException;
import org.apache.poi.xssf.usermodel.XSSFRow;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;


public class ExcelUtil2 {
    
    static WebDriver driver;
    
    void setup() {
        System.setProperty("webdriver.chrome.driver","C:\\Users\\Dell\\Desktop\\New\\Semester-6\\Test Automation\\Chrome_Driver_89\\chromedriver.exe");
    }
    
     void checkLogin(String username, String pw) {
    	 driver=new ChromeDriver();
    	 driver.get("https://www.amazon.in/");
    	 driver.manage().window().maximize();
    	 System.out.println("1");
    	 WebElement signin = driver.findElement(By.id("nav-link-accountList-nav-line-1"));
    	 signin.click();

    	 WebElement email = driver.findElement(By.id("ap_email"));
    	 email.sendKeys(username);

    	 WebElement continu = driver.findElement(By.id("continue"));
    	 continu.click();

    	 WebElement pswd = driver.findElement(By.id("ap_password"));
    	 pswd.sendKeys(pw);

    	 WebElement signin1 = driver.findElement(By.id("signInSubmit"));
    	 signin1.click();
      
    
    }

    public static void main(String[] args) throws IOException {
        
        
        (new ExcelUtil2()).setup();
        
       
            
                FileInputStream file= new FileInputStream("C:\\Users\\Dell\\Desktop\\New\\Semester-6\\Test Automation\\TestData.xlsx");
    
                XSSFWorkbook wb = new XSSFWorkbook(file);
    
                XSSFSheet sheet= wb.getSheet("Login");
                String username,password;
    
                            
                for(int count = 1;count <= sheet.getLastRowNum(); count++ ){
        			
                	XSSFRow row = sheet.getRow(count);
                	username=row.getCell(0).toString();
                	password=row.getCell(1).toString();
      				
                  System.out.println("Username: " + username);
                  System.out.println("Password: " + password);
        			
        			
        			(new ExcelUtil2()).checkLogin(username,password);
        			System.out.println("Test successful");
        		}
                          
    }

}

```

### Excel Sheet Format =>

![image](https://user-images.githubusercontent.com/46487696/114361509-d3275480-9b93-11eb-9594-c293130ade3f.png)


### Outputs

![image](https://user-images.githubusercontent.com/46487696/114361542-dde1e980-9b93-11eb-8957-d68d846f1e3c.png)

![image](https://user-images.githubusercontent.com/46487696/114361553-dfabad00-9b93-11eb-9df6-6295a2a00247.png)

![image](https://user-images.githubusercontent.com/46487696/114361564-e2a69d80-9b93-11eb-8dc0-68ccbaa0597f.png)

![image](https://user-images.githubusercontent.com/46487696/114361576-e4706100-9b93-11eb-9e31-25ed0483b097.png)
