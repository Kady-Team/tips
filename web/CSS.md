# Some CSS tips 

> 🔎 **Basic CSS knowledge is required !**

## Organize your rules:
> In CSS, we can use a looottt of rules for only one element !
> This can result in a very big block, and sometimes we can't find a specific rule

> This is why we recommend to organize your rules, for example:
```css
.container div.body {
  width: calc(100% - 20px);
  height: 400px;
  background: #333;
  
  margin: 0;
  padding: 10px 0; /* similar to 10px 0 10px 0 */
  
  border-radius: 7px;
  border: 2px solid #eaeaea;
}
```
💡 **You can minify your code when you deploy it to optimize the time of client requests !**

## Use variables 
> In CSS, we use at sometime the same color in sooo many places
> And when we want to change this... Good luck !!!

> This is why we recommend to use CSS variables, for example:
```css
* {
  --background: #333;
  --main-color: #e56e19;
  --default-paddind-size: 10px;
}

body, div.container {
  background: var(--background);
}

body .navbar {
  --height: 50px;
}
body .navbar.invisible {
  --height: 0;
}

body .navbar {
  height: var(--height);
  /* If the Navbar have the "invisible" class, the height will be 0, otherwise the height will be 50 ! */
}

div.container {
  padding: var(--default-paddind-size);
  border: 5px solid var(--main-color);
}

a.main-links {
  color: var(--main-color);
}
```
💡 **This is very useful for a dark/light theme !**

## Don't mess with class names and CSS path 
> If you use a lot of librairies and plugins, they can also have a CSS file
> But if you use the same class name, this can result in strange errors and issues 🙃

> Don't be afraid to give longer and more explicit names !
```css

/* With this CSS Path and class name, we reduce the CSS rules collisions */
body .navbar buttons::hover p.navbar-button-title {
  color: #fff;
}

/* Another example */
body div.container section:not(#main-body-container) p {
  font-size: 12px;
  color: #9a9a9a;
}
```
💡 **This will be easier for code reviewer and you when you look at your code after some time.**

## Add a lot of comments
> Especially when you work with another developer, we don't understand what he (or she) does at sometime

> This is why comments are recommended!
```css
/* By default, the theme is dark */
body {
  --background: #333;
  --text-color: #fff;
  
  /* This variable is not dependent on the theme, change it only if you want to edit the footer */
  --footer-height: 400px;
}
/* If the body has the .light class (light theme enable), we rewrite variables to adapt */
body.light {
  --background: #fff;
  --text-color: #000;
}
```
💡 **Your colleagues will thank you !**
