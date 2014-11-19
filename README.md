Bootstrap an App with Constant Contact 
==========

a proof of concept for a kiosk app to add users to a mailing list or check them in at an event 

Hipchat room for tonights event: https://www.hipchat.com/gvNsQ0cJQ

==========
Steps for setting up the basic app :

The most recent version of these steps found here : http://slides.com/brian915/bootstrap-an-app-with-constant-contact--2

1) it will utilize AppConnect  - Constant Contact's Developer API
Developers will need to setup a Mashery Account to get an API key :

https://constantcontact.mashery.com/io-docs



# Setup
1. Clone your fork to your local machine.
2. cd Bootstrap-Kiosk-App/config/initializers/ 
3. mv _secret_tokens.rb.example _secret_tokens.rb
 (note this file is git-ignored so you don't accidently put your private keys on github)
4. cd ../../; bundle installl
5. Run 'rake secret' to generate a new rails secret key.
6. Paste this key into '_secret_tokens.rb' on the line: BootstrapKioskApp::Application.config.secret_key_base
7. Sign up for an API key through mashery:  https://constantcontact.mashery.com/
8. Create a new application by clicking API Keys, then Applications 
9. Make sure to enter the following for the
   'Redirect URI for OAuth calls' : http://localhost:3000/users/auth/constantcontact/callback
10. Enter the api key and secret key into:       _secret_tokens.rb file.
11. rake db:create
12. rake db:migrate
13. If you don't have a Constant Contact account, register for one account, and verify your account email address.
14. If you DO have a CTCT account, you will need to know the email address associated with that account.
15. Start your rails server :  'rails s'.
16. Load "Localhost:3000",  Click 'sign in'.
17. Enter your constantcontact login information.
    ( your username should be the email address you signed up with )
18. Success! 

Keep in mind that if other people work on your app they will need a copy of your _secret_tokens file, which should not be in github.
