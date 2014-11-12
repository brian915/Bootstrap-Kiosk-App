Bootstrap an App with Constant Contact 
==========

a proof of concept for a kiosk app to add users to a mailing list or check them in at an event 



#Goals of the Exercise : 

1) replicate the sign-up form 

2) thank you page 

3) automatic return to form upon submit 

4) bonus round - create an event signup option

This application  will utilize AppConnect  - Constant Contact's Developer API

# Setup Instructions

1. Fork this repo from github
2. Clone your fork to your local machine.
3. Copy the config/initializers/_secret_tokens.rb.example file to _secret_tokens.rb
 (note this file is git-ignored so you don't accidently put your private keys on github)
4. Open config/initializers/_secret_tokens.rb in your editor of choice
5. Run: 'bundle install'
6. Run 'rake secret' to generate a new rails secret key.
7. Paste this key into the _secret_tokens.rb file on the line for 'BootstrapKioskApp::Application.config.secret_key_base
8. Sign up for an API key through mashery:
https://constantcontact.mashery.com/
9. Create a new application by clicking API Keys, then Applications
 ** Make sure to enter the following as the 'Redirect URI for OAuth calls'
http://localhost:3000/users/auth/constantcontact/callback
10. Enter the api key and secret key into the _secret_tokens.rb file.
11. Register for a ConstantContact account, and verify your account email address
12. Start your rails server with rails s
13. Click 'sign in'
14. Enter your constantcontact login information * your username should be the email address you signed up with *

You should now be a all set up!

Keep in mind that if other people work on your app they will need a copy of your _secret_tokens file, which should not be in github.
