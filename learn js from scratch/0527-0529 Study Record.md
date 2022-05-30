![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530090300.png)

<h1>Task 1: Debugging with the Console and Breakpoints</h1>
Udemy Course: The Complete JavaScript Course 2022: From Zero to Expert! 
Teacher:  Jonas Schmedtmann
Progress: Debugging with the Console and Breakpoints (Video 61)

<h2>Section 1: Debugging with console</h2>

```javascript
const measureKelvin = function() {
  const measurement = {
    type: 'temp',
    unit: 'celsius',
    //value: prompt('Degrees celsius:') 
    
    //C. Fix the bug 👆🏻
    value: Number(prompt('Degrees celcius:')),
  };
  
  // B. Find the bug
  console.table(measurement);
  
  //console.log(measurement.value);
  //console.warn(measurement.value);
  //console.error(measurement.value);
  
  const kelvin = measurement.value + 273;
  return kelvin;
};
// A. Identify the bug
console.log(measureKelvin());
```

<h3> About prompt()  </h3>
Q: Does `prompt()`always come back as a string that you have to convert?

A: `prompt()`always returns a string, whether numbers or characters, with one exception. When the user clicks `Cancel`or presses the `Esc`key, `prompt()`returns `null`.

<h3>About console.table()</h3>
Debugging is the skill that all developers should have in their toolbox.

`console.table()`allows you to print your arrays and objects to the console in tabular form. The tabular representation of data works like a chart which means you will get greater insight into your data and you can just debug your code faster. You can also sort columns quickly.

**syntax:**

```javascript
table(data)
table(data, columns)
```

**Parameters:**

`data`: The data to display. This must be either an array or an object.
`columns`: An array containing the names of columns to include in the output.

**Return Value:**

None (undefinied)

<h3>How to implement console.table()</h3>
console.table() can be implemented in the following ways:

<h4>1.Array</h4>

```javascript
var fruits=["apple","mango","grapes"];
console.table(fruits);
```

Output👇🏻
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530092004.png)

<h4>2.Array of arrays</h4>

```javascript
var teams=[["John","Jari"],["Claus","Andrew"],["Marti","Martha"]];
console.table(teams);
```

Output👇🏻
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530092119.png)

<h4>3.Object</h4>

```javascript
var user={
     name:"neha",
     age:20,
     gender:"female",
}
console.table(user);
```

Output👇
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530101307.png)

<h4>4.Array of objects</h4>

```javascript
var users = [
    {
        name: "john",
        age: 40
    },
    {
        name: "amit",
        age: 35
    },
    {
        name: "neha",
        age: 20
    }
];
console.table(users);
```

Output👇🏻
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530092422.png)

<h4>5.Nested objects</h4>

```javascript
var employees = {
    leader: {
        firstname: "Andrew",
        lastname: "Story",
        email: "andrew@gmail.com"
    },
    manager: {
        firstname: "Amit",
        lastname: "Bhatt",
        email: "amit@gmail.com"
    },
    developer: {
        firstname: "Param",
        lastname: "Dutta",
        email: "param@gmail.com"
    }
}
console.table(employees);
```

Output👇🏻
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530092635.png)

<h2>Section 2: Debugging with a debugger in Google Chrome</h2>
DevTools provides a lot of different tools for different tasks, such as changing CSS, profiling page load performance, and monitoring network requets. The **Sources** panel is where your debug JavaScript.

<table><tr><td><font color=blue> Open DevTools by pressing Command+Option+I (Mac) or Control+Shift+I (Windows, Linux). This shortcut opens the Console panel. Then click the Sources Tab. </font></td></tr></table>

The **Sources** panel UI has 3 parts:
![[Pasted image 20220530093752.png]]
1.  The **File Navigator** pane. Every file that the page requests is listed here.
2.  The **Code Editor** pane. After selecting a file in the **File Navigator** pane, the contents of that file are displayed here.
3.  The **JavaScript Debugging** pane. Various tools for inspecting the page's JavaScript. If your DevTools window is wide, this pane is displayed to the right of the **Code Editor** pane.

