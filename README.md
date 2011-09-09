From http://stackoverflow.com/questions/7358550/restrict-access-to-a-webpage-with-jquery:

```
Is there a way to restrict access to a specific webpage such as
http://www.example.com/subpage with jQuery? I know there are many other
feasible ways to accomplish that via PHP and .htaccess but in our case we
don't have access to .htaccess file. However jQuery is installed. I was
thinking to try to read the window.location.href and add a hash to the URL.
But I am not sure if this can be exposed if a user view the source code of
the page in question. - digitup
```

```
This may be a bit too crazy: You could load parts of the page with Ajax,
as tandu suggests it, but store them encrypted on the server. On the client
side, let the user type in the password and use a JavaScript implementation
of an crypto algorithm to decrypt the received data. – Felix Kling
```

This is a simple implementation of that idea, built using [SJCL](http://crypto.stanford.edu/sjcl/).

Be sure to have [node.js](http://nodejs.org) installed.

Then from the root directory of this project, run:

node dumbcrypt.js *myfile.html* *password* > *encrypted_file.html*

If the password contains spaces or special characters, enclose it in single-quotes.