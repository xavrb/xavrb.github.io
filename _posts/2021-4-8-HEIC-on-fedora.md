---
layout: post
title: See HEIC files correctly on Fedora  
tags: [heic, heif, fedora]
---

HEIC is the new standard for image/video files on iOS ecosystem and by default are not recognized on Fedora. There is a very easy way to fix this and its installing the library that lives on rpmfusion-free repository.
We can install it as simple as typing:

{% highlight bash %}
$ sudo dnf install libheif
{% endhighlight %}

And it's done:

![heic](../images/heic/heic.png)   

We can see the preview for the heic file is created and your default or favorite image viewer should be able to show the file correctly:

![heic2](../images/heic/heic2.png)   
![heic3](../images/heic/heic3.png)   



EZ PZ