<h3>Reference</h3>
[https://developer.chrome.com/docs/devtools/javascript/](https://developer.chrome.com/docs/devtools/javascript/)


<h2>Breakpoint</h3>
In software development, a **breakpoint** is an intentional stopping or pausing place in a program, put in place for debugging purposes. It is also sometimes simply referred to as a **pause**.

More generally, a breakpoint is a means of acquiring knowledge about a program during its execution. During the interruption, the programmer inspects the test environment (general purpose registers, memory, logs, files, etc.) to find out whether the program is functioning as expected. In practice, a breakpoint consists of one or more conditions that determine when a program's execution should be interrupted.

Breakpoints were invented for ENIAC, one of the earliest digital computers, by programmer Betty Holberton. In the initial design of ENIAC, program flow was set by plugging cables from one unit to another. To make the program stop at a certain point, a cable was removed, called a breakpoint.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530094024.png)

<h3>Overview of when to use each breakpoint type</h3>

| Breakpoint Type | Use This When You Want To Pause |
| :--- | :--- |
| Line-of-code | Use a line-of-code breakpoint when you know the exact region of code that you need to investigate. DevTools _always_ pauses before this line of code is executed.|
| Conditional line-of-code | Use a conditional line-of-code breakpoint when you know the exact region of code that you need to investigate, but you want to pause only when some other condition is true.|
| DOM | Use a DOM change breakpoint when you want to pause on the code that changes a DOM node or its children.|
| XHR | Use an XHR breakpoint when you want to break when the request URL of an XHR contains a specified string. DevTools pauses on the line of code where the XHR calls `send()`.|
| Event listener | Use event listener breakpoints when you want to pause on the event listener code that runs after an event is fired. You can select specific events, such as `click`, or categories of events, such as all mouse events.|
| Exception | Use exception breakpoints when you want to pause on the line of code that's throwing a caught or uncaught exception.|
| Function | Call `debug(functionName)`, where `functionName` is the function you want to debug, when you want to pause whenever a specific function is called. You can insert `debug()` into your code (like a `console.log()` statement) or call it from the DevTools Console. `debug()` is equivalent to setting a line-of-code breakpoint on the first line of the function.|

<h3>Reference</h3>

<h2>Interested Topic 1: Introduction to Chrome Developer Tools</h2>
**Chrome Developer Tools** (also known as **DevTools**) is an essential component of any front-end developer’s toolkit. Mastering this useful in-browser tool will substantially enhance your coding workflow. DevTools has a great deal of features, and to take advantage of them, it’s wise to invest some time learning the ins-and-outs of the tool in order to unlock its true potential.

<h3>Elements panel</h3>
![img]（https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530095724.png）

View and change the DOM and CSS.

