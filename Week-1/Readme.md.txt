1.When a user enters an URL in the browser, how does the browser fetch the desired result ? Explain this with the below in mind and Demonstrate this by drawing a diagram for the same.
•	a. What is the main functionality of the browser?
•	b. High Level Components of a browser.
•	c. Rendering engine and its use.
•	d. Parsers (HTML, CSS, etc)
•	e .Script Processors
•	f .Tree construction
•	g .Order of script processing
•	h .Layout and Painting

Before understanding how a Browser’s work its necessary to know what is URL, DNS a URL Stands for Uniform resource locator which provides a address that helps the web browsers to identify a specific page across internet.
As the websites are being hosted on the servers across the internet its very difficult to find them without the address each server is associated with a particular IP ,And Its Responsibility Of The Browser To Fetch The Content From That Server but as a user its difficult for us to remember such IP address ,That Where DNS (Domain Name system )comes to play it make the weird IP address into a user readable and flexible form. 
If we look in detail of the URL https://codesandbox.io/ https:// responds to the protocol mention the browser to transfer the data over a secure layer Codesandbox.io is the Domain name. 
A web browser takes URL as input the browser has to lookup for the DNS and identify the IP of the server associated with the DNS on which the site is being hosted and establishes a Secure connection with the server and transfer data over the TCP connection with either of the protocols(HTTP or HTTPS) and the Rendering Engine which is the most crucial part of the browser is responsible for displaying the content in structured form. 
A web browser has various functional components. Browsers also support storage mechanisms such as local Storage, Indexed DB, Web SQL and File System
 
Components of Browser and what is use of rendering Engine?
•	User Interface: That acts as a frontend to the user it consists of search bar, and other browser options Each browser has a different User Interface.
•	Browser Engine: Which acts a intermediate between the UI and the main component named rendering engine
•	Rendering Engine: The most crucial component that is responsible for display the web pages content on to the site, it first processes the HTML Or Xml structure then applies the CSS or JavaScript. Different browsers use different rendering engines, Web Kit is an open source rendering engine. The rendering engine will start parsing the HTML document and convert elements to DOM nodes in a tree called the "content tree". The engine will parse the style data, both in external CSS files and in style elements.
•	Networking: It is responsible for providing the security and maintaining privacy for safe and secure access of information over the network.
•	JavaScript interpreter: Helpful in parsing and execute JavaScript code.
•	Data storage:  This is a persistence layer. The browser may need to save all sorts of data locally, such as cookies.
 

 


What is Render Tree and How Script Execution Works?

While the DOM tree is being constructed, the browser constructs another tree, the render tree. This tree is of visual elements in the order in which they will be displayed. It is the visual representation of the document. A renderer knows how to lay out and paint itself and its children. The renderers correspond to DOM elements Non-visual DOM elements will not be inserted in the render tree. These are usually elements with complex structure that cannot be described by a single rectangle. For example, the "select" element has three renderers: one for the display area, one for the drop down list box and one for the button. Also when text is broken into multiple lines because the width is not sufficient for one line, the new lines will be added as extra renderers. Some render objects correspond to a DOM node but not in the same place in the tree. Floats and absolutely positioned elements are out of flow, placed in a different part of the tree, and mapped to the real frame.
 
How Script Execution works?
Once the HTML and CSS processing is done that browser starts downloading the JavaScript ,the browser is faster in downloading files, The JavaScript file is then interrupted, parsed, compiled ,The scripts are parsed into Abstract Syntax tree which are then parsed by interpreter that output's bytecode .This is how the JavaScript execution takes place.
Parsers?
Parsing is the process in which analyzing and converting of program into a interpreted format that is available at run time and parser parse’s tokenized input input to document building up to DOM

In simple terms Parsing is process in which the data chunk received over the network are converted into DOM ,CSSOM which is ten painted onto screen by rendering engine The DOM is exposed and manipulated by API'S in JavaScript ,If HTML'S Page received id greater than 14KB then HTML,CSS,JS must be processed
 
HTML Parser(DOM)
When a browser receive bytes of data that needs to be converted to DOM, the  following steps:
1.	1.First parse bytes into character
2.	2.Characters are converted into tokens by the tokenizer
3.	3.The tokenizer starts parsing each starting and closing tags and converts into nodes until it will end up into converting to DOM
CSS Parser(CSSOM)
The CSS object model us similar to DOM, the browser goes through each rule set of CSS electors creating a tree of nodes with parent, child, sibling relationships based on selection rules. Building CSSOM is faster tree includes style from user agent stylesheet
What are Layouts, Painting?
Layouts:
Layout is the process in which the width height and all locations of node are determined ,determination of size and position of object of a page
layouts is one of the process in rendered tree it started once’s the rendered tree formation takes place to determine the exact size of the browser starts at root of rendered tree and traverse it Different devices and desktop preferences means a unlimited viewport size,In layer phase we take view port size into consideration, taking view port size into consideration helps in layout to start with body and laying out dimensions of all the body’s descendants with each elements box model properties the recalculation of size and position is also know as reflow
Painting:
It’s the last phase in rendering path, In this phase browser converts each box calculated in layout phase to pixels on screen. painting involves drawing every part of element on screen with colour shadows, button etc
To ensure faster painting on screen the screen is usually broken down into layers,     painting can take place with help of GPU too if rather than use of CPU threads certain layers are being used by certain layers

