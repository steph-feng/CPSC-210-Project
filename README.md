# Restaurant Finder: CPSC 210 Project

This application stores restaurants and organizes them based on the users' needs. 
Any casual restaurant-goer can input a restaurant and its characteristics such as 
a rating, pricing, hours, and cuisine into a customized collection. The user can then search for a restaurant in any 
collection based on its characteristics. The application can be tailored to the individual, and in turn used by 
any person looking to systematically organize their next meal.

This project interests me because my favourite thing about Vancouver is the number of restaurants to choose 
from. At the same time, I am indecisive and forgetful of where I've enjoyed eating at. This application will solve 
both problems, allowing me to save, categroize, and search for the next restaurant to reccomend or eat at.  

# User Stories
- As a user, I want to be able to add a restaurant to a collection.
- As a user, I want to be able to remove a restaurant from the collection.
- As a user, I want to be able to rate a restaurant on a scale of 1 to 10.
- As a user, I want to be able to add a restaurant's open hours.
- As a user, I want to be able to add the cuisine a restaurant serves.
- As a user, I want to be able to add the pricing of a restaurant on a scale of $ to $$$.
- As a user, I want to be able to find a restaurant that is open at the time I am using the application.
- As a user, I want to be able to find a restaurant that is open at a given time.
- As a user, I want to be able to sort a collection of restaurants based on some criteria, such as pricing or rating.
- As a user, I want to be able to filter a collection based on some criteria, such as pricing, rating, or cuisine.
- As a user, I want to get a random restaurant recommendation from a collection.
- As a user, I want to have the option to load the state of my restaurant collection from file.
- As a user, I want to have the option to save the state of my restaurant collection to file.

# Phase 3: Instructions for Grader 
- You can generate the first required action related to adding Xs to a Y by clicking on the button labelled "Add" on the
  home page. This lets the user add a restaurant and its details to the collection.
- You can generate the second required action related to adding Xs to a Y by clicking on the button labelled "Find" on 
  the home page. Next, click on the button labelled "Display Restaurants in Collection" to view all the restaurants in the collection,
  in other words, to display all the Xs that have been added to a Y.
- You can generate an action related to those Xs and Ys by clicking on the button labelled "Find" and then clicking on the 
  button labelled "Modify Existing Restaurant in Collection" to edit a restaurant's details.
- You can generate a second action related to those Xs and Ys by clicking on the button labelled "Find" and then clicking on the
    button labelled "Sort Restaurant Collection" to sort the restaurants by rating in descending order or by pricing in ascending order
  depending on the selected menu item.
- You can generate a third action related to those Xs and Ys by clicking on the button labelled "Find" and then clicking on the
    button labelled "Remove a Restaurant from the Collection" to remove a restaurant from the list.
- You can generate a fourth action related to those Xs and Ys by clicking on the button labelled "Find" and then clicking on the
    button labelled "Get a Random Restaurant Recommendation" to obtain a random restaurant from the list.
- You can locate visual components by clicking on the "Load" button or the "Save Button" on the home page. You can also
  click on the "Find" button followed by the "Get a Random Restaurant Recommendation" button to view a third visual 
  component.
- You can save the state of my application by clicking on the "Save" button on the home page.
- You can reload the state of my application by clicking on the "Load" button on the home page.

# Phase 4: Task 2
Created a new restaurant named: Nook\
Added a restaurant named Nook to the collection.\
Created a new restaurant named: Sura\
Added a restaurant named Sura to the collection.\
Displayed all restaurants currently in the collection.\
Sorted restaurant collection by rating from high to low.\
Sorted restaurant collection by pricing from low to high.\
Provided a random restaurant recommendation.\
Displayed all restaurants currently in the collection.\
Removed a restaurant named Sura from the collection.\
Displayed all restaurants currently in the collection.

# Phase 4: Task 3
To refactor this design, I would first apply the Singleton Design Pattern to the RestaurantManagerApp class.
As seen on the UML Design Diagram, 11/12 concrete classes (not including the RestaurantManagerApp class itself) in the GUI 
package are associated with the RestaurantManagerApp class. When investigating the code, I notice that the same instance of 
RestaurantManagerApp is passed as a parameter to each of these associated classes. Only one instance is necessary
because each action and its associated panel is displayed on the same JFrame that is held by the RestaurantManagerApp instance. 
Thus, applying the Singleton Pattern will enable global access to one and only one RestaurantManagerApp instance. This will
allow more convenient access to the RestaurantManagerApp instance while ensuring that only one instance is constructed 
during program runtime. Moreover, applying this design pattern would reduce coupling because classes would no longer be 
constantly associated with RestaurantManagerApp. While there will be dependencies between RestaurantManagerApp and the 
concrete classes in the GUI, these dependencies only occur when certain methods are called. Thus, this allows the classes
in the GUI package to be less semantically coupled with RestaurantManagerApp, thereby improving the structure of this design.

\
Next, I would refactor the DisplayPanel, SortPanel, RemovePanel, and ShowRestaurantsPanel classes such that the 
ShowRestaurantsPanel is a superclass that is extended by the SortPanel and RemovePanel classes. In turn, the DisplayPanel class
could then be removed completely. Currently, the ShowRestaurantsPanel is responsible for displaying all the restaurants in any 
collection it is a given. This function is important to the DisplayPanel, SortPanel, and RemovePanel classes, as they all 
present a collection of restaurants to the user after some action is performed. In the design thus far, SortPanel is 
associated with ShowRestaurantsPanel to lay out the sorted restaurant collection, while RemovePanel is dependent on DisplayPanel 
to lay out the altered restaurant collection. This approach to displaying restaurants is inconsistent 
among the four classes and there is substantial duplicate code. Furthermore, there is weak cohesion in the SortPanel and 
RemovePanel classes because they are responsible for both displaying the restaurants and sorting/removing restaurants.
By creating a new type hierarchy, the repeated function of displaying restaurants can be abstracted, 
enabling subclasses to better follow the Single Responsibility Principle. In addition, by passing the current collection of restaurants
into ShowRestaurantsPanel, the DisplayPanel class would not longer be needed. 
After this refacting, each class would be better centered around one cohesive concept.


# Attribution
- Drumroll Please GIF: https://media0.giphy.com/media/Xg6MhjKhDwoBwni45d/giphy.gif?cid=ecf05e471jc6inxc0thuin9wyt6hlbs6cqecyt3ql5ejw7po&rid=giphy.gif&ct=g
- All Done GIF: https://media1.giphy.com/media/l0Iyl55kTeh71nTXy/giphy.gif?cid=ecf05e47nets0b9i9eq41s79bvwvozum0u3leq3qh8lqpv4n&rid=giphy.gif&ct=g
- I Did It GIF: https://media4.giphy.com/media/l41Ye5dhLPqILtT2w/giphy.gif?cid=ecf05e47qh5t82tcwe9jjrmhsprr3dbyjoumi9mi0qt94vnr&rid=giphy.gif&ct=g
