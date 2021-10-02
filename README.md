# AMP Local Listing Landing Page

This is based on a project I originally built as a proof of concept while working at an agency [here](https://generationsbeyond-com.cdn.ampproject.org/c/generationsbeyond.com/clients/amp/), which itself was moddled after an info graphic from  "the Pefect local landing page", an article found [here](https://www.bowlerhat.co.uk/perfectly-optimised-local-landing-page/) and based on this:

![Perfectly Optimized Local Landing Page](https://searchengineland.com/figz/wp-content/seloads/2016/06/perfectly-optimized-local-landing-page.png)

So how did it go? Read On!

## 1. Setup

First I set up the AMP skeleton for the project by copying the boilerplate amp code from [here](https://amp.dev/documentation/guides-and-tutorials/start/create/basic_markup/?format=websites). It has all the required tags and meets all the structural requirements to get you started.

## 2. The Header

I set up the header with a space for the logo on the left and social sharing on the right (same as the infographic). For the social sharing component I went to the amp cpmonent library [here](https://amp.dev/documentation/components/) and found the "amp-social-share" component (checks out right?). I droped the associated script tag in the header and the component markup in a header tag with the phone number after (important for a local listing)

_note_: I removed a few of the available share buttons that I wouldnt normally use and just left the ones I would with the exeption of removing the facebook share which I would normally include. Why? There is additional setup required to add facebook shareing as far as registering it with facebook - its not dificult but I didint want to add it to the boilerplate.

_note_: What are you sharing? Basically the share buttons are picking up the title of the page as a subject and getting the link from the canonical link in the header - If you want to change whats being shared do it there.

## 3. Informational sections
Added two sections - the first has the main heading for the page up top then the hero image, sub heading and main copy block with a call to action here. The second is broken into two sections - One to ask a question / pose a problem that might relate to the client and the second offering an solution and explaining more about it. I think this is a pretty good way to go about a landing page (again, check the graphic)

## 4. Adding the testimonials slider

Here I went back to the AMP Component library and looked for something I could use for displaying client / customer testimonials. I landed on an image carousell (amp-carousel) and adapted it for my own purpouse. 

_note_: The amp-carousell component adds a ton of stuff under the hood, but you dont have to worry about that- just know that whatever the direct children comonents of the amp-carousel tag contained within the slider are will be made into slides. I also added the autoplay attribute to the amp-carousel tag so it would autoplay (obviously) and loop where as without it it wont loop at the end.

## 5. Contact and map section

Here I added the contact info as well as one last CTA on the left, then an amp-iframe on the right, taken from the examples section of the documentation [here](https://amp.dev/documentation/examples/components/amp-iframe/?format=websites). _Remember to add the corisponding script tag to the head of the doc whenever you add a component_.

Last but not least - take advantage of Google's own AMP Cache for serving your page lightning fast! How do you do it? Just adjust your URL to match there specifications and enter it in your browser and your set and its cached! The easyiest way to do it is to go to the documentation for the cache and use the url builder [here](https://amp.dev/documentation/examples/guides/using_the_google_amp_cache/) then copy and paste the link to your amp page in the input field under the _AMP Cache URL Format_ heading.

And thats the project! _Note: this boiler plate is for the most part unstyled with the exeption of some colors to show structural seperation or placeholders for images. When adding images, use the amp-img tag and be *sure to make the page mobily responsive! Remember - Amp was mostly created to speed up the mobile web. Check for other branches with styling, responsive design for mobile and Accessible markup comming sooin(ish) _:



----------

_Appended: Adding images_

This being a boilerplate, I didn't add images. Images can be a bit trickey in AMP as they have to have a specific height and width to be valid (to avoid content pushing, which annoys everyone). you can just include one size but thats not that mobile friendly - Images CAN be done responsivly with a sourceset attribue though:
ex:
`<amp-img alt="Hummingbird"
  src="/static/inline-examples/images/hummingbird-wide.jpg"
  width="640"
  height="457"
  layout="responsive"
  srcset="/static/inline-examples/images/hummingbird-wide.jpg 640w,
            /static/inline-examples/images/hummingbird-narrow.jpg 320w">
</amp-img>`

To make this work you need to have different sized images for different sized screens.

more about srcset [here](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)





---

## Testing

To test your amp page out for validation, first you need a server. You can get a host and push it live, but I would recomend checking things out locally first. The first step in local validation is firing up a server - you can use any method you want but here are a few easy ones:

1. Get a live server extension for your code editor. For example, VS Code has an extension aptly named `live server` - search for it in the extensions and follow the instructions for setting it up.
2. Have node installed? Navigate in the terminal to the folder your amp page is located in and type: `npx http-server` - after a few seconds to a minute or two (dependant on your connection) this will start a local server. Copy the address from the terminal (dont use control-c, it stops the server) - then open the page at the address provided.
3. You can use a web server solution like XAMPP - just dl, install then start the apache module - put your AMP page in a folder in the htdocs xampp folder and navigate to localhost/"folder name"

Once a server is serving up your page, open up the browser tools, navigate to the console panel then add `#development=1` to the url and reload the page (ex localhost:8080#development=1) - any validation errors will show in the console. Once you are all clear you should get the message "AMP validation successful." - congrats! Your AMP page is now ready for hosting!