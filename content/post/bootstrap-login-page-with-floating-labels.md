---
title: "Bootstrap Login Page with Floating Labels"
date: 2021-10-24T02:50:28+03:00
description: "Prettify XML strings with JS and XSLT transformations"
tags: ["Javascript", "HTML", "CSS", "Bootstrap"]
author: "kzmkrksc"
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
disableHLJS: true # to disable highlightjs
disableShare: false
searchHidden: false
cover:
	image: "" # image path/url
	alt: "" # alt text
	caption: "" # display caption under cover
	relative: false # when using page bundles set this to true
	hidden: true # only hide on current single page
---

# Bootstrap Login Page with Floating Labels

Creating a login page might not seem challenging to many in the field. However, creating a lightweight, responsive and cross-platform page might be difficult at times. 

Bootstrap is an amazing CSS framework and widely used in industry. Many of the login pages across the internet uses this CSS framework. You also might have seen floating labels on these forms across websites.

Here I will share a simple pen that I have worked in my leisure times. This pen includes Bootstrap 3 only and no additional JS code is required. This form also have basic validations.

### Login form with Floating labels - CSS only edition

```html
<div class="container">
    <div class="row">
        <div class="col-md-6 col-md-offset-3">
            <div class="panel panel-login">
                <div class="panel-heading">
                    <div class="panel-title text-center">Login</div>
                    <hr>
                </div>
                <div class="panel-body">
                    <div class="row">
                        <div class="col-lg-12">
                            <form id="login-form" class="col-lg-offset-1 col-lg-10" action="" method="post" role="form" style="display: block;">
                                <div class="form-group input-group">
                                    <span class="input-group-addon"><i class="fa fa-user"></i></span>
                                    <input type="text" name="username" id="username" tabindex="1" class="form-control" required placeholder=" ">
                                    <label class="form-control-placeholder" for="username">Username</label>
                                </div>
                                <div class="form-group input-group">
                                    <span class="input-group-addon"><i class="fa fa-lock"></i></span>
                                    <input type="password" name="password" id="password" tabindex="2" class="form-control" required placeholder=" ">
                                    <label class="form-control-placeholder" for="password">Password</label>
                                </div>
                                <div class="col-sm-6 col-sm-offset-3">
                                    <button type="submit" name="login-submit" id="login-submit" tabindex="3" class="form-control btn btn-login" value="LOGIN"><i class="fas fa-sign-in-alt"></i> Login</button>
                                </div>
                        </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
```


CSS Code:
```css
 .container {
	 padding-top: 90px;
	 font-family: "Arial", sans-serif;
}
 .panel-title {
	 font-size: 33px;
	 color: #888888;
}
 .panel-login {
	 padding-bottom: 1em;
	 background-color: #fafafa;
	 -webkit-box-shadow: 0 1px 2px 0 rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
	 box-shadow: 0 1px 2px 0 rgba(60, 64, 67, 0.3), 0 1px 3px 1px rgba(60, 64, 67, 0.15);
}
 .panel-login > .panel-heading hr {
	 margin-top: 10px;
	 margin-bottom: 0px;
	 clear: both;
	 border: 0;
	 height: 1px;
	 background-image: -webkit-linear-gradient( left, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.15), rgba(0, 0, 0, 0) );
	 background-image: -moz-linear-gradient( left, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.15), rgba(0, 0, 0, 0) );
	 background-image: -ms-linear-gradient( left, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.15), rgba(0, 0, 0, 0) );
	 background-image: -o-linear-gradient( left, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.15), rgba(0, 0, 0, 0) );
}
 .panel-login input[type="text"], .panel-login input[type="email"], .panel-login input[type="password"] {
	 height: 45px;
	 border: 1px solid #ddd;
	 font-size: 19px;
	 -webkit-transition: all 0.1s ease;
	 -moz-transition: all 0.1s ease;
	 transition: all 0.1s ease;
}
 .panel-login input:hover, .panel-login input:focus {
	 outline: none;
	 -webkit-box-shadow: none;
	 -moz-box-shadow: none;
	 box-shadow: none;
	 border-color: #ccc;
}
 .btn-login {
	 background-color: #59b2e0;
	 outline: none;
	 font-size: 18px;
	 height: auto;
	 font-weight: normal;
	 border-color: #ccc;
}
 .input-group {
	 margin-top: 35px;
}

#username:focus, #password:focus {	
	 border-bottom: 2px solid #b1b1b1;
	 padding-bottom: 3.5px;
}
#username, #password {
	 border-radius: .25rem;
	 display: block;
	 box-sizing: border-box;
	 -webkit-box-sizing: border-box;
}
 #login-submit {
	 color: #008080;
	 background-color: #fff;
	 margin-top: 25px;
	 transition: all 0.1s ease;
}
 #login-submit:hover {
	 border-color: #66afe9;
	 -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 8px rgba(102, 175, 233, 0.6);
	 box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
 .form-control-placeholder {
	  pointer-events: none;
	  cursor: text;
	 position: absolute;
	 top: 0;
	 padding: 12px 0 0 13px;
	 transition: all 200ms;
	 opacity: 0.5;
	   font-size:16px
}

.form-control-focused {
	font-size: 95%;
	 transform: translate3d(0, -100%, 0);
	 opacity: 1;
}

.panel-login input:focus ~ label, 
.panel-login input:not(:placeholder-shown) ~ label, 
.panel-login input:valid ~ label, 
.panel-login input:-webkit-autofill:focus ~ label {
	font-size: 95%;
	 transform: translate3d(0, -100%, 0);
	 opacity: 1;
}
```

