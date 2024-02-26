# Bouncer 

Bouncer is a simple yet powerful bookmarklet that helps you quickly retrieve user IDs from popular social media platforms like Twitter, Facebook, Instagram, TikTok and Reddit. Whether you're an OSINT enthusiast, a marketer, or just curious, Bouncer makes it easy to get the information you need with just one click.

## Installation

1. Right-click on your bookmarks bar and select "Add page" or "Add bookmark."
2. Name the bookmark as "Bouncer" or anything you prefer.
3. In the URL field, paste the following code:

    ```javascript
    javascript:(function(){try{var e=window.location.href;if(e.includes("twitter.com")){var t=document.evaluate('//script[@type="application/ld+json"]',document.lastChild,null,XPathResult.ANY_TYPE,null).iterateNext().textContent,n=JSON.parse(t),i=n.author&&n.author.identifier;i?alert("Twitter User ID: "+i):alert("Identifier not found!")}else if(e.includes("facebook.com")){var o=document.documentElement.innerHTML,r=o.match(/"userID":"(\d+)"/);r&&r[1]?alert("Facebook User ID: "+r[1]):alert("User ID not found on this page.")}else if(e.includes("instagram.com")){var a=document.documentElement.innerHTML,r=a.match(/"userID":"(\d+)"/);r&&r[1]?alert("Instagram User ID: "+r[1]):alert("User ID not found on this page.")}else if(e.includes("tiktok.com")){var c=document.documentElement.innerHTML,r=c.match(/"user":{"id":"(\d+)"/);r&&r[1]?alert("TikTok User ID: "+r[1]):alert("User ID not found on this page.")}else if(e.includes("reddit.com/user/")){var n=e.split("/user/")[1].split("/")[0],o=document.createElement("script");o.src="https://www.reddit.com/user/"+encodeURIComponent(n)+"/about.json?jsonp=displayRedditUserId",document.body.appendChild(o),window.displayRedditUserId=function(e){e&&e.data&&e.data.id?alert("Reddit User ID: "+e.data.id):alert("User ID not found on this page.")}}else alert("This bookmarklet only works on Twitter, Facebook, Instagram, TikTok, or Reddit.")}catch(e){alert("Error fetching or processing data: "+e.message)}})();
    ```

4. Save the bookmark.

## Usage

1. Navigate to the profile page of a user on Twitter, Facebook, Instagram, TikTok or Reddit.
2. Click on the "Bouncer" bookmarklet in your bookmarks bar.
3. A pop-up alert will display the user ID of the profile you're viewing.

## Supported Platforms

- Twitter
- Facebook
- Instagram
- TikTok
- Reddit

## Detailed Write Up

Featured in Issue #43 of The OSINT Newsletter -> https://osintnewsletter.com/p/43
