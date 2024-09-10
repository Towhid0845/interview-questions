## What is front-end web application and why frontend frameworks exist ?
Frontend is all about **Handling Data** and **Displaying Data** in a user interface. User interface needs to stay in sync with data. Because the UI always need to display the current state of data (Piece of data = Piece of state). 
## Why Frontend Frameworks Exist:
- Frontend frameworks exist because ** keeping a user interface in sync with data is really hard and a lot of work**. Frontend frameworks(React, Vue, Angular, etc different approaches but same goal) solve this problem and take hard work away from developers. 
- They enforce a **"correct"** way of sturcturing and writing code (therefore contributing to solving the problem of "peaghetti code").
- They give developers and teams a consistent way of building frontend applications

## The rise of single page application.
Before 2010, all websites always used to render on the server side. On server side rendering, a website is basically assembled in server/backend based on data and templates. The resulting HTML, CSS, and JS code send to the client side to the web browser that requested the page. The browser then take this code and execute to the screen.
Now, try to understand the senario of the picture bellow: 

So, Keeping UI and data in sync would be **virtually impossible with just vanilla JavaScript**.
### Reasons:
1. It requires lots of **DOM Manipulation and Traversing**
2. Data(State) is usually **stored in thd DOM** and then, shared accross entire app whice is very hard to reason and bug.

## How would you implement a design that needs to be resonsive accross various devices ?
Utilize CSS media queries to apply different styles based on device characteristics like width, height, or orientation. Employ a fluid grid layout and use relative units (em, rem, %) instead of pixels to ensure elements scale proportionally.
