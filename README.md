<p align="center">
<img src="https://github.com/kura-labs-org/kuralabs_deployment_1/blob/main/Kuralogo.png">
</p>
<h1 align="center">C4_deployment-1.1<h1> 

Demonstrate your ability to run a Jenkins build and manually deploy to Elastic Beanstalk.

## Deployment Instructions:
1. Log into the instructor's Jenkins server
   
	a. Login using provided credentials

2. Create and run a Jenkins build for the application (Review Jenkins setup lesson video)
   
	a.Select new item

	b.Name your item (Follow naming convention)

	c.Select pipeline and click ok

	Next page

	d.Put in description

	e.Pipeline dropdown select "pipeline script from SCM"

		*In SCM select Git
   		*Repository URL copy/paste your GitHub, repository, HTTPS url (Make sure to select the correct repository)
   
			click add and select Jenkins
   				Username of GitHub account
   				Password (use generated token)
   					Generate token in GitHub
   					Settings, Developer settings
   					click personal access token (classic)
   					click Generate new token
   						Name token
   						click on repo and admin:repo_hook
   						click Generate token
   					Copy your token and save it, as it is visible one time
   					ID: name_it
   					description: put what it is
   					click add
   
			Click the dropdown and select credentials
   
			Change branch to build to main
   
			click Apply
   
			click Save
   
	f.Click build now
		
3. Make sure you include your name and the number 1.1 in your build's name (first name_letter of last name_1.1)

4. Observe the pipeline stages via the console output and document what occurred
	Stage Log Used credentials, Deploy 1, to access remote Git Repository Cloned the repository and checked the access

	Build - Run shell script to check Python installed Checked requirements to see if PIP is installed and the correct version Found version 22.0.2 and uninstalled it. Downloaded and installed 23.2.1 py

	Test - Run Shell script to test Python using py.test and return the results, pass the test

5. If the pipeline is successful, download the application files from your repository and proceed to the next step:

https://scribehow.com/shared/How_to_Create_and_Deploy_a_Python_URL_Shortener_on_AWS_Elastic_Beanstalk__MS9pB8lfRaGFiKAq2FU-cw

6. Once you deploy, your deployment to elastic beanstalk will fail or you will see a degraded health status

  ![image](https://github.com/andmulLABS01/Deployment_1.1AM/blob/main/ELB_status-1_1a.PNG)
   
7. Navigate to the elastic beanstalk log tab and request the last 100 logs. Download and view  the logs

   a. Requested logs and found the error
   ![image](https://github.com/andmulLABS01/Deployment_1.1AM/blob/main/ELB_status-1_1error.PNG)
   
9. Use the internet or ChatGPT to assist you in discovering the issue.

    a. The error is caused by the application.py file being named incorrectly app.py
   	Fixed the issue by

   		-renaming file in Git Repository (Future in case anyone downloads the file) and in the local zip file

   		-Next, you need to upload the new files to ELB and change the version

   		-Finally, redeploy the instance		

    ![image](https://github.com/andmulLABS01/Deployment_1.1AM/blob/main/ELB_status-1_1b.PNG)
10. **HINT:** The issue is located in the /var/log/web.stdout.log section


 ![image](https://github.com/andmulLABS01/Deployment_1.1AM/blob/main/Depoyment1_1.drawio.png)
