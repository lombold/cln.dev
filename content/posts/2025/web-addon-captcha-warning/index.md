+++
title = 'Privacy concerns with reCAPTCHA V3'
date = 2025-02-07T19:00:00+01:00
draft = false
version = 1
author = 'Colin'
categories = ['Browser Addon', 'reCAPTCHA V3', 'Privacy']
+++

Captcha challenges are keeping bots from flooding the internet with generated stuff. They are tough but a lot less I guess.

Back in 2009 Google took over reCAPTCHA and, so far, they released three versions: 
* V1: The one where you help google recognising house numbers in StreetView
* V2: Just an "I'm not a robot" checkbox. User behaviour like mouse movements are tracked in the background.
* V3: Invisible. reCAPTCHA is permanently calculating a score based on the user's behaviour. [[1]](https://developers.google.com/recaptcha/docs/v3)

Since V3 is no more visible to the user there are a lot of concerns about privacy. Especially because some of the tracked data is send to Google. If interested I'm recommending the reCAPTCHA Wikipedia article: https://en.wikipedia.org/wiki/ReCAPTCHA

Apparently, Cloudflare was moving to hCaptcha because of this: https://blog.cloudflare.com/moving-from-recaptcha-to-hcaptcha/

I'm not against captchas, but it bothers me that I don't know that I'm being tracked.

To mitigate that feeling I created a small Firefox addon which adds a red border to all websites which use reCAPTCHA. Feel free to install it or fork the code: 

Addon: https://addons.mozilla.org/de/firefox/addon/captcha-warning/

Code: https://github.com/lombold/browser-addon-captcha-v3-warning




