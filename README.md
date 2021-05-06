# AdvancedPOM
Here we put together some guidelines on how to use page object model for large scale complex projects. 
We have modified page object model methodology to achieve better maintenance and easy scalability for large scale applications. 

Below are the following set of guidelines:

Following will be addressed in this page:
•	Provide better interface to interact with the page DOM objects.
•	Breakdown complex page classes in to small manageable sections.

Consider following set of suggestions when adding code to your automation project:
1.	Keep the web page classes in the same hierarchy as in the application.
 To make the pages easy to locate put the pages on the same hierarchy as in we find in the application UI.
2.	Each application page should be divided into manageable sections, such as header, left menu, main section etc. 
Often pages can be simple as user login page or complex as Facebook homepage. Try to see a big picture and understand how entire application designed to better breakdown the page into a manageable sections. 
For each page and its associated files (Menus, Main contents etc.) a folder will be created if it contains more than one section in it.
Here is the example:
Facebook home page divided in to three sections.
Header Menu
Left Menu
Page Feed

3.	One-to-One mapping between application page and automation page (Code).
Each DOM Element in the application page should correspond to only one DOM property in automation code library.

4.	All DOM elements of the page should be implemented as properties of the UI page. 
For instance, a button should be implemented as a Button property. In order to click it, one would access that property and perform one of the available click actions available for that Button class. By returning the DOM element as a property, it will provide more options to the caller of the property.

**Above guidelines are used for develop following projects:**
* [Robotize Facebook](https://github.com/IRobotizeInternet/Facebook)