-   [Get Started With Viewing And Changing The DOM](https://developer.chrome.com/docs/devtools/dom/)
-   [Get Started With Viewing And Changing CSS](https://developer.chrome.com/docs/devtools/css/)
-   [Inspect and Tweak Your Pages](https://developer.chrome.com/docs/devtools/css/#view)
-   [Edit Styles](https://developer.chrome.com/docs/devtools/css/reference/#change)
-   [Edit the DOM](https://developer.chrome.com/docs/devtools/dom/#edit)
-   [Inspect Animations](https://developer.chrome.com/docs/devtools/css/animations/)
-   [Find Unused CSS](https://developer.chrome.com/docs/devtools/coverage/)

<h3>Console panel</h3>
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530095826.png)

View messages and run JavaScript from the Console.

-   [Get Started With The Console](https://developer.chrome.com/docs/devtools/console/)
-   [Using the Console](https://developer.chrome.com/docs/devtools/console/)
-   [Interact from Command Line](https://developer.chrome.com/docs/devtools/console/utilities/)
-   [Console API Reference](https://developer.chrome.com/docs/devtools/console/api/)

<h3>Sources panel</h3>
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530095855.png)

Debug JavaScript, persist changes made in DevTools across page reloads, save and run snippets of JavaScript, and save changes that you make in DevTools to disk.

-   [Get Started With Debugging JavaScript](https://developer.chrome.com/docs/devtools/javascript/)
-   [Pause Your Code With Breakpoints](https://developer.chrome.com/docs/devtools/javascript/breakpoints/)
-   [Save Changes to Disk with Workspaces](https://developer.chrome.com/docs/devtools/workspaces/)
-   [Run Snippets Of Code From Any Page](https://developer.chrome.com/docs/devtools/javascript/snippets/)
-   [JavaScript Debugging Reference](https://developer.chrome.com/docs/devtools/javascript/reference/)
-   [Persist Changes Across Page Reloads with Local Overrides](https://developer.chrome.com/blog/new-in-devtools-65#overrides)
-   [Find Unused JavaScript](https://developer.chrome.com/docs/devtools/coverage/)

<h3>Network panel</h3>
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530095925.png)

View and debug network activity.

-   [Get Started](https://developer.chrome.com/docs/devtools/network/)
-   [Network Issues Guide](https://developer.chrome.com/docs/devtools/issues/)
-   [Network Panel Reference](https://developer.chrome.com/docs/devtools/network/reference/)
-   [Inspect Resources](https://developer.chrome.com/docs/devtools/resources/)

<h3>Performance panel</h3>
<table><tr><td><font color=blue>Note: In Chrome 58 the Timeline panel was renamed to the Performance panel.</font></td></tr></table>
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530100149.png)

Find ways to improve load and runtime performance.

-   [Optimize Website Speed](https://developer.chrome.com/docs/devtools/speed/get-started/)
-   [Get Started With Analyzing Runtime Performance](https://developer.chrome.com/docs/devtools/evaluate-performance/)
-   [Performance Analysis Reference](https://developer.chrome.com/docs/devtools/evaluate-performance/reference/)
-   [Analyze runtime performance](https://developer.chrome.com/docs/devtools/evaluate-performance/)
-   [Diagnose Forced Synchronous Layouts](https://developer.chrome.com/docs/devtools/evaluate-performance/#find_the_bottleneck)

<h3>Memory panel</h3>
<table><tr><td><font color=blue>Note: In Chrome 58 the Profiles panel was renamed to the Memory panel.</font></td></tr></table>
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530100337.png)

-   [Fix Memory Problems](https://developer.chrome.com/docs/devtools/memory-problems/)
-   [JavaScript CPU Profiler](https://developer.chrome.com/docs/devtools/rendering-tools/js-execution/)

<h3>Application panel</h3>
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530100410.png)

Inspect all resources that are loaded, including IndexedDB or Web SQL databases, local and session storage, cookies, Application Cache, images, fonts, and stylesheets.

-   [Debug Progressive Web Apps](https://developer.chrome.com/docs/devtools/progressive-web-apps/)
-   [Inspect and Manage Storage, Databases, and Caches](https://developer.chrome.com/docs/devtools/storage/localstorage/)
-   [Inspect and Delete Cookies](https://developer.chrome.com/docs/devtools/storage/cookies/)

<h3>Security panel</h3>
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530100500.png)

Debug mixed content issues, certificate problems, and more.

-   [Understand Security Issues](https://developer.chrome.com/docs/devtools/security/)


<h2>Interested Topic 2: Google Chrome for developers</h2>
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530100544.png)

<h2>Interested Topic 3: History of Google Chrome</h2>
Google CEO Eric Schmidt opposed the development of an independent web browser for six years. He stated that "at the time, Google was a small company", and he did not want to go through "bruising browser wars". After co-founders Sergey Brin and Larry Page hired several Mozilla Firefox developers and built an demonstration of Chrome, Schmidt said that "It was so good that it essentially forced me to change my mind."

In September 2004, rumors of Google building a web browser first appeared. Online journals and U.S. newspapers stated at the time that Google was hiring former Microsoft web developers among others. It also came shortly after the release of Mozilla Firebox 1.0, which was surging in popularity and taking market share from Internet Explorer, which had noted security problems. Development of the browser began in 2006 spearheaded by Sundar Pichai.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530100642.png)

<h3>Announcement</h3>
The release announcement was originally scheduled for September 3, 2008, and a comic by Scott McCloud was to be sent to journalists and bloggers explaining the features within the new browser. Copies intended for Europe were shipped early and German blogger Philipp Lenssen of Google Blogoscoped made a scanned copy of the 38-page comic available on his website after receiving it on September 1, 2008.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530100716.png)

<table><tr><td><font color=blue>Scott McCloud (born Scott McLeod on June 10, 1960) is an American cartoonist and comics theorist. He is best known for his non-fiction books about comics: Understanding Comics (1993), Reinventing Comics (2000), and Making Comics (2006), all of which also use the medium of comics.</font></td></tr></table>

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530101128.png)

Google subsequently made the comic available on Google Books, and mentioned it on their official blog along with an explanation for the early release. The product was named "Chrome" as an initial development project code name, because it is associated with fast cars and speed. Google kept the development project name as the final release name, as a "cheeky" or ironic moniker, as one of the main aims was to minimize the user interface chrome.

<h3>Public release</h3>
The browser was first publicly released, officially as a beta version, on September 2, 2008 for Windows XP and newer, and with support for 43 languages, and later as a "stable" public release on December 11, 2008. On that same day, a CNET news item drew attention to a passage in the Terms of Service statement for the initial beta releases, which seemed to grant to Google a license to all content transferred via the Chrome browser. This passage was inherited from the general Google terms of service. Google responded to this criticism immediately by stating that the language used was borrowed from other products, and removed this passage from the Terms of Service.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530122800.png)

Chrome quickly gained about 1% usage share. After the initial surge, usage share dropped until it hit a low of 0.69% in October 2008. It then started rising again and by December 2008, Chrome again passed the 1% threshold. In early January 2009, CNET reported that Google planned to release versions of Chrome for OS X and Linux in the first half of the year. The first official Chrome OS X and Linux developer previews were announed on June 4, 2009, with a blog post saying they were missing many features and were intended for early feedback rather than general use. In December 2009, Google released beta versions of Chrome for OS X and Linux. Google Chrome 5.0, announced on May 25, 2010, was the first stable release to support all three platforms.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530101250.png)

Chrome was one of the twelve browsers offered on BrowserChoice.eu to European Economic Area users of Microsoft Windows in 2010.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530101307.png)

<h3>Development</h3>
Chrome was assembled from 25 different code libraries from Google and third parties such as Mozilla's Netscape Portable Runtime, Network Security Services, NPAPI (dropped as of version 45), Skia Graphics Engine, SQLite, and a number of other open-source projects. The V8 JavaScript virtual machine was considered a sufficiently important project to be split off (as was Adobe/Mozilla's Tamarin) and handled by a separate team in Denmark coordinated by Lars Bak in Aarhus.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530123600.png)

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530123800.png)

According to Google, existing implementations were designed "for small programs, where the performance and interactivity of the system weren't that important", but web applications such as Gmail "are using the web browser to the fullest when it comes to DOM manipulations and JavaScript", and therefore would significantly benefit from a JavaScript engine that could work faster.

Chrome initially used the WebKit rendering engine to display web pages. In 2013, they forked the WebCore component to create their own layout engine Blink. Based on WebKit, Blink only uses WebKit's "WebCore" components, while substituting other components, such as its own multi-process architecture, in place of WebKit's native implementation.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530124200.png)

Chrome is internally tested with unit testing, automated testing of specified user actions, fuzz testing, as well as WebKit's layout tests (99% of which Chrome is claimed to have passed), and againt commonly accessed websites inside the Google index within 20-30 minutes. Google created Gears for Chrome, which added features for web developers typically relating to the building of web applications, including offline support. Google phased out Gears as the same functionality became available in the HTML5 standards. 

In March 2011, Google introduced a new simplified logo to replace the previous 3D logo that had been used since the project's inception. Googld designer Steve Rura explained the company reasoning for the change: "Since Chrome is all about making your web experience as easy and clutter-free as possible, we refreshed the Chrome icon to better represent these sentiments. A simpler icon embodies the Chrom spirit - to make the web quicker, lighter, and easier for all."

On January 11, 2011, the Chrome product manager, Mike Jazayeri, announced that Chrome would remove H.264 video codec support for its HTML5 player, citing the desire to bring Google Chrome more in line with the currently available open codecs available in the Chromium project, which Chrome is based on. Despite this, on November 6, 2012, Google released a version of Chrome on Windows which added hardware-accelerated H.264 video decoding. In October 2013, Cisco announced that it was open-sourcing its H.264 codecs and would cover all fees required.

On February 7, 2012, Google launched _Google Chrome Beta_ for Android 4.0 devices. On many new devices with Android 4.1 and later preinstalled, Chrome is the default browser. In May 2017, Google announced a version of Chrome for augmented reality and virtual reality devices.

<h2>Interested Topic 4: Code Reuse in Google Chrome Browser</h2>
Google Chrome browser shows an excellent example of code reuse. They use at least 25 different software libraries.
<h3>Library 1: Google Breakpad</h3>
Google Breakpad is a set of client and server components which implement a crash-reporting system.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530101611.png)

<h3>Library 2: Chrome's URL Library</h3>
Chrome's URL Library is a small library for parsing and canonicalizing URLs.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530101653.png)

<h3>Library 3: Skia</h3>
Skia is an open source 2D graphics library which provides common APIs that work across a variety of hardware and software platforms. It serves as the graphics engine for Google Chrome and Chrome OS, Android, Flutter, and many other products.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530124600.png)

<h3>Library 4: V8</h3>
V8 is Google's open source high-performance JavaScript and WebAssembly engine, written in C. It is used in Chrome and in Node.js, among others. It implements ECMAScript and WebAssembly, and runs on Windows 7 or later, macOS 10.12+, and Linux systems that use x64, IA-32, ARM, or MIPS processors. V8 can run standalone, or can be embedded into any C++ application.
<table><tr><td><font color=blue>WebAssembly (abbreviated Wasm) is a binary instruction format for a stack-based virtual machine. Wasm is designed as a portable compilation target for programming langauges, enabling deployment on the web for client and server applications.</font></td></tr></table>
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530101835.png)

<h3>Library 5: WebKit</h3>
WebKit is a browser engine developed bu Apple and primarily used in its Safari web browser, as well as all iOS web browsers. WebKit is also used by the BlackBerry Browser, PlayStation consoles beginning from the PS3, the Tizen mobile operating systems, and a browser included with the Amazon Kindle e-book reader. WebKit's C++ application programming interface (API) provides a set of classes to display Web content in windows, and implements browser features such as following links when clicked by the user, managing a back-forward list, and managing a history of pages recently visited.

WebKit's HTML and JavaScript engine started as a fork of the KHTML and KJS libraries from KDE, and has since been further developed by KDE contributors, Apple, Google, Nokia, Bitstream, BlackBerry, Sony, Igalia, and others. WebKit supports macOS, Windows, Linux and various other Unix-like operating systems. On April 3, 2013, Google announced that it had forked WebCore, a component of WebKit, to be used in future versions of Google Chrome and the Opera web browser, under the name Blink.

WebKit is available under the BSD 2-Clause license with the exception of the WebCore and JavaScriptCore components, which are available under the GNU Lesser General Public License. As of March 7, 2013, WebKit is a trademark of Apple, registered with the U.S. Patent and Trademark Office.
![https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530101908.png]

<h3>Library 6: Netscape Portable Runtime (NSPR)</h3>
In computing, the **Netscape Portable Runtime**, or **NSPR**, a platform abstraction library, makes all operating systems it supports appear the same to (for example) Mozilla-style web-browsers. NSPR provides platform independence for non-GUI operating system facilities. These facilities include:

-   threads
-   thread synchronization
-   normal file and network I/O
-   interval timing and calendar time
-   basic memory management (malloc and free)
-   shared library linking.

Much of the library, and perhaps the overall thrust of it in the Gromit environment, provides the underpinnings of the Java virtual machine, more or less mapping the sys layer that Sun defines for the porting of the Java VM to various platforms. NSPR does go beyond that requirement in some areas, as it also functions as the platform-independent layer for most of the servers produced by Netscape.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530102007.png)

<h3>Library 7: Network Security Services (NSS)</h3>
**Network Security Services** (**NSS**) is a collection of cryptographic computer libraries designed to support cross-platform development of security-enabled client and server applications with optional support for hardware TLS/SSL acceleration on the server side and hardware smart cards on the client side. NSS provides a complete open-source implementation of cryptographic libraries supporting Transport Layer Security (TLS) / Secure Sockets Layer (SSL) and S/MIME. NSS releases prior to version 3.14 are tri-licensed under the Mozilla Public License 1.1, the GNU General Public License, and the GNU Lesser General Public License. Since release 3.14, NSS releases are licensed under GPL-compatible Mozilla Public License 2.0.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530124900.png)

<h3> Library 8: Hunspell </h3>
Hunspell is the spell checker of LibreOffice, OpenOffice.org, Mozilla Firefox 3 & Thunderbird, Google Chrome, and it is also used by proprietary software packages, like macOS, InDesign, memoQ, Opera and SDL Trados.

Main features:

-   Extended support for language peculiarities; Unicode character encoding, compounding and complex morphology.
-   Improved suggestion using n-gram similarity, rule and dictionary based pronunciation data.
-   Morphological analysis, stemming and generation.
-   Hunspell is based on MySpell and works also with MySpell dictionaries.
-   C++ library under GPL/LGPL/MPL tri-license.
-   Interfaces and ports: AndroidHunspellService (for Android, based on the Chromium fork of Hunspell), Enchant (Generic spelling library from the Abiword project), XSpell (macOS port, but Hunspell is part of the macOS from version 10.6 (Snow Leopard), and now it is enough to place the Hunspell dictionary files into ~/Library/Spelling or /Library/Spelling for spell checking), Delphi, Java (JNA, JNI), Perl, .NET, .NET Standard, Python, Ruby (1, 2, 3), UNO, RichEdit.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530125200.png)

<h3>Library 9: Windows Template Library</h3>
**Windows Template Library** (**WTL**) is a free software, object-oriented C++ template library for Win32 development. WTL was created by Microsoft employee Nenad Stefanovic for internal use and later released as an unsupported add-on to Visual Studio and the Win32 Framework SDK. It was developed primarily as a light-weight alternative to the Microsoft Foundation Classes and builds upon Microsoft's ATL, another lightweight API widely used to create COM and ActiveX libraries.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530102301.png)

<h3>Library 10: Google C++ Testing Framework</h3>
_Google C++ Testing Framework_ helps you write better C++ tests.

No matter whether you work on Linux, Windows, or a Mac, if you write C++ code, Google Test can help you.

So what makes a good test, and how does Google C++ Testing Framework fit in? We believe:

1.  Tests should be _independent_ and _repeatable_. It's a pain to debug a test that succeeds or fails as a result of other tests. Google C++ Testing Framework isolates the tests by running each of them on a different object. When a test fails, Google C++ Testing Framework allows you to run it in isolation for quick debugging.
2.  Tests should be well _organized_ and reflect the structure of the tested code. Google C++ Testing Framework groups related tests into test cases that can share data and subroutines. This common pattern is easy to recognize and makes tests easy to maintain. Such consistency is especially helpful when people switch projects and start to work on a new code base.
3.  Tests should be _portable_ and _reusable_. The open-source community has a lot of code that is platform-neutral, its tests should also be platform-neutral. Google C++ Testing Framework works on different OSes, with different compilers (gcc, MSVC, and others), with or without exceptions, so Google C++ Testing Framework tests can easily work with a variety of configurations. (Note that the current release only contains build scripts for Linux - we are actively working on scripts for other platforms.)
4.  When tests fail, they should provide as much _information_ about the problem as possible. Google C++ Testing Framework doesn't stop at the first test failure. Instead, it only stops the current test and continues with the next. You can also set up tests that report non-fatal failures after which the current test continues. Thus, you can detect and fix multiple bugs in a single run-edit-compile cycle.
5.  The testing framework should liberate test writers from housekeeping chores and let them focus on the test _content_. Google C++ Testing Framework automatically keeps track of all tests defined, and doesn't require the user to enumerate them in order to run them.
6.  Tests should be _fast_. With Google C++ Testing Framework, you can reuse shared resources across tests and pay for the set-up/tear-down only once, without making tests depend on each other.

Since Google C++ Testing Framework is based on the popular xUnit architecture, you‘ll feel right at home if you’ve used JUnit or PyUnit before. If not, it will take you about 10 minutes to learn the basics and get started. So let's go!

_Note:_ We sometimes refer to Google C++ Testing Framework informally as _Google Test_.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530125600.png)

<h3>Library 11: bsdiff/bspatch</h3>
bsdiff and bspatch are libraries for building and applying patches to binary files.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530125800.png)


<h3>Library 12: bzip2</h3>
bzip2 is a freely available, patent free , high-quality data compressor. It typically compresses files to within 10% to 15% of the best available techniques (the PPM family of statistical compressors), whilst being around twice as fast at compression and six times faster at decompression.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530130000.png)

<h3>Library 13: International Components for Unicode (ICU)</h3>
**International Components for Unicode** (**ICU**) is an open-source project of mature C/C++ and Java libraries for Unicode support, software internationalization, and software globalization. ICU is widely portable to many operating systems and environments. It gives applications the same results on all platforms and between C, C++, and Java software. The ICU project is a technical committee of the Unicode Consortium and sponsored, supported, and used by IBM and many other companies.
<table><tr><td><font color=blue>Unicode Consortium: The Unicode Consortium is a non-profit corporation devoted to developing, maintaining, and promoting software internationalization standards and data, particularly the Unicode Standard, which specifies the representation of text in all modern software products and standards. The Unicode Consortium actively develops standards in the area of internationalization including defining the behavior and relationships between Unicode characters. The Consortium works closely with W3C and with ISO and IEC—in particular with ISO/IEC/JTC 1/SC2/WG2, which is responsible for maintaining ISO/IEC 10646, the International Standard synchronized with the Unicode Standard.</font></td></tr></table>
ICU provides the following services: Unicode text handling, full character properties, and character set conversions; Unicode regular expressions; full Unicode sets; character, word, and line boundaries; language-sensitive collation and searching; normalization, upper and lowercase conversion, and script transliterations; comprehensive locale data and resource bundle architecture via the Common Locale Data Repository (CLDR); multiple calendars and time zones; and rule-based formatting and parsing of dates, times, numbers, currencies, and messages. ICU provided complex text layout service for Arabic, Hebrew, Indic, and Thai historically, but that was deprecated in version 54, and was completely removed in version 58 in favor of HarfBuzz.

ICU provides more extensive internationalization facilities than the standard libraries for C and C++. Unicode 14.0 is supported. ICU 67 supports Unicode 13.0 and handles removal of Great Britain from the EU. ICU 64 supports Unicode 12.0, while ICU 64.2 added support for Unicode 12.1, i.e. the single new symbol for current Japanese Reiwa era (but support for it has also been backported to older ICU versions down to ICU 4.8.2). ICU 58 (with Unicode 9.0 support) is the last version to support older platforms such as Windows XP and Windows Vista. Support for AIX, Solaris and z/OS may also be limited in later versions (i.e. building depends on compiler support).ICU has been included as a standard component with Microsoft Windows since Windows 10 version 1703.

ICU has historically used UTF-16, and still does only for Java; while for C/C++ UTF-8 is supported, including the correct handling of "illegal UTF-8".

ICO 70 updated to Unicode 14 and added support for emoji properties of strings and C++20 compilers.

ICU 71 adds e.g. phrase-based line breaking for Japanese (earlier methods didn't work well for short Japanese text, such as in titles and headings) and support for Hindi written in Latin letters (hi_Latn), also referred to as "Hinglish" and updates to the time zone data version 2022a.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530103739.png)

<h3>Library 14: libjpeg</h3>
**libjpeg** is a free library with functions for handling the JPEG image data format. It implements a JPEG codec (encoding and decoding) alongside various utilities for handling JPEG data. It is written in C and distributed as free software together with its source code under the terms of a custom permissive (BSD-like) free software license, which demands attribution. The original variant is maintained and published by the Independent JPEG Group (IJG). Meanwhile, there are several forks with additional features.

JPEG JFIF images are widely used on the Web. The amount of compression can be adjusted to achieve the desired trade-off between file size and visual quality.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530103839.png)

<h3>Library 15: libpng</h3>
**libpng** is the official Portable Network Graphics (PNG) reference library (originally called **pnglib**). It is a platform-independent library that contains C functions for handling PNG images. It supports almost all of PNG's features, is extensible, and has been widely used and tested for over 23 years. libpng is dependent on zlib for data compression and decompression routines.

libpng is released under the libpng license, a permissive free software licence, and is free software. It is frequently used in both free and proprietary software, either directly or through the use of a higher level image library.

As of 2017 the latest versions in the 1.6.x and 1.5.x branches were considered as release versions, while 1.4.x, 1.2.x, and 1.0.x were considered as legacy versions getting only security fixes. All vulnerability warnings and crash bugs are published on the main page.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530103913.png)

<h3>Library 16: libxml</h3>
**libxml** is a software library for parsing XML documents.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530104039.png)

<h3>Library 17: libxlst</h3>
**libxslt** is the XSLT C library developed for the GNOME project. It provides an implementation of XSLT 1.0, plus most of the EXSLT set of processor-portable extensions functions and some of Saxon's evaluate and expressions extensions. libxslt is based on libxml2, which it uses for XML parsing, tree manipulation and XPath support. It is free software released under the MIT License and can be reused in commercial applications.
<table><tr><td><font color=blue>GNOME Project is a community behind the GNOME desktop environment and the software platform upon which it is based. It consists of all the software developers, artists, writers, translators, other contributors, and active users of GNOME. It is no longer part of the GNU Project.</font></td></tr></table>
libxslt can be used either as library embedded into an application, or via the xsltproc command line tool. The integration into applications is eased by a multitude of language bindings and wrappers. Being written in C, libxslt is a fast and low-resource processor. This makes it a popular choice for DocBook formatting and as standard XSLT processor for programming languages like PHP, Perl or Python.

The WebKit layout engine (used e.g. in Apple Safari and Google Chrome web browser) uses the libxslt library to do XSL transformations.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530104557.png)

<h3>Library 18: LZMA SDK</h3>
The **LZMA SDK** provides the documentation, samples, header files, libraries, and tools you need to develop applications that use **LZMA** compression.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530104627.png)

<h3>Library 19: stringencoders</h3>
A collection of high performance c-string transformations (in this case, base 64 encoding/decoding), frequently 2x faster than standard implementations (if they exist at all).
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530104719.png)

<h3>Library 20: Netscape Plugin Application Programming Interface (NPAPI)</h3>
**Netscape Plugin Application Programming Interface** (**NPAPI**) is an application programming interface (API) of the web browsers that allows plugins to be integrated.

Initially developed for Netscape browsers, starting in 1995 with Netscape Navigator 2.0, it was subsequently adopted by other browsers.

In NPAPI architecture, a plugin declares content types (e.g. "audio/mp3") that it can handle. When the browser encounters a content type it cannot handle natively, it loads the appropriate plugin, sets aside space within the browser context for the plugin to render and then streams data to it. The plugin is responsible for rendering the data. The plugin runs in-place within the page, as opposed to older browsers that had to launch an external application to handle unknown content types. NPAPI requires each plugin to implement and expose approximately 15 functions for initializing, creating, deleting and positioning plugin content. NPAPI also supports scripting, printing, full-screen plugins, windowless plugins and content streaming.

NPAPI was frequently used for plugins which required intensive, low-level performance such as video players, including Adobe Flash Player and Microsoft Silverlight, as well as platforms for web applications such as the Java Runtime Environment.

NPAPI support among major browsers started to wane since 2015 and it was gradually deprecated over the last years. With the advent of HTML5, all major web browsers have removed support for 3rd party NPAPI plugins for security reasons. There are some smaller browsers such as Pale Moon and Waterfox Classic that still support NPAPI plugins.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530104949.png)

