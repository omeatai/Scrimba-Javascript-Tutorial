# Javascript-Tutorial
Javascript Tutorial by Ifeanyi Omeata

## Tutorial

---

### [1-INTRO TO APIS](#)

<details>
  <summary>1. Introduction with CDNs</summary>

REACT DOCS:

```Javascript
https://reactjs.org/docs/cdn-links.html
```

React and ReactDOM are available over a CDN:

DEVELOPMENT:

```Javascript
<script crossorigin src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
```

PRODUCTION:

```Javascript
<script crossorigin src="https://unpkg.com/react@18/umd/react.production.min.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@18/umd/react-dom.production.min.js"></script>
```

BABEL:

```Javascript
<script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
```

Index.html:

```Javascript
<html>
    <head>
        <link rel="stylesheet" href="index.css">
        <script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
        <script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
        <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
    </head>
    <body>
        <div id="root"></div>
        <script src="index.js" type="text/babel"></script>
    </body>
</html>
```

Index.js:

```Javascript
ReactDOM.render(<h1>Hello, everyone!</h1>, document.getElementById("root"))
```

```Javascript
ReactDOM.render(
    <ul><li>Thing 1</li><li>Thing 2</li></ul>,
    document.getElementById("root")
)
```

Imperative expression:

```Javascript
const h1 = document.createElement("h1")
h1.textContent = "This is an imperative way to program"
h1.className = "header"
document.getElementById("root").append(h1)
```

Declarative expression:

```Javascript
ReactDOM.render(<h1 className="header">Hello, React!</h1>, document.getElementById("root"))
```

</details>

<details>
  <summary>2. Creating Custom JSX Functions in React</summary>

Index.js:

```Javascript
import React from "react"
import ReactDOM from "react-dom"

const page = (
    <div>
        <h1 className="header">This is JSX</h1>
        <p>This is a paragraph</p>
    </div>
)

ReactDOM.render(
    page,
    document.getElementById("root")
)
```

```Javascript
import React from "react"
import ReactDOM from "react-dom"

const navbar = (
    <nav>
        <h1>Bob's Bistro</h1>
        <ul>
            <li>Menu</li>
            <li>About</li>
            <li>Contact</li>
        </ul>
    </nav>
)

ReactDOM.render(navbar, document.getElementById("root"))
```

</details>

<details>
  <summary>3. Create Root for React 18</summary>

```Javascript
import React from "react"
import ReactDOM from "react-dom/client"

const navbar = (
    <nav>
        <h1>Bob's Bistro</h1>
        <ul>
            <li>Menu</li>
            <li>About</li>
            <li>Contact</li>
        </ul>
    </nav>
)

const root = ReactDOM.createRoot(document.getElementById("root"))
root.render(navbar)
```

```Javascript
import React from "react"
import ReactDOM from "react-dom/client"

const page = (
    <div>
        <h1>My awesome website in React</h1>
        <h3>Reasons I love React</h3>
        <ol>
            <li>It's composable</li>
            <li>It's declarative</li>
            <li>It's a hireable skill</li>
            <li>It's actively maintained by skilled people</li>
        </ol>
    </div>
)

const root = ReactDOM.createRoot(document.getElementById("root"))
root.render(page)
```

</details>

<details>
  <summary>4. Creating Custom JSX Components in React </summary>

```Javascript
import React from "react"
import ReactDOM from "react-dom"

function MainContent(){
    return (
        <div>
            <h1>This is a World War!</h1>
            <h2>I don't like wars.</h2>
        </div>
    )
}

ReactDOM.render(
    <div>
        <Navbar />
        <MainContent />
    </div>,
    document.getElementById("root")
)
```

```Javascript
import React from "react"
import ReactDOM from "react-dom"

function Page() {
    return (
        <div>
            <header>
                <nav>
                    <img src="./react-logo.png" width="40px" />
                </nav>
            </header>
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
            <footer>
                <small>© 2021 Ziroll development. All rights reserved.</small>
            </footer>
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))
```

```Javascript
import React from "react"
import ReactDOM from "react-dom"

function Header() {
    return (
        <header>
            <nav>
                <img src="./react-logo.png" width="40px" />
            </nav>
        </header>
    )
}

function Footer() {
    return (
        <footer>
            <small>© 2021 Ziroll development. All rights reserved.</small>
        </footer>
    )
}

function MainContent() {
    return (
        <div>
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
        </div>
    )
}

function Page() {
    return (
        <div>
            <Header />
            <MainContent />
            <Footer />
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))
```

