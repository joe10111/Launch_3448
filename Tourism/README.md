# Launch Mod 3 Week 2 Assessment

## Questions (10 Points)

1. Define MVC and explain the purpose of each of the three parts of this pattern.
	MVC is shorthand for Model, View, and Controller. MVC is a way of organizing your code into distinct locations in your projects file structure so that only certain systems in code are talking to the correct system. 
	
2. Explain the difference between the **New** route and the **Create** route.
	A **new** route in context of MVC refers to the URL routes that map incoming requests to certain action methods that have been defined in a corresponding controller. 
	A **create** route is not a predefined route but is the route that handles submission of forum data for creating a new recorded in the database.  

4. List all of the RESTful routes for the `employee` entity. Make sure to include the Route Name, Path, and HTTP Method for each of the routes. (2 points)
- Route Name: Index
	- URL Path: /employees
	- HTTP Type: Get
- Route Name: Show
	- Path: /employees/{id}
	- HTTP Type: Get
- Route Name: Create 
	- Path: /employees
	- HTTP Type: Post
- Route Name: Update
	- Path: /employees/{id}
	- HTTP Type: Put
- Route Name: Delete
	- Path: /employees/{id}
	- HTTP Type: DELETE
</br>
For the following three questions, explain both how to fix the error/bug and why the part of the code that was broken is important. (2 points each)

4. 
<img width="1213" alt="Screenshot 2023-06-13 102204" src="https://github.com/turingschool/launch-curriculum/assets/11747682/f37c233d-e7aa-483e-9f75-7c9b111811e5">
A: On line 8 in the file `index.cshtml` you can see the expectation thrown is telling us that the object refence dose not exist in the current scope. 
This made me initially look for code in the `HotelController.cs` that was named incorrectly or not being executed.
On line 20 in `HotelController.cs` you can see the view is being returned but having no information passed into it. 
Meaning when we try to loop through the Model it will not have any information in it. 

5.
<img width="1245" alt="Screenshot 2023-06-13 102555" src="https://github.com/turingschool/launch-curriculum/assets/11747682/87c9fbf7-de63-4580-9b36-8632df27b91b">
A: In the above photo you can see in the solution explore under `Views/Hotels` the view index file is named `indexes` instead of `index`. 
So when the controller goes to go find`Views/Hotels/Index.cshtml` it cant because the actual path is `Views/Hotels/Indexes.cshtml`.
So as far as the controller knows there is currently no view for it to display for `Hotels/Index`. 

6. 
<img width="1238" alt="Screenshot 2023-06-13 102856" src="https://github.com/turingschool/launch-curriculum/assets/11747682/a39b525d-ae05-463f-b724-be68aa70148c">
A: In the above photo on line 11 `hotel.Name` and `hotel.location` are being called with out the `@` symbol. 
This symbol in `cshtml` allows us to references a c# object with its data collection that we pass into the view from the controller. 
The `@` is important in this context because with out it you will get a plain text version of your object call. 

## Exercise (10 Points)

Make sure to first run `update-database` to populate the `Tourism` database used by this application.

This application already has the `Index` route for States.

Your task is to do the following:
1. Add the `Show` RESTful route to display the name and abbreviation for a particular state.
1. Add a test for your new `Show` route in the `StateCRUDTests.cs` file.