What is it?
===========

If you want to install Django LFS [http://www.getlfs.com/] with facebook support, you can fork this repository.

How to install it?
==============
```
$ git clone https://github.com/filippo91/lfs_facebook_buildout.git

$ cd lfs_facebook_buildout/lfs-installer

$ virtualenv --no-site-packages .

$ bin/pip install --upgrade setuptools

$ bin/python bootstrap.py
```

* facebook settings

  * You have to modify lfs_project/settings.py, where to put right data for these variables:

    ```

      FACEBOOK_APP_ID = 'YOUR APP ID'
      FACEBOOK_APP_SECRET = 'YOUR APP SECRET NUMBER'

      FACEBOOK_PAGE = 'YOUR PAGE ID'

      """
      If you set some of these variables as True, the page will be visible only for authenticated users; 
      a non-authenticated user will be immediately redirected to loggin page. 
      Loggin uses facebook backend.
      """
      VIEW_WITH_LOGIN_REQUIRED = {
        'add-to-cart': '' #True or False,
        'shop': '' #True or False,
        'category': '' #True or False,
        'product': '' #True or False,
        'checkout': '' #True or False,
      }
      
    ```

  * While you’re editing lfs_project/settings.py, set your DATABASE options as you like, althought it is already set to work with sqlite3.

```
$ bin/buildout -v

$ bin/django syncdb

$ bin/django lfs_init

$ bin/django collectstatic

$ bin/django runserver
```

Features
==============
* With lfs_facebook you can make a product available for facebook fans only.

   To set this feature to a product you add a lfs property(of whatever type you want) 
   with title: "Facebook Fan Reserved". So if a user doesn't like your Facebook page, he can't
   add to cart the specific product. 


More information
==============

* https://pypi.python.org/pypi/django-facebook
* http://www.getlfs.com/
* http://blog.pythonanywhere.com/35/
* https://github.com/redomino/lfs_responsivetheme