</details>

<details>
  <summary>5. Using ClassName for Styling</summary>

In style.css:

```css
.nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.nav-logo {
    width: 60px;
}

.nav-items {
    list-style: none;
    display: flex;
}

.nav-items > li {
    padding: 10px;
}
```

In index.js:

```Javascript
import React from "react"
import ReactDOM from "react-dom"

function Header() {
    return (
        <header>
            <nav className="nav">
                <img src="./react-logo.png" className="nav-logo" />
                <ul className="nav-items">
                    <li>Pricing</li>
                    <li>About</li>
                    <li>Contact</li>
                </ul>
            </nav>
        </header>
    )
}

function Footer() {
    return (
        <footer>
            <small>© 2021 Ziroll development. All rights reserved.</small>
        </footer>
    )
}

function MainContent() {
    return (
        <div>
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
        </div>
    )
}

function Page() {
    return (
        <div>
            <Header />
            <MainContent />
            <Footer />
        </div>
    )
}

ReactDOM.render(<Page />, document.getElementById("root"))

```

</details>

<details>
  <summary>6. Organizing Components using Imports and Exports</summary>

In index.js:

```Javascript
import React from "react"
import ReactDOM from "react-dom"
import Header from "./Header"
import Footer from "./Footer"
import MainContent from "./MainContent"

function App() {
    return (
        <div>
            <Header />
            <MainContent />
            <Footer />
        </div>
    )
}

ReactDOM.render(<App />, document.getElementById("root"))

```

In Header.js:

```Javascript
import React from "react"

export default function Header() {
    return (
        <header>
            <nav className="nav">
                <img src="./react-logo.png" className="nav-logo" />
                <ul className="nav-items">
                    <li>Pricing</li>
                    <li>About</li>
                    <li>Contact</li>
                </ul>
            </nav>
        </header>
    )
}
```

In Footer.js:

```Javascript
import React from "react"

export default function Footer() {
    return (
        <footer>
            <small>© 2021 Ziroll development. All rights reserved.</small>
        </footer>
    )
}
```

In MainContent.js:

```Javascript
import React from "react"

export default function MainContent() {
    return (
        <div>
            <h1>Reasons I'm excited to learn React</h1>
            <ol>
                <li>It's a popular library, so I'll be
                able to fit in with the cool kids!</li>
                <li>I'm more likely to get a job as a developer
                if I know React</li>
            </ol>
        </div>
    )
}
```

</details>

<details>
  <summary>7. Installing NVM and using Vite for development</summary>

```Javascript
https://vitejs.dev/guide/
```

+METHOD I:

Install NVM:

https://www.youtube.com/watch?v=ohBFbA0O6hs&ab_channel=DevCaf%C3%A9

```Javascript
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | zsh
```

Install Node:

```Javascript
nvm install node
```

```Javascript
nvm install --lts
```

```Javascript
nvm install 10.13
```

Check Current Version:

```Javascript
nvm current

node -v
node --version

npm -v
npm --version
```

List Existing Node Versions:

```Javascript
nvm ls
```

Change Current Node version:

```Javascript
nvm use 15.1.0
```

Uninstall Node Version:

```Javascript
nvm uninstall 10.13.0
```

NVM Use case:

```Javascript
nvm use 10.13.0
```

```Javascript
nvm install -g live-server
```

```Javascript
live-server --help
```


+METHOD II:

Install Homebrew:

```Javascript
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Remove existing Node Versions:

```Javascript
brew uninstall --ignore-dependencies node
brew uninstall --force node
```

Install NVM on macOS:

```Javascript
brew update
brew install nvm
```

create a directory for NVM at home

```Javascript
mkdir ~/.nvm
```

configure the required environment variables

```Javascript
vim ~/.bash_profile
```

```Javascript
export NVM_DIR=~/.nvm
source $(brew --prefix nvm)/nvm.sh
```

```Javascript
Press ESC + :wq to save and close your file.
```

load the variable to the current shell environment

```Javascript
source ~/.bash_profile
```

+INSTALL Vite to create Project:

```Javascript
npm create vite@latest
```

```Javascript
cd <Name of project>
npm install
npm run dev
```

</details>

<details>
  <summary>8. Project Setup with components</summary>

Using Inter Font in index.html:

```html
<html>
    <head>
        <link rel="preconnect" href="https://fonts.googleapis.com">
        <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
        <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <div id="root"></div>
        <script src="index.js"></script>
    </body>
