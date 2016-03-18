+++
date = "2016-03-18T16:15:41+11:00"
draft = false
title = "Moving to Hugo"

+++

After using [Metalsmith](http://www.metalsmith.io/) as my [previous blog engine](http://barclay.io/metalsmith/) I decided to move to Hugo.

I previously used Metalsmith for the large amount of flexibility and the fact I could easily write new additions to my site.

The downside is that it is time consuming to get right. I spent a bit of time on it, then somewhat stopped. I never got the theming fully finished, or RSS support integrated.

[Hugo](https://gohugo.io/) comes with everything fully configured out of the box. I was able to drop my markdown files into the content folder and generated a new site with no trouble.

So far I have been very happy with this, and can imagine a lot of improvements to the way I generate this site.

I still use github to store the content for my site, rebuild with travis and push all the content to a S3 bucket that I serve out of.

In the future I would love to put [CloudFront](https://aws.amazon.com/cloudfront/) with a [LetsEncrypt](https://letsencrypt.org/) certificate in front of the S3 bucket. I'll also look into using a [Lambda](https://aws.amazon.com/lambda/) such as [this one](https://github.com/ryansb/hugo-lambda) to generate the site. Eventually I should be able to create a simple admin page that can write to the S3 bucket and regenerate the site.

Still, until then, the new theme and functionality has been a great improvement over my old site.
