# AMP Local Listing Landing Page

This is based on a project I originally built as a proof of concept while working at an agency [here](https://generationsbeyond-com.cdn.ampproject.org/c/generationsbeyond.com/clients/amp/), which itself was modled after an info graphic from the "Pefect local landing page", an article found [here](https://www.bowlerhat.co.uk/perfectly-optimised-local-landing-page/) and based on this:

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

## 5.
