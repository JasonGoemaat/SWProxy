# Install python

Location: C:\python27

Use git bash for commands, created file in C:\apps\bin (because it's in my path) like this:

    /c/python27/python.exe "@*"

Install pip, copied this to C:\python27 and ran ./get-pip.py from the git bash:

    https://bootstrap.pypa.io/get-pip.py

Added another script /c/apps/bin/pip:

    /c/python27/scripts/pip.exe "@*"

Oops, that's $@, not @*

Got insecure platform warning, had to upgrade ndg-httpsclient:

    https://urllib3.readthedocs.org/en/latest/security.html#snimissingwarning
    pip install --upgrade ndg-httpsclient

Still getting error:

		Jason@HOMEJASON3 MINGW64 /c/python27
		$ pip install pcrypto
		Collecting pcrypto
		  Could not find a version that satisfies the requirement pcrypto (from versions: )
		No matching distribution found for pcrypto

Actually spelling the module right (pYcrypto) helps, but gives error that Visual C++ 9.0 is required:

    error: Microsoft Visual C++ 9.0 is required (Unable to find vcvarsall.bat). Get it from http://aka.ms/vcpython27

That redirects to: https://www.microsoft.com/en-us/download/confirmation.aspx?id=44266
83 mb later, I wonder where to isntall it...

Well well, after installing it just worked...

Had to install two other packages with no issues:

    pip install dpkt
    pip install yapsy

And for my own use:

    pip install requests
    