What is it?
===========

If you want to install Django LFS [http://www.getlfs.com/] with facebook support, you can fork this repository.

How to use it?
==============

* git clone git@github.com:filippo91/lfs_facebook.git
* cd lfs_facebook_buildout/lfs-installer 
* virtualenv --no-site-packages . 
* bin/pip install --upgrade setuptools
* bin/python bootstrap.py
* bin/buildout -v
* bin/django syncdb
* bin/django lfs_init
* bin/django collectstatic
* bin/django runserver

More information
==============

https://pypi.python.org/pypi/django-facebook
http://www.getlfs.com/
http://blog.pythonanywhere.com/35/
