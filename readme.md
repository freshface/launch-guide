# Quick launch checklist

- `$debug = false;`
- Check url in `parameters.yml`
- SSL and http/2
- Clear cache
- Check website
- ImageOptim
- PageSpeed Insights ([link](https://developers.google.com/speed/pagespeed/insights/))
- SEO

  

# Optimizations

## Website

## FontAwesome

Well... we only need a couple of icons, so loading in a selected set of icons would be better instead of the whole library.
To be continued...

### Minify javascript files

Don't forget to minify (or re-minify after changes) the javascript files.


### Lazy load images and background images

Background image:

`<div class="b-lazy" data-src=""></div>`

Image:

`<img class="b-lazy"  src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==" data-src=""> `

*You can also add `data-src-small=""` but it's optional*


### Loading external css or javascript

- Always try to use `https://` or `//assets.site.tld ` (the last one uses the http(s) protocol of the website)

- For css, load it in the deferred stylesheets part of Head.html.twig:  `<noscript id="deferred-styles"> ... </noscript>`

- For javascript, load it defferred: `<script defer src=""></script>`






## Server


### SSL, https/2 and GZIP

When activating SSL, try enabling https/2 for speed gain (the assets of this Fork theme or optimized for https/2)

You can enable this in `my.combell.be` of the hosting package under `"Site instellingen > http/2"`

Also enable GZIP compression in the general tab of `"Site instellingen > algemeen"`


### ImageOptim images

ImageOptim the theme images and `/src/Frontend/Files` folder from the server (the live files)


### Cookie-less domain

Add this to the .htaccess: __(always test this!)__  
This removes the cookies from al the loaded assets for page speed gains.

```
# file caching in browser
<IfModule mod_expires.c>
	ExpiresActive On
	<FilesMatch "\.(?i:ico|gif|jpe?g|png|svg|svgz|js|css|swf|ttf|otf|woff|eot)$">
		ExpiresDefault "access plus 1 month"
		RequestHeader unset Cookie
		Header unset Cookie
		Header unset Set-Cookie
	</FilesMatch>
</IfModule>
```


## SEO

### General

- Add a good general page title 

### Home page

- Change the page title (so it doesn't have __home__ in it)
- Add a meta description (for the serp)


### Google

- Submit your website to the developpers tool ([link](ttps://www.google.com/webmasters/tools/home))
- And add a sitemap ([link](ttps://www.google.com/webmasters/tools/home))
- Run thru PageSpeed Insights ([link](https://developers.google.com/speed/pagespeed/insights/))
- Add Google Analytics ([link](https://analytics.google.com))