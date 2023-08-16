<p align="center">
<img src="https://github.com/kura-labs-org/kuralabs_deployment_1/blob/main/Kuralogo.png">
</p>
<h1 align="center">C4_deployment-1.1<h1> 

Demonstrate your ability to run a Jenkins build and manually deploy to Elastic Beanstalk.

- Step #1 Plan Deployment and Map it out in Draw.io
- Step #2 Upload Repository to GitHub
- Step #3 and Step #4:  Use Jenkins to Auto-Build and Auto:Test Application:  Successful
- Step #5:  Download Repository from GitHub, unzip file and re-zip file
- Step #6:  Create AWS Roles and Deploy Application on AWS Elastic Beanstalk
-     1st Attempt: Health Status:  Degraded
-       Debugging Process:
-           1. Downloaded 1st 100 lines of the log
-           2.  Searched for "Error" in the log and it contained in the "/var/log/web.stdout.log" section
-           3. Copied "/var/log/web.stdout.log" to ChatGPT to Explan AWS Log:
-           4.  Per ChatGPT, main issue is:  ModuleNotFoundError: No module named 'application...Make sure the application module is correctly named"
            5.  Renameed the app.py to application.py, rezip content
            6.  Reload Files and Re-Deployed Applicaition on AWS Elastic Beanstalk
                  2nd Attempt: Health Status:  Ok
-  Step #7:  URL, http://url-shortener-env.eba-av38k5ye.us-east-1.elasticbeanstalk.com/, successfully Loaded              
            
## Deployment instructions Link:
-  Link to instructions: https://github.com/kura-labs-org/C4_deployment-1.1/blob/main/Deployment-instructions.md
