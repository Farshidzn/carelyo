
1.Long pulling is used for getting information in a specific time from back-end. 
*a) 
*client:
*function poll() {
*  var xhr = new XMLHttpRequest();
*  xhr.open('GET', '/poll');
*  xhr.onload = function() {
*    if (xhr.status === 200) {
*      console.log(xhr.responseText);
*      poll();
*    }
*  };
*  xhr.send();
*}
*poll();
*server:
*const http = require('http');
*const server = http.createServer(function(req, res) {
*  if (req.url === '/poll') {
*    res.writeHead(200, {'Content-Type': 'text/plain'});
*    let i = 0;
*    const interval = setInterval(function() {
*      res.write(`${i++}\n`);
*    }, 1000);
*    req.connection.addListener('close', function() {
*      clearInterval(interval);
*    }, false);
*  }
*});
*server.listen(3000);
*b) WebSocket is the other alternative. It’s a TCP connection between client and the server.
*c) Positive: minimizing the latency in server-client message and processing resources. Negative: connection establishment and caching 
2. server can access the client’s cookies but not data storage. Cookies are smaller in size than local storage. Cookies expire but local storage doesn’t have expire *time. 
3. Get method, to retrieve data. PUT method creates a resource or replace a target resource. Delete method, deletes the specified resource. Post method sends data to *server. 
4. An array is a collection of data that is stored in a sequence of memory and we can access them by calling the index number. We can store integer, float, string and *Boolean in an array. Object is used to represent a ‘thing’. It can be anything like cars, person etc.
5. React is JS library for building client side, based on UI components.
*a) hooks help you use react without classes and mange React state
*b) don’t call hooks inside loops or conditions because to make sure that hooks are called in the same order each time a component renders. Don’t call hooks from JS *function to ensure that all stateful logic in a component is clearly visible form its source code. Only call hooks at the top level: Hooks should only be called at *the top level of your functional component, not inside loops, conditions, or nested functions
*c) JSX stands for JavaScript XML. JSX allows us to write HTML in React. JSX makes it easier to write and add HTML in React.
*d) variables that are available through a global process. env Object. That global Object is provided by your environment through NodeJS
*e) Props are arguments passed into React components.
*f) with useState. const [state, setState] = useState(“text”)
*g) We can return only one element.
*H)
* i. import React from 'react';
*function LoginButton(props) {
*  return (
*    <button onClick={props.onClick}>
*      Login
*    </button>
*  );
*}
*export default LoginButton;

*   import React, { useState } from 'react';
*import LoginButton from './LoginButton';

*function LoginForm() {
*  const [isLoggedIn, setIsLoggedIn] = useState(false);
*  function handleLoginClick() {
*    setIsLoggedIn(true);
*  }
*  return (
*    <div>
*      {isLoggedIn ? (
*        <p>You are logged in</p>
*      ) : (
*        <LoginButton onClick={handleLoginClick} />
*      )}
*    </div>
*  );
*}
*ii.
*import React, { useState } from 'react';

*function GroupComponent() {
*  const options = ['React', 'LIA', 'Carelyo'];
*  const [selectedOption, setSelectedOption] = useState(options[0]);

*  function handleOptionChange(event) {
*    setSelectedOption(event.target.value);
*  }

*  return (
*    <div>
*      <form>
*        {options.map(option => (
*          <div key={option}>
*            <input
*              type="radio"
*              id={option}
*              name="group"
*              value={option}
*              checked={selectedOption === option}
*              onChange={handleOptionChange}
*            />
*            <label htmlFor={option}>{option}</label>
*          </div>
*        ))}
*      </form>
*      <p>Selected option: {selectedOption}</p>
*    </div>
*  );
*}
7. 
*a) TypeScript extends JavaScript and improves the developer experience. It enables developers to add type safety to their projects.
*b) positive: it’s easier to debug and writing code. negative: You have to write more code and it takes more time.
*c) let var1 = "Hello";
*var1 = 10;
*console.log(var1);
*let var1: string = "Hello";
*var1 = 10;
*console.log(var1);
9.
*a) git is a version control system and it’s used for changes in files.
*b) Git hooks are scripts that run automatically every time a particular event occurs in a Git repository
*c) "Add session expiration countdown to navbar for logged in users"
10.
*a) positive public relation and better SEO
*b) poor text and image, too many navigation links and using Non-descriptive Links*





