React props
0. Basic components
Start with your files from the last task of the 0x01. React intro project

Instead of creating new elements, we’re going to create components to split the project. The App.js is going to become the main entry point, the shell, for every component in the app.

Create a Header component
Create a new folder Header:

Move the code of the header from the App.js to a new file Header.js
Move the css code, related to the header, of the App.css to a new file named Header.css
Create an empty Header.test.js. We’ll add tests for it later.
Create a Footer component
Create a new folder Footer:

Move the code of the footer from the App.js to a new file Footer.js
Move the css code, related to the footer, of the App.css to a new file named Footer.css
Create a Footer.test.js, we will add the tests later
Create a Login component
Create a new folder Login:

Move the code of the login section from the App.js to a new file Login.js
The code should be wrapped in a React Fragment
Move the css code, related to the login, of the App.css to a new file named Login.css
Create a Login.test.js, we will add the tests later
Modify the shell
In the index.js:

Remove the root-notifications
Remove the Notifications import
In the App.js:

Import Notifications, Login, Footer, and Header
Add the new Notifications component before the div.App element
Wrap Notifications and the rest of the div.App within a React Fragment
In the div.App, replace the header code by the new Header component
In the div.App-body, replace the login code by the new Login component
In the div.App-footer, replace the footer code by the new Footer component
In the App.test.js:

Most tests will fail, only keep the one testing that the component renders without crashing
Requirements:

At this point, reloading the App should display the exact same page as the last task
The console in your browser should not show any error or warning

1. Write the tests for each component
To develop your tests faster, you can watch them. The test suite will run for every change you make:

Add the following script to task_1/package.json: "test-watch": "jest --watch"
Run your suite using npm run test-watch
Header.test.js
Import your new Header component within the test, and write two checks:

Shallow render the Header component to verify it renders without crashing
Verify that the components render img and h1 tags
Login.test.js
Import your new Login component within the test, and write two checks:

Shallow render the Login component to verify it renders without crashing
Verify that the components renders 2 input tags and 2 label tags
Footer.test.js
Import your new Footer component within the test, and write two checks:

Shallow render the Footer component to verify it renders without crashing
Verify that the components at the very least render the text “Copyright”
App.test.js
Modify the App.test.js file, and add four checks:

It should contain the Notifications component
It should contain the Header component
It should contain the Login component
It should contain the Footer component
Requirements:

At this point, running the test suites, should show:


2. Split the Notifications component
2.1. Create a NotificationItem.js
The Notifications component is repeating the same tags a lot. It will be hard to maintain and reuse. Let’s create a component to support the li generation.

Create a new component named NotificationItem:

it should render a li tag
the component accept three properties (type, html, and value)
type should be rendered with the data-notification-type attribute
value should be rendered within the tag
html should be rendered with the dangerouslySetInnerHTML attribute
Create a NotificationItem.test.js
Every component should be tested. Create a new NotificationItem.test.js file, and add the following checks:

Verify that the basic rendering of the component works without crashing
Verify that by passing dummy type and value props, it renders the correct html (for example: type=“default” and value=“test”)
Verify that by passing a dummy html prop, it renders the correct html (for example: html={{ __html: '<u>test</u>' }})
Modify Notifications.js
Import the new NotificationItem component in the Notifications.js file and replace the <li> tags with NotificationItem components.

Modify Notifications.test.js
Modify the Notifications.test.js file to change one of the check:

Instead of testing if the component renders li, check that the component renders NotificationItem elements
Add a test to verify that the first NotificationItem element renders the right html (note: this is usually not the best way to write tests, but sometimes necessary when you don’t control the child component)
Requirements:

At this point, reloading the App should display the exact same page as the last task
The console in your browser should not show any error or warning
Running the test suites, should show:

3. Checking the application using the React extension
Using the React extension in Chrome:

Modify the type of the first NotificationItem to change from “default” to “urgent”. The first notification should change color to red, take a screenshot
Profile the load of the application and note which Component is the longest to render after App, take a screenshot