[Live Codepen Demo](https://codepen.io/kzmkrksc/pen/dyPByyO)

When clicked inside input boxes, the labels inside float on top of input fields. This behavior works fine in Chrome browsers.
However this particular action might not work well in other browsers. It is required to use JS if you want a cross-platform solution.

### Login form with Floating labels - JS Edition


```html
<div class="container">
    <div class="row">
        <div class="col-md-6 col-md-offset-3">
            <div class="panel panel-login">
                <div class="panel-heading">
                    <div class="panel-title text-center">Login</div>
                    <hr>
                </div>
                <div class="panel-body">
                    <div class="row">
                        <div class="col-lg-12">
                            <form id="login-form" class="col-lg-offset-1 col-lg-10" action="" method="post" role="form" style="display: block;">
                                <div class="form-group input-group">
                                    <span class="input-group-addon"><i class="fa fa-user"></i></span>
                                    <input type="text" name="username" id="username" tabindex="1" class="form-control" required placeholder=" ">
                                    <label class="form-control-placeholder" for="username">Username</label>
                                </div>
                                <div class="form-group input-group">
                                    <span class="input-group-addon"><i class="fa fa-lock"></i></span>
                                    <input type="password" name="password" id="password" tabindex="2" class="form-control" required placeholder=" ">
                                    <label class="form-control-placeholder" for="password">Password</label>
                                </div>
                                <div class="col-sm-6 col-sm-offset-3">
                                    <button type="submit" name="login-submit" id="login-submit" tabindex="3" class="form-control btn btn-login" value="LOGIN"><i class="fas fa-sign-in-alt"></i> Login</button>
                                </div>
                            </form>
                        </div>

                    </div>
                </div>
            </div>
        </div>
    </div>
</div>

```


CSS:
```css
.container {
  padding-top: 90px;
}
.panel-title {
  font-size: 33px;
  color: #888888;
}
.panel-login {
  padding-bottom: 1em;
  background-color: #fafafa;
  -webkit-box-shadow: 0 1px 2px 0 rgba(60, 64, 67, 0.3),
    0 1px 3px 1px rgba(60, 64, 67, 0.15);
  box-shadow: 0 1px 2px 0 rgba(60, 64, 67, 0.3),
    0 1px 3px 1px rgba(60, 64, 67, 0.15);
}

.panel-login > .panel-heading hr {
  margin-top: 10px;
  margin-bottom: 0px;
  clear: both;
  border: 0;
  height: 1px;
  background-image: -webkit-linear-gradient(
    left,
    rgba(0, 0, 0, 0),
    rgba(0, 0, 0, 0.15),
    rgba(0, 0, 0, 0)
  );
  background-image: -moz-linear-gradient(
    left,
    rgba(0, 0, 0, 0),
    rgba(0, 0, 0, 0.15),
    rgba(0, 0, 0, 0)
  );
}
.input-group {
  margin-top: 35px;
}
.form-group input[type="text"],
.form-group input[type="email"],
.form-group input[type="password"] {
  height: 45px;
  border: 1px solid #ddd;
    border-top-right-radius: 0.25rem;
    border-bottom-right-radius: 0.25rem;
    display: block;
    box-sizing: border-box;
    -webkit-box-sizing: border-box;
  font-size: 16px;
  -webkit-transition: all 0.1s ease;
  -moz-transition: all 0.1s ease;
  transition: all 0.1s ease;
}
.panel-login input:hover,
.panel-login input:focus {
  outline: none;
  -webkit-box-shadow: none;
  -moz-box-shadow: none;
  box-shadow: none;
  border-color: #ccc;
}
.btn-login {
  outline: none;
  font-size: 18px;
  height: auto;
  font-weight: normal;
  border-color: #ccc;
    color: #008080;
  background-color: #fff;
  margin-top: 25px;
  transition: all 0.1s ease;
}
.btn-login:hover {
  border-color: #66afe9;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075),
    0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075),
    0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control-placeholder {
  pointer-events: none;
  cursor: text;
  position: absolute;
  top: 0;
  padding: 12px 0 0 13px;
  -webkit-transition: all 0.2s;
  transition: all 0.2s;
  opacity: 0.5;
  font-size: 16px;
  font-weight: 400;
}

input:focus + label,
input + label.label-animated {
 font-size: 95%;
     transform: translatey(-2.5em);
     opacity: 1;
}

input:-webkit-autofill + label {
 font-size: 95%;
     transform: translateY(-2.5em);
     opacity: 1;
}
input:not(:placeholder-shown) + label {
 font-size: 95%;
     transform: translateY(-2.5em);
     opacity: 1;
}

```

And finally JS: 
```js
$(function () {  
  $(".form-group input").on("checkval", function () {
    let label = $(this).next("label");
    if(this.value !== "") {
      label.addClass("label-animated");
    } else {
      label.removeClass("label-animated");
    }
  }).on("keyup", function () {
    $(this).trigger("checkval");
  })
});


```


[Live Codepen Demo](https://codepen.io/kzmkrksc/pen/dyoyZNx)