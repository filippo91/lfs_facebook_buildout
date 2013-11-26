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

  * You have to modify lfs_project/settings.py, where you are going to put right data for these variables:

    ```

      FACEBOOK_APP_ID = 'YOUR APP ID'
      FACEBOOK_APP_SECRET = 'YOUR APP SECRET NUMBER'

      FACEBOOK_PAGE = 'YOUR PAGE ID'

      """
      If you set True some of these variables, the page will be visible only for the user that is authenticated; 
      so if user isn't already authenticated, it will be immediately redirected to loggin page. 
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

  * While you’re editing lfs_project/settings.py, set DATABASE to your favourites options, althought is already setted to work with sqlite3.

```
$ bin/buildout -v

$ bin/django syncdb

$ bin/django lfs_init

$ bin/django collectstatic

$ bin/django runserver
```
More information
==============

* https://pypi.python.org/pypi/django-facebook
* http://www.getlfs.com/
* http://blog.pythonanywhere.com/35/
* https://github.com/redomino/lfs_responsivetheme
