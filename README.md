# Software 1 - Class Exercise 2
## Goals
- Create the base classes for the store.
- Interact with the classes by making some objects and running basic logic on them.
- Learn how to make a console app wait for certain input before exiting using a loop.

## Instructions
1. Create a new console app in Visual Studio.  Make sure to give the solution a good name and make sure you create the solution in place that you can find it later.
1. Add a class to your project called `Product`.  This class will be what's called a _base_ class or a _parent_ class.  This will be the most basic class that all product classes will inherit from.
1. Add the following _properties_ to your naew class.
   - Name - Type `string`
   - Price - Type `decimal`
   - Quantity - Type `int`
   - Description - Type `string`
1. Add another class called `CatFood`.  Make this class _inherit_ from the base class `Product`.
1. Give `CatFood` a few _Properties_.
   - WeightPounds - Type `double`
   - KittenFood- Type `bool`
1. Make another class called `DogLeash` and have it inherit from `Product` as well. Give it a the following _Properties_ 
   - LengthInches - Type `int`
   - Material - Type `string`
1. Now we want to get this conaole app to run until the user decides to end it.  We will do this by using a `while` loop.  Loops require 3 things: an inital condition, check in condition, and a change in condition.  Our inital condition is going to be our first input from the user.  Our check is what is in the while loop.  Our change is going to be what the user inputs after an action has been complete.  So, let's get started with the initial condion.
1. At the top of the files, add the following lines: `Console.WriteLine("Press 1 to add a product");` and below that add `Console.WriteLine("Type 'exit' to quit");`.
1. Add this line of code below what you added in step 11 `string userInput = Console.ReadLine();`.  This will get what the user enters before hitting enter.
1. Now add your while loop.  The condition in the loop should be something like this: `userInput.ToLower() != "exit"`.  We use the method `ToLower` just in case the user enters "Exit" instead of "exit".
1. Inside the brackets for the while loop, at the end, add this line `userInput = Console.ReadLine();`. This is our change in condition.  We will add code before this though, so it will make more sense after that. Add the instructions for the console app above that line again: `Console.WriteLine("Press 1 to add a product");` and `Console.WriteLine("Type 'exit' to quit");`. 
1. Inside of the while loop, above the what you added in the previous step, add an `if` statement.  This if statment will check the input of the user a second time to see if they wanted to add a product. We told them to enter "1" to add a product, so check for that in the if statment.  Remember, the input is a `string` type, not an `int`.
1. Create a new object.  It should be `CatFood` or `DogLeash` not the base class `Product`.  Note: remember to add a `using` statment so that the `Program` class knows where to find your class.
1. Since we don't really have a database, when we add a product, we're going to just create that object and print it to the console.  Use `Console.Write()` and `Console.ReadLine()` to get data from the user and then add it to the object you just created.  Since some of the types aren't going to match, you will need to convert them using the target types `Parse` method.  So to turn a string to an int, use `int.Parse()`.
1. To make printing the object easier, we'll use the `JsonSerializer` class.  You don't need to know all the ins and outs of how this works right now, but basically it will just convert our object to a json object.  Add the following line to your code: `Console.WriteLine(JsonSerializer.Serialize(dogLeash));`.  You will replace `dogLeash` with whatever you named your object.
1. Now, all you have to do is test it!  Run the application and see if everything works properly.