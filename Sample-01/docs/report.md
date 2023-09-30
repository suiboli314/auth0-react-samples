# Setting up Twilio and Auth0 to React-App

## Setting up Auth0 Account 

If you don't have one, you can register for free https://auth0.com/signup

1. Go to Application Section

2. Create Application
  - For this project, choose Single Page Web App.
    There will be error for Regular Web Application for the project.

3. Into the Application Settings
  - in Basic Information, copy Domain and Client ID to auth_config.json

  ![Athu0](./images/auth0Setting.heic)

4. Setting Up API URL
  - For local development, setting Allowed Callback URLs, Allowed Logout URLs, Allowed Web Origins to https://localhost:3000

  ![APIURL](./images/APIURL.heic)

5. Test App
  - run `yarn install` and `yarn dev`
    ![test1](./images/test1.heic)
  - click Login
    ![login](./images/Login.heic)
  - after signup, login and accept authentication
    ![accpetAuth](./images/AcceptAuthentication.heic)
  - successfully login
    ![successfullyLogin](./images/AfterLogin.heic)
  
## Setting Up MFA with Twilio

If you don't have one, you can register for free. Verify SMS while signup and select SMS service for web app.

1. Getting Start to get a number, and copy SID, Auth Token, phone number
  ![TwilioSetting](./images/TwilioSetting.heic)
  ![MFA/SMS](./images/MFA:SMS.heic)

2. restart web app and click login, and will see the phone verification
  ![phone](./images/phone.heic)
  ![getCode](./images/getCode.heic)
  Only the verified phone number could receive the code, and you will successfully login
  ![test2](./images/test2.heic)

## Conclusion
The integration of Auth0 and Twilio with a React application provides a robust authentication and multifactor authentication (MFA) solution. By following the steps mentioned, we can set up an Auth0 account, ensuring that the right settings are in place for our Single Page Web App. It is crucial to remember to use the correct settings for local development and to test the application thoroughly to verify proper login functionality.

I met issue with by using presetting traditional web app in Auth0. It could be fixed to
set application as single page web app.

Furthermore, setting up MFA with Twilio offers an additional layer of security. It requires users to verify their identity using an SMS code sent to their phone, ensuring that even if someone knows a user's password, they won't be able to access the account without the verification code.

In today's digital age, security is paramount. Incorporating authentication mechanisms like Auth0, combined with MFA solutions such as Twilio, can significantly improve the security posture of your React application. This tutorial provides a straightforward roadmap to achieving this.
