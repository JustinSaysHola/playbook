# Drupal

This chapter is about the Poetic process and ideology for engineering websites. We use Drupal as a way to provide upgradable, stable and powerful websites.

Being a Drupal developer at Poetic means you are entering into two families. The poetic family and Drupal family. We encourage you to be active in both!

## Recieiving the Design

First, get excited! This is an opportunity to learn and expand your knowledge while also creating something useful for human beings. When receiving a new site go to hansel and navigate to the clients designs, normally structured something like this:

Clients > Name of client > nameofclient.com > Designs > Originals

*See a designer if you cannot find the project.*

As a developer it is important for you to slow down and take the time to look at all the designs and begin mentally planning your attack. Diving into a project without thoroughly becoming antiquated with the design and structure will slow you down and lead to problems down the road. Slow down and pay attention to detail,
slow down and pay attention to detail,
slow down and pay attention to detail.

You have several missions at this point:

* Figure out all contrib modules needed and if any custom modules need to be coded.
* Find any inefficiencies in the design and bring these up with the designer and/or team lead.
* Identify all challenges that the design and project will have.
* Develop a game plan for solving all the challenges and how to structure the site.
* If anything goes outside the scope of the project bring it up with a leader.

Figuring these out are essential for not only eliminating challenges from the specific project but advancing your self as a developer.

## Choose Platform

The first thing you should do is casually scan the designs to figure out which platform you will be using for the project. For example if you scan the designs and find a “View Shopping Cart” link then this would be a clue that you would likely need an e-commerce platform.

## Analyze Design Elements

After you have chosen the appropriate platform now we want to go into deeper detail. Analyzing the design comprises of a careful “top to bottom, left to right” process. Each element must be examined and studied. We want to determine how each element will be solved in code whether it be using a block, template override, contrib module or custom module.

