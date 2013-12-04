What is it?
===========

If you want to install Django LFS [http://www.getlfs.com/] with facebook support, you can fork this repository.

![ScreenShot](https://raw.github.com/filippo91/lfs_facebook_buildout/master/screenshots/facebook_lfs_product.png)

How to install it?
==============
```
$ git clone https://github.com/filippo91/lfs_facebook_buildout.git

$ cd lfs_facebook_buildout/

$ virtualenv --no-site-packages .

$ bin/pip install --upgrade setuptools

$ bin/python bootstrap.py
```
  
You have to modify lfs_project/settings.py, where to put right data for these variables:


      FACEBOOK_APP_ID = 'YOUR APP ID'
      FACEBOOK_APP_SECRET = 'YOUR APP SECRET NUMBER'

      FACEBOOK_PAGE = 'YOUR PAGE ID'

      """
      If you set some of these variables as True, the page will be visible only for authenticated users; 
      a non-authenticated user will be immediately redirected to loggin page. 
      Loggin uses facebook backend.
      """
      VIEW_WITH_LOGIN_REQUIRED = {
        'add-to-cart': '', #True or False
        'shop': '', #True or False
        'category': '', #True or False
        'product': '', #True or False
        'checkout': '', #True or False
      }
      
      #Title of the property to allowed a view for Facebook fan only
      FACEBOOK_FAN_RESERVED_PROPERTY = "Facebook Fan Reserved"
      

While you’re editing lfs_project/settings.py, set your DATABASE options as you like, althought it is already set to work with sqlite3.

```
$ bin/buildout -v

$ bin/django syncdb

$ bin/django lfs_init

$ bin/django collectstatic

$ bin/django runserver
```

How do I get Facebook Application credentials?
==============
To create a Facebook Application ID:

* Go to the Facebook Developers Apps page, and sign in with your Facebook username and password.

* Click the "Create New App" button.

* If you do not see the option to create a new app in the upper right hand corner, click on "Register as Developer."

* Enter a name for the application in the "App Name" field. Using your store name is recommended.

* Read the Facebook Platform Policies and decide if you accept them. Once you've read the Facebook Platform Policies and have entered an App Name (step 2, above), click the "Continue" button. Note that by clicking the "Continue" button, you agree to the Facebook Platform Policies.

* You may be asked to verify your account by providing a mobile number or credit card number. If your Facebook account has already been verified, you may not be asked to verify your account.

* You may also encounter a Captcha security check. Enter the Captcha code and click the "Continue" button.

* You should now be on the Basic (Basic Settings) page for your app, where the App Name you provided in Step 2 will be shown in the "Display Name" field. Check that this name is correct, and that your contact email address is correct, and then proceed to the "App Domains" field.

* Enter your domain name in the "App Domains" field (e.g. papayadayspa.com).

* Next, scroll down to the "Select how your app integrates with Facebook" section of the Basic page, and click "Website with Facebook Login." This section will expand to show a "Site URL" field.

* Enter your store URL in the "Site URL" field (e.g. http://www.papayadayspa.com ).

* Click the "Save Changes" button.

Now you have a Facebook Application with its ID and secret key, you can check it at main page of application.

Remember that Facebook requires https. 

Credits
==========
* Filippo Projetto <heartbreakid91@gmail.com> (@filippo91), maker
* Fabrizio Reale <fabrizio.reale@redomino.com> (@realefab), Project manager
* Davide Moro <davide.moro@redomino.com> (@davidemoro), IT specialist & motivator :)
* Andrea D'este <andrea.deste@redomino.com> (@adeste), Programmer & Designer

More information
================

* https://pypi.python.org/pypi/django-facebook
* http://www.getlfs.com/
* http://blog.pythonanywhere.com/35/
* https://developers.facebook.com/docs/web/
* https://github.com/redomino/lfs_responsivetheme
