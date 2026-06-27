# Inventory Management App
The zip file in this repo contains an Android app that can be opened in Android 
Studio. 


*Q:* Briefly summarize the requirements and goals of the app you developed.
What user needs was this app designed to address?

*A:* The goal of this app is to aid small businesses in dealing with inventory
management. A large warehouse or corporation would likely need something more
robust than a simple mobile app, but for small shop owners, this could work
well. 

*Q:* What screens and features were necessary to support user needs and
produce a user-centered UI for the app? How did your UI designs keep users in
mind? Why were your designs successful?

*A:* There were really only 2 screens that were necessary for this project.
A login/registration screen, and the main inventory management screen. Users
don't want a convoluated experience with buttons all over the place. To address
this, I made my app as simple as possible. After logging in, there is a single
button on the screen that's used for both adding new items to the inventory,
and updating existing quantities of items in the database. If a user clicks on
a row, then the *Add Item* button becomes an *Update Item* button.

*Q:* How did you approach the process of coding your app? What techniques or
strategies did you use? How could those techniques or strategies be
applied in the future?

*A:* I like to separate components into related groups. For example, I created
a *DatabaseMgmt* class that managed all of the database operations in a high
level interface. This made it easy to add new items or update existing 
quantities. I also created an *InventoryRow* class that represents a row in the
database, which prevented me from having to do things like:
```java
String[] row = db.getRow(0);
int itemId = Integer.parseInt(row[0]);
String description = row[1];
int qty = Integer.parseInt(row[2]);
```
over and over again in my code.

*Q:* How did you test to ensure your code was functional? Why is this process
important, and what did it reveal?

*A:* An automated test would be the best approach, but I just manually tried
every edge case that I could think of such as signing up for an account with a 
blank username and password field, adding an item to the database with a 
description that already exists in the database, adding an item that doesn't
have a description, etc. Before deciding that the app was finished, I made sure
that I could create an account, login, load the inventory, delete an item, add
a new item, and update an existing item without issues.

*Q:* Consider the full app design and development process from initial
planning to finalization. Where did you have to innovate to overcome a
challenge?

*A:* Figuring out how to incorporate existing UI elements into new processes
was one way that I innovated processes. In my original design, there were 3 
screens. A login/registration screen, the inventory table screen, and a third 
screen where for actually inserting new data or updating existing data. The 
third screen had several buttons and fields. In the end, I was able to remove
the third screen completely and maintain the same functionality using only 2 
*EditText* components and single button that serves both as the add and update
button.

*Q:* In what specific component of your mobile app were you particularly
successful in demonstrating your knowledge, skills, and experience?

*A:* Probably the *DatabaseMgmt* class. I've made many classes like this 
before in previous apps. I find that it's always extremely helpul to create a 
database management class that can perform common operations for you, rather
than having to hard code several SQL queries all over your code base.


