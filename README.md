# Instagram_Instafeed How it works

### How to get Instagram images on to website using instafeed.js

## Step 1: Register A New Client

1.Register as a new Client with the instagram developer website.
⋅⋅* vist [This Link](https://www.instagram.com/developer/) and login to your account.

2.Complete the form, here’s a break down of what each field is (Screen Shot below):

..1. Application Name: An arbitrary descriptive name for your App (e.g. ‘Blog’ or ‘my_app’)
..2. Description: A description of your app or service (e.g. ‘My life through my Blog’ or ‘App about beer’)
..3. Company Name: The company name... duh! or if its a personal site or app, Just use something simple like your name.
..4. Website Url: The Url of the site or application. This works for local websites still in production too!
..5. Valid redirect URIs: This field is another website url, it is simply the address to which users will be redirected after they are asked by Instagram to confirm or deny access to the account.
..6. Privacy Policy URL: I left this blank for testing purposes, but if you have a URL with your Privacy Policy stated, you can add this in the field. (If you leave it blank, you can always add it later.)
..7. Contact email: This field is for your email address so Instagram can contact you about important information about your app you are creating. 

![alt screenshot](/Screenshots/Capture.PNG)

3. Once you Register, You will be presented with a Client ID and the client status. Keep the page open, we will need this stuff later on. 

## Authorize your App/Client

1. Copy this URL - https://instagram.com/oauth/authorize/?client_id=YOURCLIENTIDHERE&amp;redirect_uri=HTTP://YOURREDIRECTURLHERE.COM&amp;response_type=token - and past it to a new open page in the browser. 

2. Replace the bits in UPPERCASE with the clientClient ID and Redirect URI you have open in another page. Then Hit Enter to submit the URL.

..* ! If you get an error message about "implicit OAuth is disabled" go back to the instagram developer page and click "manage" > "Security" and uncheck "Disable implicit OAuth:"

..* Repeat Steps 1 & 2

3. After you have successfully achieved that, You will be prompted of a screen that says something like " Hi Bob, The beer app is requesting you do the following:".... Just click Authorize and the page will redirect you to the redirect URI you submitted when registering. 

4. This is important! In the URL, It displays the address and also the access_token. Looks Something like https://www.google.com/#access_token=42343007962.5t49b31.297br08eccde4b05ad75ff49c5239f6f. (This is an example and has been modified to be fictitious)

5. Copy the access_token and store it somewhere to copy for later use. 

##Applying the HTML & Javascript code.

`<div id="instafeed">&nbsp;</div>

<p><script type="text/javascript" src="/themes/donnie/js/instafeed.min.js"></script><script>
var feed = new Instafeed({
  get: 'user',
  userId: '20658065',
  accessToken: '20658065.f61fb3b.9d9df46a18674371874cbf544d3f9f21',
  resolution: 'low_resolution',
});
feed.run();
console.log( "feed" + feed);

</script></p>`

