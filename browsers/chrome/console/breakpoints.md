# Breakpoints

{% embed url="https://dev.to/songthamtung/stop-console-logging-this-is-how-to-use-chrome-to-debug-javascript-48nm" %}



If you console.log\(\) when you debug, you’re doing it wrong. There’s an easier way and it’s right in the palm of your browser.

### Sound familiar?

Javascript is the most popular programming language according to StackOverflow’s 2019 survey. If you develop with Javascript, you’ve most likely came across a situation where you had to fix a bug or two.

“No problem!” you say to your rubber ducky, let’s reproduce the bug and fix it with `console.log()`. Now, what if I told you that this is not the best practice?

_At the end of this article, I included a TL;DR summary._

### Console logging works, but there’s a better way.

[![consolelog](https://res.cloudinary.com/practicaldev/image/fetch/s--fBr1bCEy--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://miro.medium.com/max/1284/0%2Aj2xSdGh-CoSe0mck.jpg)](https://res.cloudinary.com/practicaldev/image/fetch/s--fBr1bCEy--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://miro.medium.com/max/1284/0%2Aj2xSdGh-CoSe0mck.jpg)

Instead of console.logging and restarting every time you want to debug, you can instead use Chrome DevTools \(right click + inspect\).

Perhaps you’re already using it to view and modify HTML/CSS elements, monitor console logs, and measure network performance. But did you know that Chrome has a powerful built in debugging feature where you can:

* view source code
* set breakpoints
* step into, step over, and step out

The rest of the article is a step by step guide on how to use Chrome’s debugging feature with Angular — but feel free to follow along with your existing projects on any javascript frontend framework.

### Setting up your environment.

_NOTE: If you already have an existing project, skip to the next section._

In this section, we will quickly set up an Angular app using their official guide.

**Prerequisites**  
Node.js version 10.9.0 or later.

**Step 1. Install Angular CLI**  
`npm install -g @angular/cli`

**Step 2: Create a workspace and initial application**  
`ng new my-app`

**Step 3: Run the application**  
`cd my-app  
ng serve --open`

This will open your browser to the url localhost:4200  
[![Angularv8.2](https://res.cloudinary.com/practicaldev/image/fetch/s--U-qmosi_--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://miro.medium.com/max/5112/1%2Ai4zrKrXodBww-bku1Y-1ig.png)](https://res.cloudinary.com/practicaldev/image/fetch/s--U-qmosi_--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://miro.medium.com/max/5112/1%2Ai4zrKrXodBww-bku1Y-1ig.png)Angular v8.2

### Create the bug 🐛

For the purposes of this demonstration, let’s create a bug and then debug it ;\).

Open your favorite text editor and navigate to `src/app/app.component.ts`  
Replace the lines with the following and save.

|  | import { Component } from '@angular/core'; |
| :--- | :--- |
|  |  |
|  | @Component\({ |
|  |  selector: 'app-root', |
|  |  templateUrl: './app.component.html', |
|  |  styleUrls: \['./app.component.css'\] |
|  | }\) |
|  | export class AppComponent { |
|  |  author = getAuthor\(\); |
|  |  title = \`my-app by ${this.author}\`; |
|  | } |
|  |  |
|  | function getAuthor\(\) { |
|  |  const obj = { name: 'songthamtung' }; |
|  |  return obj; |
|  | } |

[view raw](https://gist.github.com/songthamtung/008ecd0897a2d82b93b4b52258d14ba2/raw/6566a0507cc159b5620e61854f553d00df414148/app.component.ts)[app.component.ts](https://gist.github.com/songthamtung/008ecd0897a2d82b93b4b52258d14ba2#file-app-component-ts) hosted with ❤ by [GitHub](https://github.com/)

Look at the browser again and you should see a bug!  
[![bug](https://res.cloudinary.com/practicaldev/image/fetch/s--dPi3O90l--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://miro.medium.com/max/2320/1%2AIYuf_CG-_x_wSORoFhA8Vg.png)](https://res.cloudinary.com/practicaldev/image/fetch/s--dPi3O90l--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://miro.medium.com/max/2320/1%2AIYuf_CG-_x_wSORoFhA8Vg.png)  
\[object Object\] is simply the default return value when converting a POJO \(plain old javascript object\) to a string. This is not a desired outcome — so let’s fix it!

### Debug Mode 🔴

**1. Inspect the sources**  
[![inspect](https://res.cloudinary.com/practicaldev/image/fetch/s--qME40Y9i--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://miro.medium.com/max/2400/0%2Aey2hTBkRuJzU1bb7.gif)](https://res.cloudinary.com/practicaldev/image/fetch/s--qME40Y9i--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://miro.medium.com/max/2400/0%2Aey2hTBkRuJzU1bb7.gif)  
Using Chrome, `right click > inspect > sources > cmd + p > search file`

If done correctly, this will take you to the source code, where the bug lurks.

**2. Set breakpoints**  
Setting breakpoints is vital to debugging effectively. A breakpoint is an intentional pause in a program, which allows the developer to inspect the internal state of the application at that moment. You can use it to view variables and perform other debugging functions.

> A breakpoint is an intentional pause in a program, which allows the developer to inspect the internal state of the application at that moment.

To set a breakpoint, click the line number where you want the program to pause. In the example below, we set it at line 9.  
[![breakpoint](https://res.cloudinary.com/practicaldev/image/fetch/s--tItms3xy--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://miro.medium.com/max/5112/1%2AfKzayBe8_Zoo8KKNY_S_jg.png)](https://res.cloudinary.com/practicaldev/image/fetch/s--tItms3xy--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://miro.medium.com/max/5112/1%2AfKzayBe8_Zoo8KKNY_S_jg.png)

Refresh the browser and you should see “Paused in debugger”.  
[![pause](https://res.cloudinary.com/practicaldev/image/fetch/s--UN6tsxLz--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://miro.medium.com/max/2400/0%2AFZYrQcapj0RaeirX.gif)](https://res.cloudinary.com/practicaldev/image/fetch/s--UN6tsxLz--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://miro.medium.com/max/2400/0%2AFZYrQcapj0RaeirX.gif)

Hover your mouse over the variable author— it should be undefined. The reason that it’s undefined is because the program hasn’t reached this line yet. It finished executing line 8 and is about to reach line 9.

Press ▶️ to continue execution.

**3. Step into, step over, and step out.**  
These basic 3 steps is the bread and butter for debugging.

* _Step into_ is when the debugger steps into or inside a function
* _Step over_ is when the debugger steps to the next line
* _Step out_ is when the debugger steps outside the current function

[![s3](https://res.cloudinary.com/practicaldev/image/fetch/s--hnPhK4EP--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://miro.medium.com/max/2400/1%2An-4jo-FOec2rlBB4tYcXfw.gif)](https://res.cloudinary.com/practicaldev/image/fetch/s--hnPhK4EP--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://miro.medium.com/max/2400/1%2An-4jo-FOec2rlBB4tYcXfw.gif)Step in, step over, and step across in action

Refresh the browser again and once the debugger pauses at your breakpoint, step into the function using the panel on the right hand side. This will take you to the function `getAuthor()`. Hover your mouse over obj and you will see undefined since we haven’t actually executed it yet. Step over to execute the line and hover your mouse over obj again. This time, you should see a POJO. Step out to return to the caller and now this time author is no longer undefined.

Great — so we now know that author object has value. How do we fix it?

**4. Fix the bug**  
Replace line 10 with the following and save.  
`title =`my-app by ${this.author.name}`;`

**5. Deactivate breakpoints**

[![deactivate](https://res.cloudinary.com/practicaldev/image/fetch/s--qd87OJAC--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://miro.medium.com/max/908/0%2A3IeQp6_SlrMg3fts.gif)](https://res.cloudinary.com/practicaldev/image/fetch/s--qd87OJAC--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://miro.medium.com/max/908/0%2A3IeQp6_SlrMg3fts.gif)  
Click _Deactivate breakpoints_. It changes blue to indicate that it’s active. While this is set, DevTools ignores any breakpoints you’ve set.  
Refresh the page.

Fixed!

### Closing

Congratulations! You now know how to use Chrome DevTools to debug efficiently. While `console.log()` does have a place in programming, it’s limited to modifying the source code, restarting the program, and nonstop execution. Chrome’s built in debugging tool addresses these disadvantages and offers you the ability to stop, inspect, and investigate what’s happening in the program at the specific point in time.

### TL;DR

Open inspector, click the Sources tab, and `CMD + P` to view your source code and set breakpoints.

For more information, check out [Google’s blog](https://developers.google.com/web/tools/chrome-devtools/javascript/) on this topic.

Thanks for reading! Originally published on [Faun](https://medium.com/faun/how-to-use-chrome-to-debug-javascript-ad3c6900e8d5).

