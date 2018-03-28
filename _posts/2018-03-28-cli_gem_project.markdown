---
layout: post
title:      "CLI Gem Project"
date:       2018-03-28 17:33:19 -0400
permalink:  cli_gem_project
---


Hi everyone!

Finally - a portfolio project under my belt!

I have to admit, I saw the requirements for this project and thought, there is absolutely no way I'm ready to do all of this by myself. However, after just under two weeks of frustration, patience, and finally, success, I am beyond proud of myself for completing this project.

The idea for my project was to generate a list of available cats from a real cat rescue, and to then offer more information about each cat with the option of making an appointment, or exiting the shelter.

Initially, I struggled tremendously with getting started. I had to review all of the Github sections to refresh my memory on adding, committing, and pushing changes. I also could not figure out how to bundle the gem without it being under a bigger folder, so I just went with it and got started.

I began by studying the `daily-deal` walkthrough, which I swear I watched about 5 times. I used Avi's advice for setting up the environment, which really helped to understand how my files would interact.

I knew I wanted to outline my project as needing the following:
* a CLI file, `cli.rb`
* a scraper/object generating file, `cats.rb`
* a bin file to start the program, `bin/adopt`
I created the files and began writing my code.

I started defining each class, and I began the real bulk of my code within the `cats.rb` file, where I introduced the Nokogiri gem and attempted to scrape.  This is where the frustration began! I really wanted to accomplish the scraping by myself, but I needed a one-on-one session to help me step away and see why I wasn't scraping what I needed. Thankfully, I got more specific with my scraper and was able to get the attributes for each cat:

```
*doc = Nokogiri::HTML(open("http://ws.petango.com/webservices/adoptablesearch/wsAdoptableAnimals.aspx?species=All&sex=A&agegroup=All&location=&site=&onhold=A&orderby=name&colnum=4&css=https://ws.petango.com/WebServices/adoptablesearch/css/styles.css&authkey=uqn3fk5upf1ol62utcer2x7b0sfg42ytj6j51sefh01e5u64k6&recAmount=&detailsInPopup=No&featuredPet=Include&stageID="))
*   doc.css(".list-animal-info-block").each do |catbio|
*     cat = self.new
*     cat.name = catbio.css(".list-animal-name").text
*     cat.gender = catbio.css(".list-animal-sexSN").text
*     cat.breed = catbio.css(".list-animal-breed").text
*     cat.age = catbio.css(".list-animal-age").text
*     @@all << cat
*   end
*end
```

Next, I knew I would have to put all of my cat instances into a class variable, `@@all`, which would then be accessed by my CLI to print a list of all cats. Here is the partial code from my CLI file that returned a numbered list of cats with their names: 

```
* def list_cats
*     puts "Today's Available Cats"
*     @cats = AdoptACat::Cats.all
*     @cats.each.with_index(1) do |cat, i|
*     puts "#{i}. #{cat.name}"
* end
* end
```

To then access more information about the cat, I knew I would have to match either the index to user input, or the cat's name to the input. Since there were multiple cats with the same name, it only made sense to use the index since every cat has a different number and is identifiable that way. This was the code I used to retrieve more information:  

```
*   def more_info
*     puts "Please enter the number of the cat you'd like more information about:"
*     input = gets.strip
*     @cats.each.with_index(1) do |cat, i|
*     if input.to_i == i
*     puts ""
*     puts "#{i}. #{cat.name}"
*     puts "Age: #{cat.age}"
*     puts "Breed: #{cat.breed}"
*     puts "Gender: #{cat.gender}"
*     puts ""
*   end
* end
* end
 ```

Now when a cat's number is entered, it returns the cat's name, age, breed, and gender, which we scraped from the cats file in the above code.

At first, my CLI kept creating the full list of cats over and over, since I called my `#create` method within my list_cats method. I knew I had to move it somewhere where it would only be called once - in `bin/adopt`, right before `bin/adopt` runs `AdoptACat::CLI.new.call`.

After much frustration, I was able to get my program fully working today! It does not run in circles, and it returns the list of cats just how I wanted it to. 

I learned soooo much from the beginning to the end of this project, and it really reinforced so much of OO Ruby that I wasn't understanding so well before. 

Thank you to everyone who gave me advice for this project - please see my video walkthrough for a better visual as well as instructions to install my gem! [https://youtu.be/EL0WoJkaofE](http://)

Best,
Elle