</html>
```

```css
font-family: 'Inter', sans-serif;
```

components/Main.js:

```Javascript
import React from "react"

export default function Main() {
    return <h1>Main component</h1>
}
```

components/Navbar.js:

```Javascript
import React from "react"

export default function Navbar() {
    return <h1>Navbar component</h1>
}
```

App.js:

```Javascript
import React from "react"
import Navbar from "./components/Navbar"
import Main from "./components/Main"

export default function App() {
    return (
        <div className="container">
            <Navbar />
            <Main />
        </div>
    )
}
```

Index.js:

```Javascript
import React from "react"
import ReactDOM from "react-dom"
import App from "./App"

ReactDOM.render(<App />, document.getElementById("root"))
```

</details>

<details>
  <summary>9. Navbar Component and Styling</summary>

components/Navbar.js:

```Javascript
import React from "react"

export default function Navbar() {
    return (
        <nav>
            <img src="../images/react-icon-small.png" className="nav--icon" />
            <h3 className="nav--logo_text">ReactFacts</h3>
            <h4 className="nav--title">React Course - Project 1</h4>
        </nav>
    )
}
```

style.css:

```css
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Inter, sans-serif;
}

nav {
    display: flex;
    align-items: center;
    background-color: #21222A;
    height: 90px;
    padding: 30px 25px;
}

.nav--logo_text, .nav--title {
    margin: 0;
}

.nav--logo_text {
    margin-right: auto;
    color: #61DAFB;
    font-weight: 700;
    font-size: 22px;
}

.nav--title {
    color: #DEEBF8;
    font-weight: 600;
}

.nav--icon {
    height: 30px;
    margin-right: 7px;
}
```

</details>

<details>
  <summary>10. Main Component and Styling</summary>

components/Main.js:

```Javascript
import React from "react"

export default function Main() {
    return (
        <main>
            <h1 className="main--title">Fun facts about React</h1>
            <ul className="main--facts">
                <li>Was first released in 2013</li>
                <li>Was originally created by Jordan Walke</li>
                <li>Has well over 100K stars on GitHub</li>
                <li>Is maintained by Facebook</li>
                <li>Powers thousands of enterprise apps, including mobile apps</li>
            </ul>
        </main>
    )
}
```

style.css:

```css
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: Inter, sans-serif;
    height: 100vh;
    background-color: #282D35;
}

nav {
    display: flex;
    align-items: center;
    background-color: #21222A;
    height: 90px;
    padding: 30px 25px;
}

.nav--logo_text, .nav--title {
    margin: 0;
}

.nav--logo_text {
    margin-right: auto;
    color: #61DAFB;
    font-weight: 700;
    font-size: 22px;
}

.nav--title {
    color: #DEEBF8;
    font-weight: 600;
}

.nav--icon {
    height: 30px;
    margin-right: 7px;
}

main {
    padding: 57px 27px;
    color: white;
}

.main--title {
    margin: 0;
    font-size: 39px;
    letter-spacing: -0.05em;
}

.main--facts {
    margin-top: 46px;
    max-width: 400px;
}

.main--facts > li {
    line-height: 19px;
    padding-block: 10px;
}
```

</details>

<details>
  <summary>11. Color the bullet Marker</summary>

The ::marker CSS pseudo-element selects the marker box of a list item, which typically contains a bullet or number. It works on any element or pseudo-element set to display: list-item, such as the li and summary elements.

Example:

```css
li::marker {
    content: '✝ ';
    font-size: 1.2em;
    color: red;
}
```

style.css:

```css
------------

.main--facts > li::marker {
    font-size: 1.4rem;
    color: #61DAFB;
}
```

</details>

<details>
  <summary>12. Background Logo</summary>

```css
main {
    padding: 57px 27px;
    color: white;
    background-image: url(./images/react-icon-large.png);
    background-repeat: no-repeat;
    background-position: right 75%;
}
```

</details>

<details>
  <summary>13. Deploy your React APP to Netlify</summary>

Check Node version:

```Javascript
node -v
```

Check NPM Version:

```Javascript
npm -v
```

```Javascript
npm install
```

```Javascript
npm run build
```

```Javascript
Deploy Manually
```

</details>

### [2-AIRBNB CLONE](#)

<details>
  <summary>90. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>
