---
layout: post
title:      "A Real Challenge with Rails"
date:       2018-08-04 22:52:46 +0000
permalink:  a_real_challenge_with_rails
---


Never have I ever learned so much in a matter of just weeks. Wow.

The Rails Portfolio Project was definitely the hardest thing I had to do so far on my coding journey. It was such a culmination of every concept learned so far, and it took many hours of frustration to get it done in a way that I felt really good about.

The idea for my Rails app is essentially an admin login for "Teachers of Flatiron High School." Teachers can log in and add students to their roster, and add and update grades for each student.

Originally, I planned on having four models; Teacher, Student, Course, and Grade. The students would be enrolled in a course, and that would be my nested route. However, after working on the app and developing these associations, I realized that with a student having many grades, it would make the nested route three levels deep which I wanted to avoid. 

I also realized that by installing Devise into my app,  my teacher model would have to become a User model. I tried to work around this, but changing every method (i.e. authenticate_teacher!) and my database to reflect my Teacher model just became confusing. For the sake of installing Devise for the first time in any app, I decided to change my teachers table into a users table.

My app then became three models - Users, Students, and Grades. The grades would be a nested route under students, and this made the associations much more simple and realistic.

I then added a little bit of formatting to my views, trying to touch on my HTML and CSS skills as well. I also felt like I learned so much from writing the code for my views, because it really solidified how to display data and associated data, as well as forms and everything that goes along with them. I used partial views with my forms, and one of my finishing touches was my form validations.

I loved working on this project because I really had to catch every little detail. I ran into so many errors, but having these errors meant I was constantly problem solving and using the concepts I've learned to come up with solutions. I felt really proud of this, because I never felt like there was a problem I couldn't solve. 

I referenced so much documentation for this. I read pretty much every tutorial or article about Devise and Omniauth, as well as many, many other previous labs so I could study the different ways to accomplish something and customize that to how I wanted.

All in all, the Rails project took me much longer to acccomplish than any other project, however it is the one I am most proud of so far <3

