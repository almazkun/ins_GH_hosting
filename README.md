# Hosting website on GitHub pages for FREE
Instruction on how to host your website on (GitHub pages)[https://pages.github.com/] for FREE.

## 1. Sing In to [Github.com](github.com) and create repository.
We need to create account on [Github.com](github.com) and create new repository of special type.
- Go to `[Github.com](github.com)`, hit `sign up` and complete the registration.
- After confirming the email address you will be redirected to the page for creating a `new repository`.
- Create new repository. 
    - Repository name should be: `*github_login*.github.io`, where *github_login* is User name you have chosen. You can see it also in a field called `Owner`. In my case the repository name should be `focuskeeperdotapp.github.io`.
    - Choose `Public`.
    - Check the `Initialize with a README`
    - Hit `Create Repository`
- Check if it is working. Navigate to the `*github_login*.github.io` and you must see the greeting page. If you see `404` error or anything else, delete the repository and start all over. Check the name of the repository, it should be exactly like your login and followed by `.github.io`.

## 2. Adding HTML website. 
Now we need to create a website you want to host on the internet. We can clone this repository to our computer and make changes to it or we can do it in the browser. For demonstration purposes we will start with a browser.
- On the page of the repository, push `Create new file` button.
- Enter the name of the file: `index.html`.
- Copy & Paste the following code:
```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <!-- Required meta tags -->
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
        <title>How to host a website on GitHub pages for FREE</title>
        <!-- Stylesheets -->
        <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
    </head>

    <body class="bg-light">
        <div class="m-4">
            <div class="jumbotron">
                <div class="container">
                    <div class="row">
                        <div class="col-xl-8">
                            <h1 class="display-1 display-fix">Awesome</h1>
                            <span class="lead">My New and Awesome website hosted on GitHub pages</span>
                        </div>
                    </div>
                </div>
            </div>

            <div class="container py-5">
                <h2 class="display-4">Thanks</h2>
                <p class="lead">Thank you for reading this instruction<br>
                    <a href="https://akun.dev">https://akun.dev</a>
                </p>
            </div>
        </div>
    </body>
</html>
```
- Commit this file to the repository.
- Open navigate to the `*github_login*.github.io`. You will see newly created website! Congratulations!

## 3. Buy your domain name.
Adding custom domain name to the GitHub pages is quite easy too. We need to buy one first. You can buy it from whatever registrar you want. I like [Porkbun](https://porkbun.com/) registrar.
- Go to [Porkbun.com](https://porkbun.com/). 
- Find a desired domain name. I wanted to buy `focuskeeper.app`.
- Click `+`, register and pay for the domain name you want.

## 4. Setting app custom domain name for GitHub pages.
Now we will point the your new domain to the GitHub pages.
- Navigate to the repository page on [Github](https://github.com). It should be: `https://github.com/*github_login*/*github_login*.github.io` and open `Settings` tab.
- Scroll down to the `GitHub pages` section and add your newly purchased domain name to the *Custom domain* field.

## 5. Cloudflare DNS records. 
We need to add new DNS records for our domain. For a number of reasons I like [Cloudflare](https://cloudflare.com) for that purposes.
- Go to the [cloudflare.com](https://cloudflare.com) and register there.
- Add `New Site`. Type your domain name in the form
- Select `Free` plan.
- Now we need to delete **all** the DNS record here.
- And add DNS records we need. In the table below is how you need to type them in the empty field. They will be displayed little differently after you hit `Add Record` button. 

    Type|Name|Value
    ---|---|---
    A|@|185.199.108.153|
    A|@|185.199.109.153|
    A|@|185.199.110.153|
    A|@|185.199.111.153|
    CNAME|www|@
    
    Press `Continue`. 

- Now we need to change `nameservers` on our registrar website(where you bought the domain name). 
- Go to [Porkbun.com](https://porkbun.com/). Open `Details` dropdown, find `AUTHORITATIVE NAMESERVERS`, click `Edit`. 
- Delete old records and add assigned by the `Cloudflare`.
- Go to the [cloudflare.com](https://cloudflare.com) and click `Done, check nameservers`. 
- Here

    - check `Full` encryption
    - `ON` to `Always Use HTTPS` 
    - choose to minify everything
    - `ON` to Brotli
    - `Done`

- It will take a sometime (they say up to 24 hrs) to change DNS record. 

## Done
We are actually done. We deployed a website to the internet without leaving a browser. Thank you!