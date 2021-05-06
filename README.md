# AdvancedPOM
Here we put together some guidelines on how to use page object model for large scale complex projects. 
We have modified page object model methodology to achieve better maintenance and easy scalability for large scale applications. 

<h2>Guidelines to design large scale automation with advances page object model pattern</h2>

**This methodology will provide following benifits:**
*	Provide better interface to interact with the page DOM objects.
*	Breakdown complex page classes in to small manageable sections.


<h3>Consider following set of guidelines when designing large scale automation project:</h3>
1.	Keep the web page classes in the same hierarchy as in the application.
 
 * To make the pages easy to locate put the pages on the same hierarchy as in we find in the application UI.
 
 
**Here is the example:** [Robotize Facebook](https://github.com/IRobotizeInternet/Facebook) Create New Listings page
 
 As shown in the folder heirarchy the `Create New Listing` goes under the `Marketplace` it fulfill the first set of guideline.
 
![image](https://user-images.githubusercontent.com/83523058/117238803-67c35200-ade2-11eb-8021-76cb78b23b2d.png)


 
2.	Each application page should be divided into manageable sections, such as header, left menu, main section etc. 
Often pages can be simple as user login page or complex as Facebook homepage. When developing project from scratch or updating an existing one, try to see the big picture and understand how entire application designed to better breakdown each page into a manageable sections. 

**Here is the example:** [Robotize Facebook](https://github.com/IRobotizeInternet/Facebook/tree/master/Robotize.BLL/App/LoggedIn/Pages/Watch) watch page is divided in to three sections.
* Header
* Menu Items
* Feed

![image](https://user-images.githubusercontent.com/83523058/117239249-46af3100-ade3-11eb-9e18-45b47f2d1a67.png)


3.	One-to-One mapping between application page and automation page (Code).
* Each DOM Element in the application page should correspond to only one DOM property in automation code library.
* We cannot emphasise enough to ensure there should be only one and only one xpath for a given DOM object. 

**Here is the example:** [Robotize Facebook](https://github.com/IRobotizeInternet/Facebook/blob/master/Robotize.BLL/App/LoggedIn/Pages/Home/PageHome.cs) Home page

![image](https://user-images.githubusercontent.com/83523058/117241075-25e8da80-ade7-11eb-8e7b-ce571215d252.png)

4.	All DOM elements of the page should be implemented as properties of the UI page. 
For instance, a button should be implemented as a Button property. In order to click it, one would access that property and perform one of the available click actions available for that Button class. By returning the DOM element as a property, it will provide more options to the caller of the property.

**Above guidelines are used for develop following projects:**
* [Robotize Facebook](https://github.com/IRobotizeInternet/Facebook)
