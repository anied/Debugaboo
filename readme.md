# Debug A Boo -- Javscript debugging with your Chrome Developer Tools

In the olden times, when Netscape and IE5 roamed the land, and AskJeeves™ was a thing, debugging Javascript was difficult-- The tools were crude and inconsistent, didn't necessarily come included with the browser, and the process was painful.

In today's modern browser landscape, the process of inspecting and debugging your code is dramatically improved, with all three of the major browsers shipping with robust (or with IE, at least relatively usable) suites of tools for developers.

Chrome seems to have established itself as the de facto browser-of-choice for web developers because of it's early inclusion of robust developer tools.  As we explore Javascript debugging with the Chrome dev tools, 

### Basic Breakpoints
The simplest way to enter debug-mode on a script is to set a breakpoint.

Simple breakpoint mechanics:

- Add/Remove
- Enable/Disable
- Group Enable/Disable

### Navigating in Debug Mode
Javascript debugging can seem a little daunting at first, but once you get the hang of it it is super-useful.

#### Pause
Just what it sounds like-- pauses execution at exactly the moment you push it.  As you can imagine, this has pretty limited usefulness.  Much better to enter debug mode using breakpoints or some other more controlled method.

#### Play/Continue
When you _are_ in a paused state, pushing the `continue` button allows scripts to continue execution as normal, until they hit the next breakpoint.
Additionally, the Chrome dev tools have an additional `play` button which will continue and ignore all breakpoints for 500ms-- perfect for allowing a page to continue loading when you have a breakpoint in a `for` loop.

#### Step Over
Somewhat confusing name, the `step over` button executes the current command and moves on to the next one _in the current scope._  If you have reached the end of code execution in the current scope, `step over` will then move up the call stack to the origination point of the current execution point.

#### Step In
`step in` will move down the call stack when there is an oppotunity to do so and begin debugging the function being called from that line-- if there is no new call being executed from that line, it will behave like a simple `step over`.  For example: _(consider example here)_

#### Step Out
`step out` is the opposite of `step in`-- rather than continuing down commands in the current function on the call stack, it instead backs out out of the current scope to the point of the originating call to the current scope.

### Doing stuff in debug mode

 - Hover
 - Watch list
 - Console
 - Change and save

### Additional ways to enter debug mode
 - Conditional breakpoints
 - The `debugger` command
 - Break on error
 - DOM/XHR/Event listener breakpoints

### Network Stack Tracing
You can also find out how any given downloaded resource was initiated for download by going to the Network Panel-- here you can hover over the blue underlined text in the initiator colum to see a navigable stack trace of showing the steps that led up to the resource being requested.  When using libraries like Backbone and jQuery there will likely be many library-internal function calls for things like ajax/fetch requests, but sorting out your personal code from library code shouldn't prove too difficult.

### Console
https://developer.chrome.com/devtools/docs/console-api

### Local Files