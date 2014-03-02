#Bottle and Python 3.3 on openshift

Minimal requirements for running quickly a [Bottle][1] application withs Python 3 on [Openshift][2].

- Setup an account on [Openshift][2].
- Install RHC client tools following [this guide][3].
- You will probably need to [setup your SSH key][4].

Create a python 3.3 app
```
rhc app create yourAppName python-3.3
```

In local application folder app.py.disabled can be remove.

In local application folder, add app.py from this repo.
This is an official [Openshift file][5]

Add Bottle and others needed packages in setup.py by modifying the "install_requires" attribute.

If your package isn't available on PyPI you could try a [custom install][6].

Create a "views" folder for tpl in /wsgi. We'll configure Bottle to search tpl in this folder (see wsgi/application).

A minimal app is visible in wsgi/application

Check your app at:
```
http://yourAppName-YourNameSpace.rhcloud.com/
```

[1]: http://bottlepy.org/docs/dev/index.html
[2]: https://www.openshift.com/
[3]: https://www.openshift.com/developers/rhc-client-tools-install
[4]: https://www.openshift.com/developers/remote-access#keys
[5]: https://github.com/openshift-quickstart/Bottle-Python3-quickstart/blob/master/app.py
[6]: https://www.openshift.com/forums/openshift/how-to-install-a-custom-python-package
