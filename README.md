<p align="center">
<img src="https://github.com/kura-labs-org/kuralabs_deployment_1/blob/main/Kuralogo.png">
</p>
<h1 align="center">Deployment-1.1:  Run a Jenkisn Build and Manually Deploy to Elastic Beanstalk<h1> 

- Step #1 Plan Deployment and Map it out in Draw.io
- Step #2 Upload Repository to GitHub
- Step #3 and Step #4:  Use Jenkins to Auto-Build and Auto:Test Application:  Successful
- Step #5:  Download Repository from GitHub, unzip file and re-zip file
- Step #6:  Create AWS Roles and Deploy Application on AWS Elastic Beanstalk
-     1st Attempt: Health Status:  Degraded
-       Debugging Process:
-           1. Downloaded 1st 100 lines of the log
-           2. Searched for "Error" in the log and it is contained in the "/var/log/web.stdout.log" section
-           3. Copied "/var/log/web.stdout.log" section to ChatGPT to Explain AWS Log:
-           4. Per ChatGPT, main issue is:  ModuleNotFoundError: No module named 'application...Make sure the application module is correctly named"
            5. Renamed the app.py to *application.py, rezip content
            6. Reload Files and Re-Deployed Applicaition on AWS Elastic Beanstalk
                  2nd Attempt: Health Status:  Ok
-  Step #7:  URL, http://url-shortener-env.eba-av38k5ye.us-east-1.elasticbeanstalk.com/, successfully Loaded
-  *This will cause an issue in the Test Stage of the Jenkins Build.  Test Stage imports an object called app from module app.py, once the module has been renamed from app.py to application.py if the Jenkins Build is reran, the Test stage will fail since the app.py file will no longer be found.  In order to resolve this, the code test_app.py needs to be updated from 'from app import app' to 'from application import app'
            
