# SSL encryption

## SSL offloading

If you need SSL encryption for your website, freistilbox has a great feature for you: SSL offloading. This means that SSL packets are decrypted the moment they reach the freistilbox infrastructure. The HTTP requests that were encrypted in the SSL packets are then passed on to the next system layers. This has several advantages:

* HTTP caching works regardless of encryption. That way, you don't need to use "mixed mode" (i.e. delivering parts of a page unencrypted) to achieve short delivery times for page assets.
* Your web application servers don't need to use their computing resources for decrypting requests and encrypting their responses.


## Recognizing secure requests

Because SSL request are decrypted before they reach your freistilboxes, your web application will always receive plain HTTP requests. In order to be able to see if a request originally came in SSL-encrypted, the SSL offloader marks those with the HTTP header "X-Forwarded-Proto" and set its value to "https". Our web servers then set an environment variable named `HTTPS` to the value `on`.

In your application, you can simply test this variable to see if a request had been encrypted by its sender. 

In PHP:

    if (_SERVER['HTTPS'] == "on")

This variable is set by PHP for incoming SSL requests, too, so existing applications, plugins and modules should work out of the box.

If you need to test for SSL in an `.htaccess` file, there's a catch. While Apache's `mod_rewrite` has a condition named `HTTPS` built in, its result is true only if the request actually reached the box via SSL -- which, thanks to our SSL offloading, will never be the case. Therefore, you need to check the environment variable of the same name instead:

Does _not_ work:

    RewriteCond %{HTTPS} on

Works:

    RewriteCond %{ENV:HTTPS} on

We recommend you cover all bases by checking both condititions:

    RewriteCond %{HTTPS} on [OR]
    RewriteCond %{ENV:HTTPS} on
