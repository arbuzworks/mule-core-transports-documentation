# Github Connector

[Purpose](#purpose)
[Prerequisites](#prerequisites)    
[Step 1: Prepare database](#step-1-install-mule-github-connector-from-update-site)    
[Step 2: Create Demo Project](#step-2-create-demo-project)   
[Step 3: Configure Github Cloud Connector](#step-3-configure-github-cloud-connector)  
[Step 4: Create createRepository flow](#step-4-create-createrepository-flow)  
[Step 5: Run project](#step-5-run-project)   
[Step 6: Test createRepository flow](#step-6-test-createrepository-flow)    
[Step 7: Create createIssue flow](#step-7-create-createissue-flow)     
[Step 8: Test createIssue flow](#step-8-test-createissue-flow)   
[Step 9: Create createComment flow](#step-9-create-createcomment-flow)   
[Step 10: Test createComment flow](#step-10-test-createcomment-flow)   
[Step 11: Create editComment flow](#step-11-create-editcomment-flow)   
[Step 12: Test editComment flow](#step-12-test-editcomment-flow)   
[Other Resources](#other-resources)     

### Purpose

This document provides detailed instructions on how to install MuleSoft's Github connector and demonstrates how to build and run a simple demo application that uses this connector.

### Prerequisites

In order to build and run this project you'll need:

*   [Github account](https://github.com/).   
*   [MuleStudio](http://www.mulesoft.org/download-mule-esb-community-edition).  
*   Web browser.  

### Step 1: Install Mule Github Connector From Update Site

*   In Mule Studio select Help > Install New Software....   
*   Select MuleStudio Cloud Connectors Update Site in Work With drop-down.   
*   Find Github Connector Mule Studio Extension by typing a word Github in filter string and click Next.  
*   Follow installation steps.  

![Install Mule Github Connector From Update Site](images/step1-1.png) 

### Step 2: Create Demo Project

*    Run Mule Studio and select **File \> New \> Mule Project** menu item.  
*    Type **demo** as a project name and click **Next**.  

![Create Demo project](images/step2-1.png)

*    Then click **Next**.

![Create Demo project](images/step2-2.png)

*    And finally click **Finish**.

![Create Demo project](images/step2-3.png)

### Step 3: Configure Github Cloud Connector

Open **flows/demo.mflow** file. For configuration of GitHub Cloud Connector select **Global Elements** tab, click **Create** button and using the filter find and select  **GitHub Cloud Connector**. Click **OK**. You will see a window for **GitHub Cloud Connector** configuration, adjust the fields as it displayed on the following image.  

![Configure Github Cloud Connector](images/step3-1.png)

### Step 4: Create createRepository flow

*    Switch to the **Message Flow** tab in the flow editor.   
*    Add a new flow by dragging it from the Palette.    
*    Double click the new flow to open its properties and rename it to **createRepository**. Click **OK**.   

![Create createRepository flow](images/step4-1.png) 

*    Drag **HTTP Endpoint** to the flow. Double click it to show its properties and adjust them as it displayed on the following image.   

![Create createRepository flow](images/step4-2.png) 

*    Find and drag **GitHub** Cloud Connector to the flow. Double click it to show its properties. Set **Display name** as **GitHub. Create repository**. Adjust rest of the fields as it shown on the following image. 

![Create createRepository flow](images/step4-3.png) 

*    Save the flow. 

### Step 5: Run project

*    Right Click **src/main/app/demo.xml \> Run As/Mule Application**.

![Run Project](images/step5-1.png) 

*    Check the console to see when the application starts.  

You should see a log message on the console:  
 
    ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++    
    + Started app 'demo'                                       +    
    ++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++   

### Step 6: Test createRepository flow

*    Once the application is started, open your browser and point it to [http://localhost:8081/createrepo](http://localhost:8081/createrepo).   
*    Then log on GitHub using your credentials. Find **Repositories** tab and click on it, you should see a page showing you newly created repository.  

![Test createRepository flow](images/step6-1.png) 

*    Stop Mule server. 

### Step 7: Create createIssue flow

*    Add a new flow by dragging it from the Palette.    
*    Double click the new flow to open its properties and rename it to **createIssue**. Click **OK**.   
*    Then drag **HTTP Endpoint** to the flow. Double click it to show its properties and adjust them as it displayed on the following image.    

![Create createIssue flow](images/step7-1.png) 

*    Find and drag **GitHub** Cloud Connector to the flow. Double click it to show its properties. Set **Display name** as **GitHub. Create issue**. Adjust rest of the fields as it shown on the following image. Put whatever text you want in the **Body** field; type in the name of repository you have just created in the **Repository** field; name issue using **Title** field.    

![Create createIssue flow](images/step7-2.png) 

### Step 8: Test createIssue flow

*    Run mule application.  
*    Once the application is started, open your browser and point it to [http://localhost:8081/createissue](http://localhost:8081/createissue).   
*    Switch to your previously opened page on **GitHub**. Find **Contributions** tab and click on it, you should see something like that ![new issue](images/new_issue.png) at the bottom of the page. Number standing before the issue title is an issue id.  Then click on the issue title, you should see page with your issue open. Notice, that issue body contains the same text you have input in the **Body** field.    

![Test createIssue flow](images/step8-1.png) 

*    Stop Mule server.  

### Step 9: Create createComment flow

*    Add a new flow by dragging it from the Palette.    
*    Double click the new flow to open its properties and rename it to **createComment**. Click **OK**.   
*    Then drag **HTTP Endpoint** to the flow. Double click it to show its properties and adjust them as it displayed on the following image.    

![Create createComment flow](images/step9-1.png) 

*    Find and drag **GitHub** Cloud Connector to the flow. Double click it to show its properties. Set **Display name** as **GitHub. Create comment**. Adjust rest of the fields as it shown on the following image. Name comment using **Comment** field; put issue id in the **Issue Id** field; type in the name of repository you have just created in the **Repository** field. 

![Create createComment flow](images/step9-2.png) 

### Step 10: Test createComment flow

*    Run mule application.  
*    Once the application is started, open your browser and point it to [http://localhost:8081/createcomment](http://localhost:8081/createcomment).   
*    Switch to your previously opened page on **GitHub** and refresh it. You should see new comment.     

![Test createComment flow](images/step10-1.png) 

*    Stop Mule server.  

### Step 11: Create editComment flow

*    Add a new flow by dragging it from the Palette.    
*    Double click the new flow to open its properties and rename it to **editComment**. Click **OK**.   
*    Then drag **HTTP Endpoint** to the flow. Double click it to show its properties and adjust them as it displayed on the following image.    

![Create editComment flow](images/step11-1.png) 

*    Find and drag **GitHub** Cloud Connector to the flow. Double click it to show its properties. Set **Display name** as **GitHub. Edit comment**. Adjust rest of the fields as it shown on the following image. Type in the name of repository you have just created in the **Repository** field; put comment id in the **Comment Id** field (it may be found by clicking on comment icon - ![comment icon](images/comment_icon.png) switching to the previously opened page on GitHub, then in the address line find something similar to ```1#issuecomment-25231286```, that long number is a required comment id); put in the **Body** field new text for the comment.

![Create editComment flow](images/step11-2.png) 

### Step 12: Test editComment flow

*    Run mule application.  
*    Once the application is started, open your browser and point it to [http://localhost:8081/editcomment](http://localhost:8081/editcomment).   
*    Switch to your previously opened page on **GitHub** and refresh it. You should see comment with new text.     

![Test editComment flow](images/step12-1.png) 

### Other Resources

For more information on:

- Mule AnyPoint® connectors, please visit [http://www.mulesoft.org/connectors](http://www.mulesoft.org/connectors)
- Mule platform and how to build Mule apps, please visit [http://www.mulesoft.org/documentation/display/current/Home](http://www.mulesoft.org/documentation/display/current/Home)


