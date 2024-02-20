# Bouncer

Bouncer is a bookmarklet that allows you to quickly extract user IDs from social media profiles on Twitter, Facebook, Instagram, and TikTok. It's a handy tool for researchers, analysts, and anyone interested in gathering user information from these platforms.

## Installation

To install the "Bouncer" bookmarklet, simply drag the following link to your bookmarks bar:

[Click here to install Bouncer](javascript:(function(){try{var e=window.location.href;if(e.includes("twitter.com")){var t=document.evaluate('//script[@type="application/ld+json"]',document.lastChild,null,XPathResult.ANY_TYPE,null).iterateNext().textContent,n=JSON.parse(t),i=n.author&&n.author.identifier;i?alert("Twitter User ID: "+i):alert("Identifier not found!")}else if(e.includes("facebook.com")){var o=document.documentElement.innerHTML,r=o.match(/"userID":"(\d+)"/);r&&r[1]?alert("Facebook User ID: "+r[1]):alert("User ID not found on this page.")}else if(e.includes("instagram.com")){var a=document.documentElement.innerHTML,r=a.match(/"userID":"(\d+)"/);r&&r[1]?alert("Instagram User ID: "+r[1]):alert("User ID not found on this page.")}else if(e.includes("tiktok.com")){var c=document.documentElement.innerHTML,r=c.match(/"user":{"id":"(\d+)"/);r&&r[1]?alert("TikTok User ID: "+r[1]):alert("User ID not found on this page.")}else alert("This bookmarklet only works on Twitter, Facebook, Instagram, or TikTok.")}catch(e){alert("Error fetching or processing data: "+e.message)}})();)

**Note:** This bookmarklet is designed to work on the specified social media platforms. Please ensure you are on the profile page of the platform you wish to extract the user ID from before using the bookmarklet.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
