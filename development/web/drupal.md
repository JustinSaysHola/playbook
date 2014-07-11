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

I begin by asking myself how this element will function in the site and what is the best solution to implement the design. Since the content here is unlikely to change and has been constant for years (this is a legacy client with years of history with us) I will decide to bake it in to page.tpl.php. This will reduce block clutter as I estimate that a site of this size will have a healthy amount of blocks. This solution could be revisited during the refactor phase but will most likely be an acceptable solution here.

![](http://i.imgur.com/57A8Llt.png)

The next element is the logo and I begin by asking myself what standards does this element demand? I know that this element should have 2 versions, one for normal screens and one for retina display so I need to plan accordingly. Knowing that the site logo can be implemented through the theme I google solutions for ‘drupal theme logo retina module’ to see if there is anything to solve this. I won’t spend more than 10-15 minutes searching for such a solution. There were no modules so I will plan on solving this by baking in a logo div in the page.tpl.php which will then have CSS solutions for loading the retina version on mobile.

An issue like this is a perfect example of a need for coding a module. Every site we do will likely need a normal and retina logo so a module would be awesome to have for this solution. You are a Drupal Dev so make it! Publishing a contrib module will make you look like a badass and will help the Drupal community as a whole.

![](http://i.imgur.com/Bp6dVq2.png)