![](http://i.imgur.com/OICI3cM.png)

I begin by asking myself how this element will function in the site and what is the best solution to implement the design. Since the content here is unlikely to change I will decide to bake it in to page.tpl.php. This will reduce block clutter as I estimate that a site of this size will have a healthy amount of blocks. This solution could be revisited during the refactor phase but will most likely be an acceptable solution here.

![](http://i.imgur.com/57A8Llt.png)

The next element is the logo and I begin by asking myself what standards does this element demand? I know that this element should have 2 versions, one for normal screens and one for retina display so I need to plan accordingly. Knowing that the site logo can be implemented through the theme I google solutions for ‘drupal theme logo retina module’ to see if there is anything to solve this. I won’t spend more than 10-15 minutes searching for such a solution. There were no modules so I will plan on solving this by baking in a logo div in the page.tpl.php which will then have CSS solutions for loading the retina version on mobile.

An issue like this is a perfect example of a need for coding a module. Every site we do will likely need a normal and retina logo so a module would be awesome to have for this solution. You are a Drupal Dev so make it! Publishing a contrib module will make you look like a badass and will help the Drupal community as a whole.

![](http://i.imgur.com/Bp6dVq2.png)

Analyzing this next element we see functionality associated with e-commerce solutions. Now we must determine if this will be solved with contrib or custom modules. Drupal commerce is the standard contrib module for e-commerce but at this stage we want to make 2 checks. We want to check if Drupal Commerce can solve this design element and also make a quick google search to see if anything other than Drupal Commerce is a better choice. After searching through Commerce documentation we find that it can solve the elements here but didn’t find anything about wishlist. I searched ‘drupal commerce wishlist’ and found https://drupal.org/project/commerce_wishlist a contrib module that should solve this. At this point we want to look and see if this module exists on the platform. It does not exist on the platform so this must be addressed to the person who maintains the platform. We can place the module in the module folder with the site but it will not be upgraded ever if it is here.

We also want to check if there are any updates or upgrades to the platform. In this case there were upgrades not only to contrib modules but to the Drupal version. At this point we want to upgrade the platform so that it is up to date. You should be able to do this yourself, if not then bring it to the attention of the platform maintainer but why wouldn’t you know how to do this? This is a perfect example of being a part of the solution rather than a part of the problem. Every step that every dev makes on our team which creates clutter builds a future disaster. Your knowledge and self growth are an integral part of the team and as the old wisdom goes, a chain is only as strong as its weakest link. Learn about platforms and contribute to reducing clutter!

I also did some google searches to see if there were any alternatives to Commerce. There is Ubercart but upon doing a quick search find that it lacks customization and doesn’t have as much Drupal 7 support as Commerce. If we found another better solution we would want to discuss it with a team lead and figure out if we want to switch to it. You could find the next best thing! Be that person!

![](http://i.imgur.com/Sl8EbON.png)

Something that I noticed was that the entire top menu layout changes from the home page to the inner pages, the logo, menu, search, commerce controls and phone number CTA (call to action) move around. This will lead to extra developer time but seems to make no real benefit to the user/design. At this point we want to ask the designer for the reason for the difference. Every design element should have a purpose and reason and we want to find out the reason this design element was implemented in this way.

Upon consulting with our super awesome designer I found out that the top area on the home page is the default design for all the pages and that it wasn’t updated on the inner pages. This level of care and attention to detail BEFORE initial coding just saved us tons of time. We might have coded this in only to find out that the home page was the default design for all pages.

Also remember that our designers have poured their heart and soul into the designs and maybe even made a deal with the Devil to make it look perfect. Make sure to be extra careful how you ask your questions regarding design elements.

“Hey Karen, I noticed that these elements differ from page to page, what was your reason or purpose in making them different?”

-- they respond --

“If they were the exact same we could save maybe 2 hours of dev time do you still want to keep the elements different?”

If you feel there is still some sort of code disaster brewing from the design decision and the designer still insists on it then grab a leader and discuss it with them.

Continue carefully through the designs and plan out all solutions for the design. Do not rush or be careless but maintain a pride and consistency that a code poet would have. Your code is a reflection of you and you should be proud of it. As I continue I turn on modules and make decisions for each and every design element.

## Templates

Now we want to begin modeling our templates. This is the time to break out a pen and paper and begin sketching the sites pieces.

![](http://i.imgur.com/Ytfz8Ql.jpg)

Sketching the architecture of the design will help you conceptualize the proper way to code the template as well as increase your knowledge of the sites design.

What we strive for is to encompass all our designs pages while not making the page.tpl.php file a cluster. We don't want a template override for every content type.

Now we write modern markup in a template to serve the needs of the project.

## Content Types

After I believe I have accounted for every module that I will need I then make a list of content types I believe I will need. Remember that every content type should be singular because it is the blueprint by which we make nodes. An Event content type is used to create an event so logically this should be singular.

When we create a view it is so we can list off a series of nodes so the view would be called Events. If you are caught calling a content type with an incorrect plurality you will be forced to delete it and start over, shame on you! Also remember that all content types and views have descriptions, use these! Not only will it force your brain to better understand the purpose of the data but it will be nicer for anyone else working on the site later.

Review the design again and try to imagine what content pieces exist and how they will be organized into content types.

![](http://i.imgur.com/bddHvLv.png)

Looking at the above design we can see multiple image galleries. This design tells us that we will have a content type of Gallery and that this specific page will be a view of Gallery nodes.

![](http://i.imgur.com/5Zn9HAL.png)

We have another design which shows a page of videos. This would tell us that we will have a content type of Video and this is a Videos view.

However, we notice that both designs have similar styles and the content images and videos are very similar in what they are, which is Media. We can refactor our content type theory then to have a content type of Media and add a field to Media which will delineate whether or not it is an image or video. This way we have a cleaner and more linear process for the end user for creating Media.

Let us imagine how things could break or get kludgy. An end user could create a Media node and upload images and a video, maybe they think they can put both on one node. We want a solution to red rope them into success.

Ideally here we want a condition where we would only show the image upload field when Image is checked from the type feild or show a youtube field when Video is checked. Now we google "conditional fields" since we want fields which are conditional on the value of another. Our google search quickly shows https://www.drupal.org/project/conditional_fields.

Read the README.txt from the module, read the module page and documentation. I cannot stress this enough! Never just install and start clicking.

After I did that I found that we already have the module in our stack, turned it on and programmed the logic for the conditions. Now when someone creates a Media node they must choose a Media Type of Image or Video before they even see the fields for those types.

![](http://i.imgur.com/906QZx2.png)

![](http://i.imgur.com/ebWW5NW.png)

## Refactor!

Now go back and review the design. Again, go page by page and review if anything new stands out. Check your template and refactor the markup. Check your content types and make sure you have a content type that addresses each peice of content in the design. Refactor your content types, maybe you can remove one and combine it into another like we did above with Images and Videos. Go into each content type and compare the fields with the designs and refactor your fields.

It is super important to take your time here. The planning process shouldn't be rushed but instead relished as a stage of first evolution and then perfection. The next stage is writing any functional code (javascript etc) and custom drupal modules. If all the planning and architecture was done correctly then after the custom code is done the entire site will be ready for content and will function properly.

## More Functionality

After refactoring and cleaning up any kludge we jump back into functionality. For this project I need Drupal Commerce and instead of just jumping into creating stuff I instead pause and go read the manual. First I read the README.txt that comes with the module, this will sometimes cover what we need but often we will have to go read other documentation. After some google searches I found this https://drupalcommerce.org/user-guide/ which goes over all the details about using Drupal Commerce.

After reading this I begin testing and sketching out schemas for our architecture.

![](http://i.imgur.com/x5ucFt4.jpg)

After I am comfortable with Drupal Commerce and have a good idea about the structure then I go back and check the designs.

![](http://i.imgur.com/NZxeh6b.png)

Our design shows us that we should split the products into Guitars, Basses, Amps, Pro Audio and Accessories. We could even check out the old site and ask the designer for more information to verify that this is correct.

Next I would need to figure out all the feilds each type will need and then intergrate them into a content type.
