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

## What is CORS and how do you handle it in web applications ?
CORS (Cross-Origin Resource Sharing) is a security feature implemented in web browsers that controls how resources are requested from a different domain (origin) than the one from which the website is being served. By default, browsers block cross-origin requests to prevent malicious websites from making unauthorized requests to a different domain on behalf of the user. It allows the server to specify which domains are permitted to access its resources and which HTTP methods and headers are allowed during the cross-origin request.

### How to handle CORS in web applications?

1. **Server-Side Configuration**: The most common way to handle CORS is to configure the server to include appropriate headers in its responses.
   - **`Access-Control-Allow-Origin`**: This header specifies which origins are allowed to access the resource. It can be set to a specific domain (e.g., `https://example.com`) or to `*` to allow access from any origin.
   - **`Access-Control-Allow-Methods`**: Specifies which HTTP methods (e.g., `GET`, `POST`, `PUT`, `DELETE`) are allowed when accessing the resource.
   - **`Access-Control-Allow-Headers`**: Lists the allowed custom headers that can be sent in the actual request.
   - **`Access-Control-Allow-Credentials`**: Indicates whether credentials (such as cookies) can be sent with the request. This must be explicitly allowed by setting it to `true`.

2. **Handling Preflight Requests**: For certain types of requests, such as those with custom headers or non-simple methods like `PUT` or `DELETE`, the browser first sends an **OPTIONS** request to the server to check if the actual request is permitted. This is called a **preflight request**. The server should respond with the appropriate CORS headers in response to the preflight request.

3. **Client-Side Adjustments**: In some cases, changes to the client may be necessary, such as ensuring that credentials (cookies, authentication headers) are only sent if the server permits it by setting `Access-Control-Allow-Credentials`.

4. **CORS Proxy**: If you don’t have control over the server, a common workaround is to use a **CORS proxy**. This proxy sits between the client and the server, making the request on the client’s behalf and returning the result, thus bypassing the browser's CORS restrictions.

### Example in Express.js (Node.js):

```javascript
const express = require('express');
const cors = require('cors');
const app = express();

// Enable CORS for all routes
app.use(cors({
  origin: 'https://example.com', // or '*'
  methods: ['GET', 'POST', 'PUT', 'DELETE'],
  allowedHeaders: ['Content-Type', 'Authorization'],
  credentials: true
}));

app.get('/data', (req, res) => {
  res.json({ message: 'CORS enabled!' });
});

app.listen(3000, () => {
  console.log('Server is running on port 3000');
});
```

This approach ensures that your application complies with CORS policies and allows secure cross-origin requests when necessary.

## What Strategies would you employ to Optimize the Performance of a Web Application ?

1. **Code Optimization**: 
   - Minimize and compress JavaScript, CSS, and HTML files.
   - Remove unused code and libraries (e.g., use tree-shaking for JavaScript).
   - Optimize loops and reduce unnecessary computations.

2. **Lazy Loading and Code Splitting**:
   - Load only essential resources first and defer non-critical assets (lazy loading).
   - Split large code bundles into smaller, more manageable chunks that load on demand.

3. **Caching**:
   - Use browser caching (with `Cache-Control` headers) to store static resources.
   - Implement server-side caching with tools like Redis or Memcached to store frequently accessed data.

4. **CDN (Content Delivery Network)**:
   - Serve static assets (images, CSS, JavaScript) from a CDN to reduce latency and improve load times by distributing content closer to users.

5. **Image Optimization**:
   - Compress images and use modern formats like WebP.
   - Serve responsive images with appropriate resolution based on the device (e.g., `srcset`).

6. **Reduce HTTP Requests**:
   - Combine CSS and JavaScript files where possible.
   - Use inline SVGs for small images/icons to reduce requests.

7. **Database Optimization**:
   - Use indexing and efficient queries to reduce database load.
   - Implement database connection pooling to manage resources effectively.

8. **Asynchronous Operations**:
   - Perform long-running tasks asynchronously (e.g., background processing) to avoid blocking the main thread.
   - Use non-blocking code patterns (e.g., `async`/`await` in JavaScript).

9. **GZIP/Compression**:
   - Enable GZIP or Brotli compression on the server to reduce the size of transferred files.

10. **Monitoring and Profiling**:
   - Use performance monitoring tools (e.g., Lighthouse, Chrome DevTools) to identify bottlenecks and optimize the application based on real-world usage.

## What are the SEO challenges with SPA's and how can they be addressed ?
SPAs often struggle with SEO as content is dynamically loaded, making it hard for search engine crawlers to index. 

### Solutions include:
- **server-side rendering (SSR)**,
- **Using the History API to update URLs for different views** and 
- **Leveraging pre-rendering services or static site generations (SSG)**.

## Describe the CSS box model and how CSS properties related to it affect layout ?
The CSS box model consists of four areas: **content, padding, border, and margin**.
These layers affect the total size and spacing of an element on the page.

Understanding this model is crucial for precise layout control, as it determines how elements are sized and how they interact with each other in the document flow.