<h3>Library 21: Pthreads </h3>
The POSIX 1003.1-2001 standard defines an application programming interface (API) for writing multithreaded applications. This interface is known more commonly as _pthreads_. A good number of modern operating systems include a threading library of some kind: Solaris (UI) threads, Win32 threads, DCE threads, DECthreads, or any of the draft revisions of the pthreads standard. The trend is that most of these systems are slowly adopting the pthreads standard API, with application developers following suit to reduce porting woes.

Win32 does not, and is unlikely to ever, support pthreads natively. This project seeks to provide a freely available and high-quality solution to this problem.

Various individuals have been working on independent implementations of this well-documented and standardised threading API, but most of them never see the light of day. The tendency is for people to only implement what they personally need, and that usually does not help others. This project attempts to consolidate these implementations into one implementation of pthreads for Win32.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530105023.png)

<h3>Library 22: Scons</h3>
**SCons** is a computer software build tool that automatically analyzes source code file dependencies and operating system adaptation requirements from a software project description and generates final binary executables for installation on the target operating system platform. Its function is analogous to the traditional GNU build system based on the make utility and the autoconf tools.

SCons generates project configurations and build process implementations in the form of Python scripts.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530130800.png)

<h3>Library 23: SQLite</h3>
**SQLite** is a database engine written in the C language. It is not a standalone app; rather, it is a library that software developers embed in their apps. As such, it belongs to the family of embedded databases. It is the most widely deployed database engine, as it is used by several of the top web browsers, operating systems, mobile phones, and other embedded systems.

SQLite has bindings to many programming languages. It generally follows PostgreSQL syntax but does not enforce type checking. This means that one can, for example, insert a string into a column defined as an integer.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530105134.png)

<h3>Library 24: TLS Lite</h3>
TLS Lite is an open source python library that implements SSL and TLS. TLS Lite supports RSA and SRP ciphersuites. TLS Lite is pure python, however it can use other libraries for faster crypto operations. TLS Lite integrates with several stdlib neworking libraries.

![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530131200.png)

<h3>Library 25: zlib</h3>
**zlib** is a software library used for data compression. zlib was written by Jean-loup Gailly and Mark Adler and is an abstraction of the DEFLATE compression algorithm used in their gzip file compression program. zlib is also a crucial component of many software platforms, including Linux, macOS, and iOS. It has also been used in gaming consoles such as the PlayStation 4, PlayStation 3, Wii U, Wii, Xbox One and Xbox 360.

The first public version of zlib, 0.9, was released on 1 May 1995 and was originally intended for use with the libpng image library. It is free software, distributed under the zlib License.
![img](https://github.com/EarlyDaysDeepRoots/webdev2022/blob/main/images/Pasted%20image%2020220530105338.png)
