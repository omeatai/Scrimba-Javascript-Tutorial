# Javascript-Tutorial
Learn Javascript

# React-Tutorial

React-Tutorial by Ifeanyi Omeata

## Tutorial

---

### [1-REACT INFO SITE](#)

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
  <summary>14. Project Setup with Navbar component</summary>

index.html:

```html
<html>
    <head>
        <link rel="preconnect" href="https://fonts.googleapis.com">
        <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
        <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;600&display=swap" rel="stylesheet">
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <div id="root"></div>
        <script src="index.js"></script>
    </body>
</html>

```

index.js:

```Javascript
import React from "react"
import ReactDOM from "react-dom"
import App from "./App"

ReactDOM.render(<App />, document.getElementById("root"))
```

App.js:

```Javascript
import React from "react"
import Navbar from "./components/Navbar"

export default function App() {
    return (
        <div>
            <Navbar />
        </div>
    )
}
```

Navbar.js:

```Javascript
import React from "react"

export default function Navbar() {
    return (
        <nav>
            <img src="../images/airbnb-logo.png" className="nav--logo"/>
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
}

nav {
    height: 70px;
    display: flex;
    padding: 20px 36px;
    box-shadow: 0px 2.98256px 7.4564px rgba(0, 0, 0, 0.1);
}

.nav--logo {
    max-width: 100px;
}

```

</details>

<details>
  <summary>15. Hero Component and Styling</summary>

App.js:

```Javascript
import React from "react"
import Navbar from "./components/Navbar"
import Hero from "./components/Hero"

export default function App() {
    return (
        <div>
            <Navbar />
            <Hero />
        </div>
    )
}
```

components/Hero.js:

```Javascript
import React from "react"

export default function Hero() {
    return (
        <section className="hero">
            <img src="../images/photo-grid.png" className="hero--photo" />
            <h1 className="hero--header">Online Experiences</h1>
            <p className="hero--text">Join unique interactive activities led by
            one-of-a-kind hosts—all without leaving home.</p>
        </section>
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
    font-family: 'Poppins', sans-serif;
}

nav {
    height: 70px;
    display: flex;
    padding: 20px 36px;
    box-shadow: 0px 2.98256px 7.4564px rgba(0, 0, 0, 0.1);
}

.nav--logo {
    max-width: 100px;
}

section {
    padding: 20px;
}

.hero {
    display: flex;
    flex-direction: column;
}

.hero--photo {
    max-width: 400px;
    align-self: center;
}

.hero--header {
    margin-bottom: 16px;
}

.hero--text {
    margin-top: 0;
}
```

</details>

<details>
  <summary>16. Card Component and Styling</summary>

App.js:

```Javascript
import React from "react"
import Navbar from "./components/Navbar"
import Hero from "./components/Hero"
import Card from "./components/Card"

export default function App() {
            // <Hero />
    return (
        <div>
            <Navbar />
            <Card />
        </div>
    )
}
```

components/Card.js:

```Javascript
import React from "react"

export default function Card() {
    return (
        <div className="card">
            <img src="../images/katie-zaferes.png" className="card--image" />
            <div className="card--stats">
                <img src="../images/star.png" className="card--star" />
                <span>5.0</span>
                <span className="gray">(6) • </span>
                <span className="gray">USA</span>
            </div>
            <p>Life Lessons with Katie Zaferes</p>
            <p><span className="bold">From $136</span> / person</p>
        </div>
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
    font-family: 'Poppins', sans-serif;
}

nav {
    height: 70px;
    display: flex;
    padding: 20px 36px;
    box-shadow: 0px 2.98256px 7.4564px rgba(0, 0, 0, 0.1);
}

.bold {
    font-weight: bold;
}

.gray {
    color: #918E9B;
}

.nav--logo {
    max-width: 100px;
}

section {
    padding: 20px;
}

.hero {
    display: flex;
    flex-direction: column;
}

.hero--photo {
    max-width: 400px;
    align-self: center;
}

.hero--header {
    margin-bottom: 16px;
}

.hero--text {
    margin-top: 0;
}

.card {
    width: 175px;
    font-size: 12px;
}

.card--image {
    width: 100%;
    border-radius: 9px;
}

.card--stats {
    display: flex;
    align-items: center;
}

.card--star {
    height: 14px;
}
```

</details>

<details>
  <summary>17. JS inside JSX</summary>

```Javascript
import React from "react"
import ReactDOM from "react-dom"

function App() {
    const date = new Date()
    const hours = date.getHours() % 12

    return (
        <h1>It is currently about {hours} o'clock!</h1>
    )
}

ReactDOM.render(<App />, document.getElementById("root"))
```

```Javascript
import React from "react"
import ReactDOM from "react-dom"

function App() {
    const date = new Date()
    const hours = date.getHours()
    let timeOfDay

    if (hours < 12) {
        timeOfDay = "morning"
    } else if (hours >= 12 && hours < 17) {
        timeOfDay = "afternoon"
    } else {
        timeOfDay = "night"
    }

    return (
        <h1>Good {timeOfDay}!</h1>
    )
}

ReactDOM.render(<App />, document.getElementById("root"))

```

</details>

<details>
  <summary>18. Using React Props</summary>

Contact.js:

```Javascript
import React from "react"

export default function Contact(props) {
    return (
        <div className="contact-card">
            <img src={props.img}/>
            <h3>{props.name}</h3>
            <div className="info-group">
                <img src="./images/phone-icon.png" />
                <p>{props.phone}</p>
            </div>
            <div className="info-group">
                <img src="./images/mail-icon.png" />
                <p>{props.email}</p>
            </div>
        </div>
    )
}
```

App.js:

```Javascript
import React from "react"
import Contact from "./Contact"

function App() {
    return (
        <div className="contacts">
            <Contact
                img="./images/mr-whiskerson.png"
                name="Mr. Whiskerson"
                phone="(212) 555-1234"
                email="mr.whiskaz@catnap.meow"
            />
            <Contact
                img="./images/fluffykins.png"
                name="Fluffykins"
                phone="(212) 555-2345"
                email="fluff@me.com"
            />
            <Contact
                img="./images/felix.png"
                name="Felix"
                phone="(212) 555-4567"
                email="thecat@hotmail.com"
            />
            <Contact
                img="./images/pumpkin.png"
                name="Pumpkin"
                phone="(0800) CAT KING"
                email="pumpkin@scrimba.com"
            />
        </div>
    )
}

export default App
```

</details>

<details>
  <summary>19. Destructuring Props</summary>

Contact.js:

```Javascript
import React from "react"

export default function Contact({img, name, phone, email}) {
    return (
        <div className="contact-card">
            <img src={img}/>
            <h3>{name}</h3>
            <div className="info-group">
                <img src="./images/phone-icon.png" />
                <p>{phone}</p>
            </div>
            <div className="info-group">
                <img src="./images/mail-icon.png" />
                <p>{email}</p>
            </div>
        </div>
    )
}
```

</details>

<details>
  <summary>20. Props in Practice</summary>

index.js:

```Javascript
import React from "react"
import ReactDOM from "react-dom"
import App from "./App"


ReactDOM.render(<App />, document.getElementById("root"))
```

App.js:

```Javascript
import React from "react"
import Joke from "./Joke"

export default function App() {
    return (
        <div>
            <Joke
                punchline="It’s hard to explain puns to kleptomaniacs because they always take things literally."
            />
            <Joke
                setup="I got my daughter a fridge for her birthday."
                punchline="I can't wait to see her face light up when she opens it."
            />
            <Joke
                setup="How did the hacker escape the police?"
                punchline="He just ransomware!"
            />
            <Joke
                setup="Why don't pirates travel on mountain roads?"
                punchline="Scurvy."
            />
            <Joke
                setup="Why do bees stay in the hive in the winter?"
                punchline="Swarm."
            />
            <Joke
                setup="What's the best thing about Switzerland?"
                punchline="I don't know, but the flag is a big plus!"
            />
        </div>
    )
}
```

Joke.js:

```Javascript
import React from "react"

export default function Joke(props) {
    return (
        <div>
            <h3>Setup: {props.setup}</h3>
            <p>Punchline: {props.punchline}</p>
            <hr />
        </div>
    )
}
```

</details>

<details>
  <summary>21. Props Conditionals</summary>

Joke.js:

```Javascript
import React from "react"

export default function Joke(props) {
    return (
        <div>
            {props.setup && <h3>Setup: {props.setup}</h3>}
            <p>Punchline: {props.punchline}</p>
            <hr />
        </div>
    )
}
```

Joke.js:

```Javascript
import React from "react"

export default function Joke(props) {
    return (
        <div>
            <h3 style={{display: props.setup ? "block" : "none"}}>Setup: {props.setup}</h3>
            <p>Punchline: {props.punchline}</p>
            <hr />
        </div>
    )
}
```
</details>

<details>
  <summary>22. Passing Card Component Props</summary>

App.js:

```Javascript
import React from "react"
import Navbar from "./components/Navbar"
import Hero from "./components/Hero"
import Card from "./components/Card"

export default function App() {
            // <Hero />
    return (
        <div>
            <Navbar />
            <Card
                img="katie-zaferes.png"
                rating="5.0"
                reviewCount={6}
                country="USA"
                title="Life Lessons with Katie Zaferes"
                price={136}
            />
        </div>
    )
}
```

components/Card.js:

```Javascript
import React from "react"

export default function Card(props) {
    return (
        <div className="card">
            <img src={`../images/${props.img}`} className="card--image" />
            <div className="card--stats">
                <img src="../images/star.png" className="card--star" />
                <span>{props.rating}</span>
                <span className="gray">({props.reviewCount}) • </span>
                <span className="gray">{props.country}</span>
            </div>
            <p>{props.title}</p>
            <p><span className="bold">From ${props.price}</span> / person</p>
        </div>
    )
}
```

</details>

<details>
  <summary>23. Using Javascript Map Method</summary>

```Javascript
const array1 = [1, 4, 9, 16];

// pass a function to map
const map1 = array1.map(x => x * 2);

console.log(map1);
// expected output: Array [2, 8, 18, 32]
```

```Javascript
/*
Challenge 1:
Given an array of numbers, return an array of each number, squared
*/
const nums = [1, 2, 3, 4, 5]

const squares = nums.map(function(num) {
    return num * num
})

console.log(squares)
// [1, 4, 9, 16, 25]
```

```Javascript
/*
Challenge 2:
Given an array of strings, return an array where
the first letter of each string is capitalized
*/
const names = ["alice", "bob", "charlie", "danielle"]

const capitalized = names.map((name) => {
    return name[0].toUpperCase() + name.slice(1)
})

console.log(capitalized)
// ["Alice", "Bob", "Charlie", "Danielle"]
```

```Javascript
/*
Challenge 3:
Given an array of strings, return an array of strings that wraps each
of the original strings in an HTML-like <p></p> tag.

E.g. given: ["Bulbasaur", "Charmander", "Squirtle"]
return: ["<p>Bulbasaur</p>", "<p>Charmander</p>", "<p>Squirtle</p>"]
*/
const pokemon = ["Bulbasaur", "Charmander", "Squirtle"]

const wrapped = pokemon.map( item => `<p>${item}</p>`)
console.log(wrapped)
// ["<p>Bulbasaur</p>", "<p>Charmander</p>", "<p>Squirtle</p>"]
```

```Javascript
// Arrow function
map((element) => { /* … */ })
map((element, index) => { /* … */ })
map((element, index, array) => { /* … */ })

// Callback function
map(callbackFn)
map(callbackFn, thisArg)

// Inline callback function
map(function(element) { /* … */ })
map(function(element, index) { /* … */ })
map(function(element, index, array){ /* … */ })
map(function(element, index, array) { /* … */ }, thisArg)
```

```Javascript
The function is called with the following arguments:

element = The current element being processed in the array.
index = The index of the current element being processed in the array.
array = The array map was called upon.
thisArg (Optional) = Value to use as this when executing callbackFn.
```

</details>

<details>
  <summary>24. React renders Arrays</summary>

```Javascript
import React from "react"
import Joke from "./Joke"

export default function App() {
    const colors = [
            <h3>Red</h3>,
            <h3>Orange</h3>,
            <h3>Yellow</h3>,
            <h3>Green</h3>,
            <h3>Blue</h3>,
            <h3>Indigo</h3>,
            <h3>Violet</h3>
        ]
    return (
        <div>
            {colors}
        </div>
    )
}
```

jokesData.js:

```Javascript
export default [
    {
        setup: "I got my daughter a fridge for her birthday.",
        punchline: "I can't wait to see her face light up when she opens it."
    },
    {
        setup: "How did the hacker escape the police?",
        punchline: "He just ransomware!"
    },
    {
        setup: "Why don't pirates travel on mountain roads?",
        punchline: "Scurvy."
    },
    {
        setup: "Why do bees stay in the hive in the winter?",
        punchline: "Swarm."
    },
    {
        setup: "What's the best thing about Switzerland?",
        punchline: "I don't know, but the flag is a big plus!"
    }
]
```

Joke.js

```Javascript
import React from "react"

export default function Joke(props) {
    return (
        <div>
            {props.setup && <h3>Setup: {props.setup}</h3>}
            <p>Punchline: {props.punchline}</p>
            <hr />
        </div>
    )
}
```

App.js:

```Javascript
import React from "react"
import Joke from "./Joke"
import jokesData from "./jokesData"

export default function App() {
    const jokeElements = jokesData.map(joke => {
        return <Joke setup={joke.setup} punchline={joke.punchline} />
    })
    return (
        <div>
            {jokeElements}
        </div>
    )
}
```

</details>

<details>
  <summary>25. Map data into components</summary>

data.js:

```Javascript
export default [
    {
        id: 1,
        title: "Life Lessons with Katie Zaferes",
        description: "I will share with you what I call \"Positively Impactful Moments of Disappointment.\" Throughout my career, many of my highest moments only came after setbacks and losses. But learning from those difficult moments is what gave me the ability to rise above them and reach my goals.",
        price: 136,
        coverImg: "katie-zaferes.png",
        stats: {
            rating: 5.0,
            reviewCount: 6
        },
        location: "Online",
        openSpots: 0,
    },
    {
        id: 2,
        title: "Learn Wedding Photography",
        description: "Interested in becoming a wedding photographer? For beginner and experienced photographers alike, join us in learning techniques required to leave the happy couple with memories that'll last a lifetime.",
        price: 125,
        coverImg: "wedding-photography.png",
        stats: {
            rating: 5.0,
            reviewCount: 30
        },
        location: "Online",
        openSpots: 27,
    },
    {
        id: 3,
        title: "Group Mountain Biking",
        description: "Experience the beautiful Norwegian landscape and meet new friends all while conquering rugged terrain on your mountain bike. (Bike provided!)",
        price: 50,
        coverImg: "mountain-bike.png",
        stats: {
            rating: 4.8,
            reviewCount: 2
        },
        location: "Norway",
        openSpots: 3,
    }
]
```

components/Card.js:

```Javascript
import React from "react"

export default function Card(props) {
    return (
        <div className="card">
            <img src={`../images/${props.img}`} className="card--image" />
            <div className="card--stats">
                <img src="../images/star.png" className="card--star" />
                <span>{props.rating}</span>
                <span className="gray">({props.reviewCount}) • </span>
                <span className="gray">{props.location}</span>
            </div>
            <p>{props.title}</p>
            <p><span className="bold">From ${props.price}</span> / person</p>
        </div>
    )
}
```

App.js:

```Javascript
import React from "react"
import Navbar from "./components/Navbar"
import Hero from "./components/Hero"
import Card from "./components/Card"
import data from "./data"

export default function App() {
            // <Hero />
    const cards = data.map(item => {
        return (
            <Card
                img={item.coverImg}
                rating={item.stats.rating}
                reviewCount={item.stats.reviewCount}
                location={item.location}
                title={item.title}
                price={item.price}
            />
        )
    })

    return (
        <div>
            <Navbar />
            {cards}
        </div>
    )
}
```

style.css

```css
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
}

nav {
    height: 70px;
    display: flex;
    padding: 20px 36px;
    box-shadow: 0px 2.98256px 7.4564px rgba(0, 0, 0, 0.1);
}

.bold {
    font-weight: bold;
}

.gray {
    color: #918E9B;
}

.nav--logo {
    max-width: 100px;
}

section {
    padding: 20px;
}

.hero {
    display: flex;
    flex-direction: column;
}

.hero--photo {
    max-width: 400px;
    align-self: center;
}

.hero--header {
    margin-bottom: 16px;
}

.hero--text {
    margin-top: 0;
}

.cards-list {
    display: flex;
    flex-wrap: nowrap;
    gap: 20px;
    overflow-x: auto;
}

.card {
    width: 175px;
    font-size: 12px;
    flex: 0 0 auto;         /* ADD */
    display: flex;          /* ADD */
    flex-direction: column; /* ADD */
}

.card--image {
    width: 100%;
    border-radius: 9px;
    margin-bottom: 9px;
}

/* ADD */
.card--title {
    overflow: hidden;
    text-overflow: ellipsis;
}

.card--stats {
    display: flex;
    align-items: center;
}

.card--star {
    height: 14px;
}

/* ADD */
.card--price {
    margin-top: auto;
}
```

</details>

<details>
  <summary>26. Adding Prop key</summary>

```Javascript
import React from "react"
import Navbar from "./components/Navbar"
import Hero from "./components/Hero"
import Card from "./components/Card"
import data from "./data"

export default function App() {
            // <Hero />
    const cards = data.map(item => {
        return (
            <Card
                key={item.id}
                img={item.coverImg}
                rating={item.stats.rating}
                reviewCount={item.stats.reviewCount}
                location={item.location}
                title={item.title}
                price={item.price}
            />
        )
    })

    return (
        <div>
            <Navbar />
            <section className="cards-list">
                {cards}
            </section>
        </div>
    )
}
```

</details>

<details>
  <summary>27. Sold Out Badge Conditional</summary>

```Javascript
import React from "react"

export default function Card(props) {
    let badgeText
    if (props.openSpots === 0) {
        badgeText = "SOLD OUT"
    } else if (props.location === "Online") {
        badgeText = "ONLINE"
    }

    return (
        <div className="card">
            {badgeText && <div className="card--badge">{badgeText}</div>}
            <img src={`../images/${props.img}`} className="card--image" />
            <div className="card--stats">
                <img src="../images/star.png" className="card--star" />
                <span>{props.rating}</span>
                <span className="gray">({props.reviewCount}) • </span>
                <span className="gray">{props.location}</span>
            </div>
            <p className="card--title">{props.title}</p>
            <p className="card--price"><span className="bold">From ${props.price}</span> / person</p>
        </div>
    )
}

```

```css

.card {
    width: 175px;
    font-size: 12px;
    flex: 0 0 auto;
    display: flex;
    flex-direction: column;
    position: relative; /* ADD */
}

.card--badge {
    position: absolute;
    top: 6px;
    left: 6px;
    background-color: white;
    padding: 5px 7px;
    border-radius: 2px;
    font-weight: bold;
}
```

</details>

<details>
  <summary>28. Pass Objects as Props</summary>

components/Card.js:

```Javascript
import React from "react"

export default function Card(props) {
    let badgeText
    if (props.item.openSpots === 0) {
        badgeText = "SOLD OUT"
    } else if (props.item.location === "Online") {
        badgeText = "ONLINE"
    }

    return (
        <div className="card">
            {badgeText && <div className="card--badge">{badgeText}</div>}
            <img src={`../images/${props.item.coverImg}`} className="card--image" />
            <div className="card--stats">
                <img src="../images/star.png" className="card--star" />
                <span>{props.item.stats.rating}</span>
                <span className="gray">({props.item.stats.reviewCount}) • </span>
                <span className="gray">{props.item.location}</span>
            </div>
            <p className="card--title">{props.item.title}</p>
            <p className="card--price"><span className="bold">From ${props.item.price}</span> / person</p>
        </div>
    )
}
```

App.js:

```Javascript
import React from "react"
import Navbar from "./components/Navbar"
import Hero from "./components/Hero"
import Card from "./components/Card"
import data from "./data"

export default function App() {
    const cards = data.map(item => {
        return (
            <Card
                key={item.id}
                item={item}
            />
        )
    })

            // <Hero />
    return (
        <div>
            <Navbar />
            <section className="cards-list">
                {cards}
            </section>
        </div>
    )
}
```

</details>

<details>
  <summary>29. Spread Objects as Props</summary>

```Javascript
import React from "react"

export default function Card(props) {
    let badgeText
    if (props.openSpots === 0) {
        badgeText = "SOLD OUT"
    } else if (props.location === "Online") {
        badgeText = "ONLINE"
    }

    return (
        <div className="card">
            {
                badgeText &&
                <div className="card--badge">{badgeText}</div>
            }
            <img
                src={`../images/${props.coverImg}`}
                className="card--image"
            />
            <div className="card--stats">
                <img src="../images/star.png" className="card--star" />
                <span>{props.stats.rating}</span>
                <span className="gray">({props.stats.reviewCount}) • </span>
                <span className="gray">{props.location}</span>
            </div>
            <p className="card--title">{props.title}</p>
            <p className="card--price">
                <span className="bold">From ${props.price}</span> / person
            </p>
        </div>
    )
}
```

App.js:

```Javascript
import React from "react"
import Navbar from "./components/Navbar"
import Hero from "./components/Hero"
import Card from "./components/Card"
import data from "./data"

export default function App() {
    const cards = data.map(item => {
        return (
            <Card
                key={item.id}
                {...item}
            />
        )
    })

    return (
        <div>
            <Navbar />
            <Hero />
            <section className="cards-list">
                {cards}
            </section>
        </div>
    )
}

```

</details>

### [3-MEME GENERATOR](#)

<details>
  <summary>30. Header component and styling</summary>

App.js:

```Javascript
import React from "react"
import Header from "./components/Header"

export default function App() {
    return (
        <div>
            <Header />
        </div>
    )
}
```

components/Header.js:

```Javascript
import React from "react"

export default function Header() {
    return (
        <header className="header">
            <img
                src="./images/troll-face.png"
                className="header--image"
            />
            <h2 className="header--title">Meme Generator</h2>
            <h4 className="header--project">React Course - Project 3</h4>
        </header>
    )
}
```

```css
* {
    box-sizing: border-box;
}

body {
    font-family: "Karla", sans-serif;
    margin: 0;
}

.header {
    display: flex;
    align-items: center;
    height: 65px;
    background: linear-gradient(90deg, #672280 1.18%, #A626D3 100%);
    color: white;
    padding: 20px;
}

.header--image {
    height: 100%;
    margin-right: 6px;
}

.header--title {
    font-size: 1.25rem;
    margin-right: auto;
}

.header--project {
    font-size: 0.75rem;
    font-weight: 500;
}
```

</details>

<details>
  <summary>31. Meme component and styling</summary>

App.js:

```Javascript
import React from "react"
import Header from "./components/Header"
import Meme from "./components/Meme"

export default function App() {
    return (
        <div>
            <Header />
            <Meme />
        </div>
    )
}
```

components/Meme.js:

```Javascript
import React from "react"

export default function Meme() {
    return (
        <main>
            <form className="form">
                <input
                    type="text"
                    placeholder="Top text"
                    className="form--input"
                />
                <input
                    type="text"
                    placeholder="Bottom text"
                    className="form--input"
                />
                <button
                    className="form--button"
                >
                    Get a new meme image 🖼
                </button>
            </form>
        </main>
    )
}
```

```css
* {
    box-sizing: border-box;
}

body {
    font-family: "Karla", sans-serif;
    margin: 0;
}

main {
    padding: 36px;
}

.header {
    display: flex;
    align-items: center;
    height: 65px;
    background: linear-gradient(90deg, #672280 1.18%, #A626D3 100%);
    color: white;
    padding: 20px;
}

.header--image {
    height: 100%;
    margin-right: 6px;
}

.header--title {
    font-size: 1.25rem;
    margin-right: auto;
}

.header--project {
    font-size: 0.75rem;
    font-weight: 500;
}

.form {
    display: grid;
    grid-template: 40px 40px / 1fr 1fr;
    gap: 17px;
}

.form--input {
    font-family: "Karla", sans-serif;
    border-radius: 5px;
    border: 1px solid #D5D4D8;
    text-indent: 5px;
}

.form--button {
    grid-column: 1 / -1;
    font-family: "Karla", sans-serif;
    border-radius: 5px;
    background: linear-gradient(90.41deg, #711F8D 1.14%, #A818DA 100%);
    color: white;
    border: none;
    cursor: pointer;
}
```

</details>

<details>
  <summary>32. React Synthetic Events</summary>

https://reactjs.org/docs/events.html

Clipboard Events:
https://reactjs.org/docs/events.html#clipboard-events

```Javascript
onCopy
onCut
onPaste
```

Composition Events:
https://reactjs.org/docs/events.html#composition-events

```Javascript
onCompositionEnd
onCompositionStart
onCompositionUpdate
```

Keyboard Events:
https://reactjs.org/docs/events.html#keyboard-events

```Javascript
onKeyDown
onKeyPress
onKeyUp
```

Focus Events:
https://reactjs.org/docs/events.html#focus-events

```Javascript
onFocus
onBlur
```

Form Events:
https://reactjs.org/docs/events.html#form-events

```Javascript
onChange
onInput
onInvalid
onReset
onSubmit
```

Generic Events:
https://reactjs.org/docs/events.html#generic-events

```Javascript
onError
onLoad
```

Mouse Events:
https://reactjs.org/docs/events.html#mouse-events

```Javascript
onClick
onContextMenu
onDoubleClick
onDrag
onDragEnd
onDragEnter
onDragExit
onDragLeave
onDragOver
onDragStart
onDrop
onMouseDown
onMouseEnter
onMouseLeave
onMouseMove
onMouseOut
onMouseOver
onMouseUp
```

Pointer Events:
https://reactjs.org/docs/events.html#pointer-events

```Javascript
onPointerDown
onPointerMove
onPointerUp
onPointerCancel
onGotPointerCapture
onLostPointerCapture
onPointerEnter
onPointerLeave
onPointerOver
onPointerOut
```

Selection Events:
https://reactjs.org/docs/events.html#selection-events

```Javascript
onSelect
```

Touch Events:
https://reactjs.org/docs/events.html#touch-events

```Javascript
onTouchCancel
onTouchEnd
onTouchMove
onTouchStart
```

UI Events:
https://reactjs.org/docs/events.html#ui-events

```Javascript
onScroll
```

Wheel Events:
https://reactjs.org/docs/events.html#wheel-events

```Javascript
onWheel
```

Media Events:
https://reactjs.org/docs/events.html#media-events

```Javascript
onAbort
onCanPlay
onCanPlayThrough
onDurationChange
onEmptied
onEncrypted
onEnded
onError
onLoadedData
onLoadedMetadata
onLoadStart
onPause
onPlay
onPlaying
onProgress
onRateChange
onSeeked
onSeeking
onStalled
onSuspend
onTimeUpdate
onVolumeChange
onWaiting
```

Image Events:
https://reactjs.org/docs/events.html#image-events

```Javascript
onLoad
onError
```

Animation Events:
https://reactjs.org/docs/events.html#animation-events

```Javascript
onAnimationStart
onAnimationEnd
onAnimationIteration
```

Transition Events:
https://reactjs.org/docs/events.html#transition-events

```Javascript
onTransitionEnd
```

Other Events:
https://reactjs.org/docs/events.html#other-events

```Javascript
onToggle
```

</details>

<details>
  <summary>33. React Click and Mouse Event Listeners</summary>

App.js:

```Javascript
import React from "react"

export default function App() {
    function handleClick() {
        console.log("I was clicked!")
    }

    function handleOnMouseOver() {
        console.log("MouseOver")
    }

    return (
        <div className="container">
            <img
                src="https://picsum.photos/640/360"
                onMouseOver={handleOnMouseOver}
            />
            <button onClick={handleClick}>Click me</button>
        </div>
    )
}
```

</details>

<details>
  <summary>34. Get Random Meme Url</summary>

components/Meme.js:

```Javascript
import React from "react"
import memesData from "../memesData.js"

export default function Meme() {

    function getMemeImage() {
        const memesArray = memesData.data.memes
        const randomNumber = Math.floor(Math.random() * memesArray.length)
        const url = memesArray[randomNumber].url
        console.log(url)
    }

    return (
        <main>
            <div className="form">
                <input
                    type="text"
                    placeholder="Top text"
                    className="form--input"
                />
                <input
                    type="text"
                    placeholder="Bottom text"
                    className="form--input"
                />
                <button
                    className="form--button"
                    onClick={getMemeImage}
                >
                    Get a new meme image 🖼
                </button>
            </div>
        </main>
    )
}

```

</details>

<details>
  <summary>35. Props & State JS representation</summary>

index.js:

```Javascript
function greeting(name) {
    const date = new Date()
    const hours = date.getHours()

    let timeOfDay
    if(hours >= 4 && hours < 12) {
        timeOfDay = "morning"
    } else if(hours >= 12 && hours < 17) {
        timeOfDay = "afternoon"
    } else if(hours >= 17 && hours < 20) {
        timeOfDay = "evening"
    } else {
        timeOfDay = "night"
    }

    return `Good ${timeOfDay}, ${name}!`
}

console.log(greeting("Bob"))
```

</details>

<details>
  <summary>36. Changing State</summary>

App.js:

```Javascript
import React from "react"

export default function App() {
    const [isImportant, setIsImportant] = React.useState("Yes")

    function handleClick() {
        setIsImportant("No")
    }

    return (
        <div className="state">
            <h1 className="state--title">Is state important to know?</h1>
            <div className="state--value" onClick={handleClick}>
                <h1>{isImportant}</h1>
            </div>
        </div>
    )
}
```

</details>

<details>
  <summary>37. Changing Count state</summary>

App.js:

```Javascript
import React from "react"

export default function App() {
    const [count, setCount] = React.useState(0)

    function add() {
        setCount(prevCount => prevCount + 1)
    }

    function subtract() {
        setCount(prevCount => prevCount - 1)
    }

    return (
        <div className="counter">
            <button className="counter--minus" onClick={subtract}>–</button>
            <div className="counter--count">
                <h1>{count}</h1>
            </div>
            <button className="counter--plus" onClick={add}>+</button>
        </div>
    )
}
```

</details>

<details>
  <summary>38. Changing MemeImage State</summary>

components/Meme.js:

```Javascript
import React from "react"
import memesData from "../memesData.js"

export default function Meme() {
    const [memeImage, setMemeImage] = React.useState("http://i.imgflip.com/1bij.jpg")

    function getMemeImage() {
        const memesArray = memesData.data.memes
        const randomNumber = Math.floor(Math.random() * memesArray.length)
        setMemeImage(memesArray[randomNumber].url)
    }

    return (
        <main>
            <div className="form">
                <input
                    type="text"
                    placeholder="Top text"
                    className="form--input"
                />
                <input
                    type="text"
                    placeholder="Bottom text"
                    className="form--input"
                />
                <button
                    className="form--button"
                    onClick={getMemeImage}
                >
                    Get a new meme image 🖼
                </button>
            </div>
            <img src={memeImage} className="meme--image" />
        </main>
    )
}
```

</details>

<details>
  <summary>39. Ternary Operator</summary>

App.js:

```Javascript
import React from "react"

export default function App() {
    const isGoingOut = false

    return (
        <div className="state">
            <h1 className="state--title">Do I feel like going out tonight?</h1>
            <div className="state--value">
                <h1>{isGoingOut ? "Yes" : "No"}</h1>
            </div>
        </div>
    )
}
```

```Javascript
import React from "react"

export default function App() {
    const [isGoingOut, setIsGoingOut] = React.useState(true)

    function changeMind() {
        setIsGoingOut(prevState => !prevState)
    }

    return (
        <div className="state">
            <h1 className="state--title">Do I feel like going out tonight?</h1>
            <div onClick={changeMind} className="state--value">
                <h1>{isGoingOut ? "Yes" : "No"}</h1>
            </div>
        </div>
    )
}
```

</details>

<details>
  <summary>40. Arrays in State</summary>

index.js:

```Javascript
import React from 'react';
import ReactDOM from 'react-dom';

function App() {
    const [thingsArray, setThingsArray] = React.useState(["Thing 1", "Thing 2"])

    function addItem() {
        setThingsArray(prevThingsArray => {
            return [...prevThingsArray, `Thing ${prevThingsArray.length + 1}`]
        })
    }

    const thingsElements = thingsArray.map(thing => <p key={thing}>{thing}</p>)

    return (
        <div>
            <button onClick={addItem}>Add Item</button>
            {thingsElements}
        </div>
    )
}

ReactDOM.render(<App />, document.getElementById('root'));
```

</details>

<details>
  <summary>41. Objects in State</summary>

App.js:

```Javascript
import React from "react"

export default function App() {
    const [contact, setContact] = React.useState({
        firstName: "John",
        lastName: "Doe",
        phone: "+1 (719) 555-1212",
        email: "itsmyrealname@example.com",
        isFavorite: false
    })

    let starIcon = contact.isFavorite ? "star-filled.png" : "star-empty.png"

    function toggleFavorite() {
        setContact(prevContact => ({
            ...prevContact,
            isFavorite: !prevContact.isFavorite
        }))
    }

    return (
        <main>
            <article className="card">
                <img src="./images/user.png" className="card--image" />
                <div className="card--info">
                    <img
                        src={`../images/${starIcon}`}
                        className="card--favorite"
                        onClick={toggleFavorite}
                    />
                    <h2 className="card--name">
                        {contact.firstName} {contact.lastName}
                    </h2>
                    <p className="card--contact">{contact.phone}</p>
                    <p className="card--contact">{contact.email}</p>
                </div>

            </article>
        </main>
    )
}
```

```Javascript
import React from "react"
import memesData from "../memesData.js"

export default function Meme() {
    const [meme, setMeme] = React.useState({
        topText: "",
        bottomText: "",
        randomImage: "http://i.imgflip.com/1bij.jpg"
    })
    const [allMemeImages, setAllMemeImages] = React.useState(memesData)


    function getMemeImage() {
        const memesArray = allMemeImages.data.memes
        const randomNumber = Math.floor(Math.random() * memesArray.length)
        const url = memesArray[randomNumber].url
        setMeme(prevMeme => ({
            ...prevMeme,
            randomImage: url
        }))

    }

    return (
        <main>
            <div className="form">
                <input
                    type="text"
                    placeholder="Top text"
                    className="form--input"
                />
                <input
                    type="text"
                    placeholder="Bottom text"
                    className="form--input"
                />
                <button
                    className="form--button"
                    onClick={getMemeImage}
                >
                    Get a new meme image 🖼
                </button>
            </div>
            <img src={meme.randomImage} className="meme--image" />
        </main>
    )
}
```

</details>

<details>
  <summary>42. Passing State as Props</summary>

App.js:

```Javascript
import React from "react"
import Count from "./Count"

export default function App() {
    const [count, setCount] = React.useState(0)

    function add() {
        setCount(prevCount => prevCount + 1)
    }

    function subtract() {
        setCount(prevCount => prevCount - 1)
    }

    console.log("App component rendered")

    return (
        <div className="counter">
            <button className="counter--minus" onClick={subtract}>–</button>
            <Count number={count} />
            <button className="counter--plus" onClick={add}>+</button>
        </div>
    )
}
```

Count.js

```Javascript
import React from "react"

export default function Count(props) {
    console.log("Count component rendered")

    return (
        <div className="counter--count">
            <h1>{props.number}</h1>
        </div>
    )
}
```

</details>

<details>
  <summary>43. Setting State from Child Components</summary>

App.js:

```Javascript
import React from "react"
import Star from "./Star"

export default function App() {
    const [contact, setContact] = React.useState({
        firstName: "John",
        lastName: "Doe",
        phone: "+1 (719) 555-1212",
        email: "itsmyrealname@example.com",
        isFavorite: true
    })

    function toggleFavorite() {
        setContact(prevContact => ({
            ...prevContact,
            isFavorite: !prevContact.isFavorite
        }))
    }

    return (
        <main>
            <article className="card">
                <img src="./images/user.png" className="card--image" />
                <div className="card--info">
                    <Star isFilled={contact.isFavorite} handleClick={toggleFavorite} />
                    <h2 className="card--name">
                        {contact.firstName} {contact.lastName}
                    </h2>
                    <p className="card--contact">{contact.phone}</p>
                    <p className="card--contact">{contact.email}</p>
                </div>

            </article>
        </main>
    )
}
```

Star.js:

```Javascript
import React from "react"

export default function Star(props) {
    const starIcon = props.isFilled ? "star-filled.png" : "star-empty.png"
    return (
        <img
            src={`../images/${starIcon}`}
            className="card--favorite"
            onClick={props.handleClick}
        />
    )
}
```

</details>

<details>
  <summary>44. React Dynamic Styles</summary>

index.js:

```Javascript
import React from "react"
import ReactDOM from "react-dom"
import App from "./App"

ReactDOM.render(<App darkMode={false} />, document.getElementById("root"))
```

App.js:

```Javascript
import React from "react"
import boxes from "./boxes"

export default function App(props) {
    const [squares, setSquares] = React.useState(boxes)

    const styles = {
        backgroundColor: props.darkMode ? "#222222" : "#cccccc"
    }

    const squareElements = squares.map(square => (
        <div style={styles} className="box" key={square.id}></div>
    ))
    return (
        <main>
            {squareElements}
        </main>
    )
}
```

</details>

<details>
  <summary>45. Dynamic Styles on Boxes</summary>

boxes.js:

```Javascript
export default [
    {
        id: 1,
        on: true
    },
    {
        id: 2,
        on: false
    },
    {
        id: 3,
        on: true
    },
    {
        id: 4,
        on: true
    },
    {
        id: 5,
        on: false
    },
    {
        id: 6,
        on: false
    },
]
```

App.js:

```Javascript
import React from "react"
import boxes from "./boxes"
import Box from "./Box"

export default function App() {
    const [squares, setSquares] = React.useState(boxes)

    const squareElements = squares.map(square => (
        <Box key={square.id} on={square.on} />
    ))

    return (
        <main>
            {squareElements}
        </main>
    )
}
```

Box.js:

```Javascript
import React from "react"

export default function Box(props) {
    const styles = {
        backgroundColor: props.on ? "#222222" : "transparent"
    }

    return (
        <div style={styles} className="box"></div>
    )
}
```

</details>

<details>
  <summary>46. Using toggle functions</summary>

App.js:

```Javascript
import React from "react"
import boxes from "./boxes"
import Box from "./Box"

export default function App() {
    const [squares, setSquares] = React.useState(boxes)

    function toggle(id) {
        setSquares(prevSquares => {
            return prevSquares.map((square) => {
                return square.id === id ? {...square, on: !square.on} : square
            })
        })
    }

    const squareElements = squares.map(square => (
        <Box
            key={square.id}
            on={square.on}
            toggle={() => toggle(square.id)}
        />
    ))

    return (
        <main>
            {squareElements}
        </main>
    )
}
```

Box.js:

```Javascript
import React from "react"

export default function Box(props) {
    const styles = {
        backgroundColor: props.on ? "#222222" : "transparent"
    }

    return (
        <div
            style={styles}
            className="box"
            onClick={props.toggle}
        >
        </div>
    )
}
```

</details>

<details>
  <summary>47. Conditional rendering</summary>

Joke.js:

```Javascript
import React from "react"

export default function Joke(props) {
    const [isShown, setIsShown] = React.useState(false)

    function toggleShown(){
        setIsShown(prevShown => !prevShown)
    }
    return (
        <div>
            {props.setup && <h3>{props.setup}</h3>}
            {isShown && <p>{props.punchline}</p>}
            <button onClick={toggleShown}>Show Punchline</button>
            <hr />
        </div>
    )
}

const cond1 = false
const cond2 = false
if(cond1 && console.log("Hello there")) {
    // this code will NOT run
}
```

```Javascript
import React from "react"

export default function Joke(props) {
    const [isShown, setIsShown] = React.useState(false)
    function toggleShown(){
        setIsShown(prevShown => !prevShown)
    }

    return (
        <div>
            {props.setup && <h3>{props.setup}</h3>}
            {isShown && <p>{props.punchline}</p>}
            <button onClick={toggleShown}>{isShown ? "Hide" : "Show"} Punchline</button>
            <hr />
        </div>
    )
}
```

```Javascript
import React from "react"

export default function App() {
    const [messages, setMessages] = React.useState(["a", "b"])

    return (
        <div>
            {
                messages.length === 0 ?
                <h1>You're all caught up!</h1> :
                <h1>
                    You have {messages.length} unread {messages.length > 1 ? "messages" : "message"}
                </h1>
            }
        </div>
    )
}
```

</details>

<details>
  <summary>48. Javascript Form Handling</summary>

```Javascript
document.getElementById("my-form").addEventListener("submit", function(event) {
    event.preventDefault()
    const formElements = event.target.elements
    const {firstName, lastName} = formElements
    submitViaAPI({
        firstName: firstName.value,
        lastName: lastName.value
    })
})

function submitViaAPI(data) {
    console.log(data)
    console.log("Submitted!")
}

```

</details>

<details>
  <summary>49. Form State Inputs</summary>

Form.js:

```Javascript
import React from "react"

export default function Form() {
    const [formData, setFormData] = React.useState(
        {firstName: "", lastName: ""}
    )

    console.log(formData)

    function handleChange(event) {
        setFormData(prevFormData => {
            return {
                ...prevFormData,
                [event.target.name]: event.target.value
            }
        })
    }

    return (
        <form>
            <input
                type="text"
                placeholder="First Name"
                onChange={handleChange}
                name="firstName"
            />
            <input
                type="text"
                placeholder="Last Name"
                onChange={handleChange}
                name="lastName"
            />
        </form>
    )
}
```

</details>

<details>
  <summary>50. Form Controlled State Inputs</summary>

Form.js:

```Javascript
import React from "react"

export default function Form() {
    const [formData, setFormData] = React.useState(
        {firstName: "", lastName: "", email: ""}
    )

    function handleChange(event) {
        setFormData(prevFormData => {
            return {
                ...prevFormData,
                [event.target.name]: event.target.value
            }
        })
    }

    return (
        <form>
            <input
                type="text"
                placeholder="First Name"
                onChange={handleChange}
                name="firstName"
                value={formData.firstName}
            />
            <input
                type="text"
                placeholder="Last Name"
                onChange={handleChange}
                name="lastName"
                value={formData.lastName}
            />
            <input
                type="email"
                placeholder="Email"
                onChange={handleChange}
                name="email"
                value={formData.email}
            />
        </form>
    )
}
```

</details>

<details>
  <summary>51. Forms - Textarea</summary>

Form.js:

```Javascript
import React from "react"

export default function Form() {
    const [formData, setFormData] = React.useState(
        {firstName: "", lastName: "", email: "", comments: ""}
    )

    console.log(formData.comments)

    function handleChange(event) {
        setFormData(prevFormData => {
            return {
                ...prevFormData,
                [event.target.name]: event.target.value
            }
        })
    }

    return (
        <form>
            <input
                type="text"
                placeholder="First Name"
                onChange={handleChange}
                name="firstName"
                value={formData.firstName}
            />
            <input
                type="text"
                placeholder="Last Name"
                onChange={handleChange}
                name="lastName"
                value={formData.lastName}
            />
            <input
                type="email"
                placeholder="Email"
                onChange={handleChange}
                name="email"
                value={formData.email}
            />
            <textarea
                value={formData.comments}
                placeholder="Comments"
                onChange={handleChange}
                name="comments"
            />
        </form>
    )
}
```

</details>

<details>
  <summary>52. Forms - Checkbox</summary>

Form.js:

```Javascript
import React from "react"

export default function Form() {
    const [formData, setFormData] = React.useState(
        {
            firstName: "",
            lastName: "",
            email: "",
            comments: "",
            isFriendly: true
        }
    )

    function handleChange(event) {
        const {name, value, type, checked} = event.target
        setFormData(prevFormData => {
            return {
                ...prevFormData,
                [name]: type === "checkbox" ? checked : value
            }
        })
    }

    return (
        <form>
            <input
                type="text"
                placeholder="First Name"
                onChange={handleChange}
                name="firstName"
                value={formData.firstName}
            />
            <input
                type="text"
                placeholder="Last Name"
                onChange={handleChange}
                name="lastName"
                value={formData.lastName}
            />
            <input
                type="email"
                placeholder="Email"
                onChange={handleChange}
                name="email"
                value={formData.email}
            />
            <textarea
                value={formData.comments}
                placeholder="Comments"
                onChange={handleChange}
                name="comments"
            />
            <input
                type="checkbox"
                id="isFriendly"
                checked={formData.isFriendly}
                onChange={handleChange}
                name="isFriendly"
            />
            <label htmlFor="isFriendly">Are you friendly?</label>
            <br />
        </form>
    )
}

```

</details>

<details>
  <summary>53. Forms - Radio Buttons</summary>

Form.js:

```Javascript
import React from "react"

export default function Form() {
    const [formData, setFormData] = React.useState(
        {
            firstName: "",
            lastName: "",
            email: "",
            comments: "",
            isFriendly: true,
            employment: ""
        }
    )
    console.log(formData.employment)

    function handleChange(event) {
        const {name, value, type, checked} = event.target
        setFormData(prevFormData => {
            return {
                ...prevFormData,
                [name]: type === "checkbox" ? checked : value
            }
        })
    }

    return (
        <form>
            <input
                type="text"
                placeholder="First Name"
                onChange={handleChange}
                name="firstName"
                value={formData.firstName}
            />
            <input
                type="text"
                placeholder="Last Name"
                onChange={handleChange}
                name="lastName"
                value={formData.lastName}
            />
            <input
                type="email"
                placeholder="Email"
                onChange={handleChange}
                name="email"
                value={formData.email}
            />
            <textarea
                value={formData.comments}
                placeholder="Comments"
                onChange={handleChange}
                name="comments"
            />
            <input
                type="checkbox"
                id="isFriendly"
                checked={formData.isFriendly}
                onChange={handleChange}
                name="isFriendly"
            />
            <label htmlFor="isFriendly">Are you friendly?</label>
            <br />
            <br />

            <fieldset>
                <legend>Current employment status</legend>

                <input
                    type="radio"
                    id="unemployed"
                    name="employment"
                    value="unemployed"
                    checked={formData.employment === "unemployed"}
                    onChange={handleChange}
                />
                <label htmlFor="unemployed">Unemployed</label>
                <br />

                <input
                    type="radio"
                    id="part-time"
                    name="employment"
                    value="part-time"
                    checked={formData.employment === "part-time"}
                    onChange={handleChange}
                />
                <label htmlFor="part-time">Part-time</label>
                <br />

                <input
                    type="radio"
                    id="full-time"
                    name="employment"
                    value="full-time"
                    checked={formData.employment === "full-time"}
                    onChange={handleChange}
                />
                <label htmlFor="full-time">Full-time</label>
                <br />

            </fieldset>
        </form>
    )
}
```

</details>

<details>
  <summary>54. Forms - Select & Options</summary>

Form.js:

```Javascript
import React from "react"

export default function Form() {
    const [formData, setFormData] = React.useState(
        {
            firstName: "",
            lastName: "",
            email: "",
            comments: "",
            isFriendly: true,
            employment: "",
            favColor: ""
        }
    )
    console.log(formData.favColor)

    function handleChange(event) {
        console.log(event)
        const {name, value, type, checked} = event.target
        setFormData(prevFormData => {
            return {
                ...prevFormData,
                [name]: type === "checkbox" ? checked : value
            }
        })
    }

    return (
        <form>
            <input
                type="text"
                placeholder="First Name"
                onChange={handleChange}
                name="firstName"
                value={formData.firstName}
            />
            <input
                type="text"
                placeholder="Last Name"
                onChange={handleChange}
                name="lastName"
                value={formData.lastName}
            />
            <input
                type="email"
                placeholder="Email"
                onChange={handleChange}
                name="email"
                value={formData.email}
            />
            <textarea
                value={formData.comments}
                placeholder="Comments"
                onChange={handleChange}
                name="comments"
            />
            <input
                type="checkbox"
                id="isFriendly"
                checked={formData.isFriendly}
                onChange={handleChange}
                name="isFriendly"
            />
            <label htmlFor="isFriendly">Are you friendly?</label>
            <br />
            <br />

            <fieldset>
                <legend>Current employment status</legend>
                <input
                    type="radio"
                    id="unemployed"
                    name="employment"
                    value="unemployed"
                    checked={formData.employment === "unemployed"}
                    onChange={handleChange}
                />
                <label htmlFor="unemployed">Unemployed</label>
                <br />

                <input
                    type="radio"
                    id="part-time"
                    name="employment"
                    value="part-time"
                    checked={formData.employment === "part-time"}
                    onChange={handleChange}
                />
                <label htmlFor="part-time">Part-time</label>
                <br />

                <input
                    type="radio"
                    id="full-time"
                    name="employment"
                    value="full-time"
                    checked={formData.employment === "full-time"}
                    onChange={handleChange}
                />
                <label htmlFor="full-time">Full-time</label>
                <br />
            </fieldset>
            <br />

            <label htmlFor="favColor">What is your favorite color?</label>
            <br />
            <select
                id="favColor"
                value={formData.favColor}
                onChange={handleChange}
                name="favColor"
            >
                <option value="">-- Choose --</option>
                <option value="red">Red</option>
                <option value="orange">Orange</option>
                <option value="yellow">Yellow</option>
                <option value="green">Green</option>
                <option value="blue">Blue</option>
                <option value="indigo">Indigo</option>
                <option value="violet">Violet</option>
            </select>
        </form>
    )
}
```

</details>

<details>
  <summary>55. Forms - Submiting the Form</summary>

Form.js:

```Javascript
import React from "react"

export default function Form() {
    const [formData, setFormData] = React.useState(
        {
            firstName: "",
            lastName: "",
            email: "",
            comments: "",
            isFriendly: true,
            employment: "",
            favColor: ""
        }
    )

    function handleChange(event) {
        const {name, value, type, checked} = event.target
        setFormData(prevFormData => {
            return {
                ...prevFormData,
                [name]: type === "checkbox" ? checked : value
            }
        })
    }

    function handleSubmit(event) {
        event.preventDefault()
        // submitToApi(formData)
        console.log(formData)
    }

    return (
        <form onSubmit={handleSubmit}>
            <input
                type="text"
                placeholder="First Name"
                onChange={handleChange}
                name="firstName"
                value={formData.firstName}
            />
            <input
                type="text"
                placeholder="Last Name"
                onChange={handleChange}
                name="lastName"
                value={formData.lastName}
            />
            <input
                type="email"
                placeholder="Email"
                onChange={handleChange}
                name="email"
                value={formData.email}
            />
            <textarea
                value={formData.comments}
                placeholder="Comments"
                onChange={handleChange}
                name="comments"
            />
            <input
                type="checkbox"
                id="isFriendly"
                checked={formData.isFriendly}
                onChange={handleChange}
                name="isFriendly"
            />
            <label htmlFor="isFriendly">Are you friendly?</label>
            <br />
            <br />

            <fieldset>
                <legend>Current employment status</legend>
                <input
                    type="radio"
                    id="unemployed"
                    name="employment"
                    value="unemployed"
                    checked={formData.employment === "unemployed"}
                    onChange={handleChange}
                />
                <label htmlFor="unemployed">Unemployed</label>
                <br />

                <input
                    type="radio"
                    id="part-time"
                    name="employment"
                    value="part-time"
                    checked={formData.employment === "part-time"}
                    onChange={handleChange}
                />
                <label htmlFor="part-time">Part-time</label>
                <br />

                <input
                    type="radio"
                    id="full-time"
                    name="employment"
                    value="full-time"
                    checked={formData.employment === "full-time"}
                    onChange={handleChange}
                />
                <label htmlFor="full-time">Full-time</label>
                <br />
            </fieldset>
            <br />

            <label htmlFor="favColor">What is your favorite color?</label>
            <br />
            <select
                id="favColor"
                value={formData.favColor}
                onChange={handleChange}
                name="favColor"
            >
                <option value="red">Red</option>
                <option value="orange">Orange</option>
                <option value="yellow">Yellow</option>
                <option value="green">Green</option>
                <option value="blue">Blue</option>
                <option value="indigo">Indigo</option>
                <option value="violet">Violet</option>
            </select>
            <br />
            <br />
            <button>Submit</button>
        </form>
    )
}
```

</details>

<details>
  <summary>56. Sign up Form</summary>

App.js:

```Javascript
import React from "react"

export default function App() {
    const [formData, setFormData] = React.useState({
        email: "",
        password: "",
        passwordConfirm: "",
        joinedNewsletter: true
    })

    function handleChange(event) {
        const {name, value, type, checked} = event.target
        setFormData(prevFormData => ({
            ...prevFormData,
            [name]: type === "checkbox" ? checked : value
        }))
    }

    function handleSubmit(event) {
        event.preventDefault()
        if(formData.password === formData.passwordConfirm) {
            console.log("Successfully signed up")
        } else {
            console.log("Passwords do not match")
            return
        }

        if(formData.joinedNewsletter) {
            console.log("Thanks for signing up for our newsletter!")
        }
    }

    return (
        <div className="form-container">
            <form className="form" onSubmit={handleSubmit}>
                <input
                    type="email"
                    placeholder="Email address"
                    className="form--input"
                    name="email"
                    onChange={handleChange}
                    value={formData.email}
                />
                <input
                    type="password"
                    placeholder="Password"
                    className="form--input"
                    name="password"
                    onChange={handleChange}
                    value={formData.password}
                />
                <input
                    type="password"
                    placeholder="Confirm password"
                    className="form--input"
                    name="passwordConfirm"
                    onChange={handleChange}
                    value={formData.passwordConfirm}
                />

                <div className="form--marketing">
                    <input
                        id="okayToEmail"
                        type="checkbox"
                        name="joinedNewsletter"
                        onChange={handleChange}
                        checked={formData.joinedNewsletter}
                    />
                    <label htmlFor="okayToEmail">I want to join the newsletter</label>
                </div>
                <button
                    className="form--submit"
                >
                    Sign up
                </button>
            </form>
        </div>
    )
}
```

</details>

<details>
  <summary>57. Meme Generator</summary>

components/Meme.js:

```Javascript
import React from "react"
import memesData from "../memesData.js"

export default function Meme() {

    const [meme, setMeme] = React.useState({
        topText: "",
        bottomText: "",
        randomImage: "http://i.imgflip.com/1bij.jpg"
    })
    const [allMemeImages, setAllMemeImages] = React.useState(memesData)


    function getMemeImage() {
        const memesArray = allMemeImages.data.memes
        const randomNumber = Math.floor(Math.random() * memesArray.length)
        const url = memesArray[randomNumber].url
        setMeme(prevMeme => ({
            ...prevMeme,
            randomImage: url
        }))

    }

    function handleChange(event) {
        const {name, value} = event.target
        setMeme(prevMeme => ({
            ...prevMeme,
            [name]: value
        }))
    }

    return (
        <main>
            <div className="form">
                <input
                    type="text"
                    placeholder="Top text"
                    className="form--input"
                    name="topText"
                    value={meme.topText}
                    onChange={handleChange}
                />
                <input
                    type="text"
                    placeholder="Bottom text"
                    className="form--input"
                    name="bottomText"
                    value={meme.bottomText}
                    onChange={handleChange}
                />
                <button
                    className="form--button"
                    onClick={getMemeImage}
                >
                    Get a new meme image 🖼
                </button>
            </div>
            <div className="meme">
                <img src={meme.randomImage} className="meme--image" />
                <h2 className="meme--text top">{meme.topText}</h2>
                <h2 className="meme--text bottom">{meme.bottomText}</h2>
            </div>
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
    font-family: "Karla", sans-serif;
    margin: 0;
}

main {
    padding: 36px;
}

.header {
    display: flex;
    align-items: center;
    height: 65px;
    background: linear-gradient(90deg, #672280 1.18%, #A626D3 100%);
    color: white;
    padding: 20px;
}

.header--image {
    height: 100%;
    margin-right: 6px;
}

.header--title {
    font-size: 1.25rem;
    margin-right: auto;
}

.header--project {
    font-size: 0.75rem;
    font-weight: 500;
}

.form {
    display: grid;
    grid-template: 40px 40px / 1fr 1fr;
    gap: 17px;
    margin-bottom: 17px;
}

.form--input {
    font-family: "Karla", sans-serif;
    border-radius: 5px;
    border: 1px solid #D5D4D8;
    text-indent: 5px;
}

.form--button {
    grid-column: 1 / -1;
    font-family: "Karla", sans-serif;
    border-radius: 5px;
    background: linear-gradient(90.41deg, #711F8D 1.14%, #A818DA 100%);
    color: white;
    border: none;
    cursor: pointer;
}

.meme {
    position: relative;
}

.meme--image {
    max-width: 100%;
    border-radius: 3px;
}

.meme--text {
    position: absolute;
    width: 80%;
    text-align: center;
    left: 50%;
    transform: translateX(-50%);
    margin: 15px 0;
    padding: 0 5px;
    font-family: impact, sans-serif;
    font-size: 2em;
    text-transform: uppercase;
    color: white;
    letter-spacing: 1px;
    text-shadow:
        2px 2px 0 #000,
        -2px -2px 0 #000,
        2px -2px 0 #000,
        -2px 2px 0 #000,
        0 2px 0 #000,
        2px 0 0 #000,
        0 -2px 0 #000,
        -2px 0 0 #000,
        2px 2px 5px #000;
}

.bottom {
    bottom: 0;
}

.top {
    top: 0;
}
```

</details>

<details>
  <summary>58. Making API Calls</summary>

App.js:

```Javascript
import React from "react"

export default function App() {
    const [starWarsData, setStarWarsData] = React.useState({})

    console.log("Component rendered")

    fetch("https://swapi.dev/api/people/1")
        .then(res => res.json())
        .then(data => console.log(data))

    return (
        <div>
            <pre>{JSON.stringify(starWarsData, null, 2)}</pre>
        </div>
    )
}
```

</details>

<details>
  <summary>59. React UseEffect</summary>

App.js:

```Javascript
import React from "react"

export default function App() {
    const [starWarsData, setStarWarsData] = React.useState({})
    const [count, setCount] = React.useState(0)

    console.log("Component rendered")

    React.useEffect(() => {
        console.log("Effect function ran")
    }, [count])

    return (
        <div>
            <pre>{JSON.stringify(starWarsData, null, 2)}</pre>
            <h2>The count is {count}</h2>
            <button onClick={() => setCount(prevCount => prevCount + 1)}>Add</button>
        </div>
    )
}

```

```Javascript
import React from "react"

export default function App() {
    const [starWarsData, setStarWarsData] = React.useState({})
    const [count, setCount] = React.useState(0)

    React.useEffect(function() {
        console.log("Effect ran")
        fetch("https://swapi.dev/api/people/1")
            .then(res => res.json())
            .then(data => setStarWarsData(data))
    }, [])

    return (
        <div>
            <pre>{JSON.stringify(starWarsData, null, 2)}</pre>
            <h2>The count is {count}</h2>
            <button onClick={() => setCount(prevCount => prevCount + 1)}>Add</button>
        </div>
    )
}
```

```Javascript
import React from "react"

export default function App() {
    const [starWarsData, setStarWarsData] = React.useState({})
    const [count, setCount] = React.useState(1)

    React.useEffect(function() {
        console.log("Effect ran")
        fetch(`https://swapi.dev/api/people/${count}`)
            .then(res => res.json())
            .then(data => setStarWarsData(data))
    }, [count])

    return (
        <div>
            <h2>The count is {count}</h2>
            <button onClick={() => setCount(prevCount => prevCount + 1)}>Get Next Character</button>
            <pre>{JSON.stringify(starWarsData, null, 2)}</pre>
        </div>
    )
}
```

components/Meme.js:

```Javascript
import React from "react"

export default function Meme() {
    const [meme, setMeme] = React.useState({
        topText: "",
        bottomText: "",
        randomImage: "http://i.imgflip.com/1bij.jpg"
    })
    const [allMemes, setAllMemes] = React.useState([])

    React.useEffect(() => {
        fetch("https://api.imgflip.com/get_memes")
            .then(res => res.json())
            .then(data => setAllMemes(data.data.memes))
    }, [])

    function getMemeImage() {
        const randomNumber = Math.floor(Math.random() * allMemes.length)
        const url = allMemes[randomNumber].url
        setMeme(prevMeme => ({
            ...prevMeme,
            randomImage: url
        }))

    }

    function handleChange(event) {
        const {name, value} = event.target
        setMeme(prevMeme => ({
            ...prevMeme,
            [name]: value
        }))
    }

    return (
        <main>
            <div className="form">
                <input
                    type="text"
                    placeholder="Top text"
                    className="form--input"
                    name="topText"
                    value={meme.topText}
                    onChange={handleChange}
                />
                <input
                    type="text"
                    placeholder="Bottom text"
                    className="form--input"
                    name="bottomText"
                    value={meme.bottomText}
                    onChange={handleChange}
                />
                <button
                    className="form--button"
                    onClick={getMemeImage}
                >
                    Get a new meme image 🖼
                </button>
            </div>
            <div className="meme">
                <img src={meme.randomImage} className="meme--image" />
                <h2 className="meme--text top">{meme.topText}</h2>
                <h2 className="meme--text bottom">{meme.bottomText}</h2>
            </div>
        </main>
    )
}
```

</details>

<details>
  <summary>60. Window Tracker Demo</summary>

WindowTracker.js:

```Javascript
import React from "react"

export default function WindowTracker() {

    const [windowWidth, setWindowWidth] = React.useState(window.innerWidth)

    React.useEffect(() => {
        window.addEventListener("resize", function() {
            setWindowWidth(window.innerWidth)
        })
    }, [])

    return (
        <h1>Window width: {windowWidth}</h1>
    )
}
```

```Javascript
import React from "react"

export default function WindowTracker() {

    const [windowWidth, setWindowWidth] = React.useState(window.innerWidth)

    React.useEffect(() => {
        function watchWidth() {
            console.log("Setting up...")
            setWindowWidth(window.innerWidth)
        }

        window.addEventListener("resize", watchWidth)

        return function() {
            console.log("Cleaning up...")
            window.removeEventListener("resize", watchWidth)
        }
    }, [])

    return (
        <h1>Window width: {windowWidth}</h1>
    )
}
```

```css
/*
    useEffect takes a function as its parameter. If that function
    returns something, it needs to be a cleanup function. Otherwise,
    it should return nothing. If we make it an async function, it
    automatically retuns a promise instead of a function or nothing.
    Therefore, if you want to use async operations inside of useEffect,
    you need to define the function separately inside of the callback
    function, as seen below:
    */
```

```Javascript
React.useEffect(() => {
        async function getMemes() {
            const res = await fetch("https://api.imgflip.com/get_memes")
            const data = await res.json()
            setAllMemes(data.data.memes)
        }
        getMemes()
    }, [])
```

</details>

### [4-NOTES & TENZIES GAME](#)

<details>
  <summary>61. Dark & Light Modes</summary>

index.js:

```Javascript
import React from "react"
import ReactDOM from "react-dom"
import App from "./App"

ReactDOM.render(<App />, document.getElementById("root"))
```

App.js:

```Javascript
import React from "react"
import Navbar from "./components/Navbar"
import Main from "./components/Main"

export default function App() {
    const [darkMode, setDarkMode] = React.useState(true)

    function toggleDarkMode() {
        setDarkMode(prevMode => !prevMode)
    }

    return (
        <div className="container">
            <Navbar
                darkMode={darkMode}
                toggleDarkMode={toggleDarkMode}
            />
            <Main darkMode={darkMode} />
        </div>
    )
}
```

components/Navbar.js:

```Javascript
import React from "react"

export default function Navbar(props) {
    return (
         <nav
            className={props.darkMode ? "dark": ""}
        >
            <img
                className="nav--logo_icon"
                src="./images/react-icon-small.png"
            />
            <h3 className="nav--logo_text">ReactFacts</h3>

            <div
                className="toggler"
            >
                <p className="toggler--light">Light</p>
                <div
                    className="toggler--slider"
                    onClick={props.toggleDarkMode}
                >
                    <div className="toggler--slider--circle"></div>
                </div>
                <p className="toggler--dark">Dark</p>
            </div>
        </nav>
    )
}
```

components/Main.js:

```Javascript
import React from "react"

export default function Main(props) {
    return (
        <main className={props.darkMode ? "dark" : ""}>
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

h1, h2, h3, h4, h5, h6, p {
    margin: 0;
}

body {
    margin: 0;
}

.container {
    display: flex;
    flex-direction: column;
    height: 100vh;
}

/* NAV styles */

nav {
    display: flex;
    align-items: center;
    background-color: #ffffff;
    padding: 30px 25px;
    height: 60px;
    box-shadow: 0px 1px 4px rgba(0, 0, 0, 0.25);
    z-index: 1;
}

nav.dark {
    background-color: #21222A;
}

.nav--logo_icon {
    width: 30px;
    margin-right: 10px;
}

.nav--logo_text {
    color: #61DAFB;
    margin-right: auto;
}

.nav--title {
    color: #DEEBF8;
}

.toggler {
    display: flex;
    align-items: center;
}

.toggler p {
    font-size: 0.625rem;
    font-weight: 600;
}

.toggler--slider {
    width: 25px;
    height: 13px;
    background-color: #2B283A;
    border-radius: 2rem;
    margin-inline: 7px;
    cursor: pointer;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    border: 1px solid black;
    box-sizing: content-box;
}

nav.dark .toggler--slider {
    border-color: white;
    background-color: #F5F5F5;
}

.toggler--slider--circle {
    height: 13px;
    width: 13px;
    background-color: white;
    border-radius: 50%;
}

nav.dark .toggler--slider--circle {
    background-color: black;
}

.toggler--light {
    color: #2B283A;
}

nav.dark .toggler--light {
    color: #918E9B;
}

.toggler--dark {
    color: #D5D4D8;
}

nav.dark .toggler-dark {
    color: #FFFFFF;
}

nav.dark .toggler--slider {
    justify-content: flex-end;
}

/* MAIN styles */
main {
    padding: 57px 27px;
    background-image: url("./images/react-icon-light.png");
    background-repeat: no-repeat;
    background-position: right center;
    flex: 1 1 auto;
    background-color: white;
    color: #2B283A;
}

main.dark {
    background-image: url("./images/react-icon-dark.png");
    background-color: #282D35;
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

.main--facts > li::marker {
    font-size: 1.4rem;
    color: #61DAFB;
}
```

</details>

<details>
  <summary>62. Local Storage</summary>

Window.localStorage:

```Javascript
/*
The localStorage read-only property of the window interface
allows you to access a Storage object for the Document's origin;
the stored data is saved across browser sessions.

localStorage is similar to sessionStorage, except that while
localStorage data has no expiration time, sessionStorage data
gets cleared when the page session ends — that is, when the page is closed.
(localStorage data for a document loaded in a "private browsing" or "incognito"
session is cleared when the last "private" tab is closed.)
*/
```

The syntax for adding data into the localStorage is as follows:

```Javascript
localStorage.setItem('myCat', 'Tom');
```

The syntax for reading the localStorage item is as follows:

```Javascript
const cat = localStorage.getItem('myCat');
```

The syntax for removing the localStorage item is as follows:

```Javascript
localStorage.removeItem('myCat');
```

The syntax for removing all the localStorage items is as follows:

```Javascript
localStorage.clear();
```

Use JSON.stringify() to turn the array into a string to save in localStorage

```Javascript
localStorage.setItem('note', JSON.stringify(notes))
```

Use JSON.parse() to turn the stringified array back into a real JS array

```Javascript
const [notes, setNotes] = React.useState(JSON.parse(localStorage.getItem('note')) || [])
```

</details>

<details>
  <summary>63. Sync Notes App with Local Storage</summary>

App.js:

```Javascript
import React from "react"
import Sidebar from "./components/Sidebar"
import Editor from "./components/Editor"
import { data } from "./data"
import Split from "react-split"
import {nanoid} from "nanoid"

export default function App() {

    const [notes, setNotes] = React.useState(
        JSON.parse(localStorage.getItem("notes")) || []
    )
    const [currentNoteId, setCurrentNoteId] = React.useState(
        (notes[0] && notes[0].id) || ""
    )

    React.useEffect(() => {
        localStorage.setItem("notes", JSON.stringify(notes))
    }, [notes])

    function createNewNote() {
        const newNote = {
            id: nanoid(),
            body: "# Type your markdown note's title here"
        }
        setNotes(prevNotes => [newNote, ...prevNotes])
        setCurrentNoteId(newNote.id)
    }

    function updateNote(text) {
        setNotes(oldNotes => oldNotes.map(oldNote => {
            return oldNote.id === currentNoteId
                ? { ...oldNote, body: text }
                : oldNote
        }))
    }

    function findCurrentNote() {
        return notes.find(note => {
            return note.id === currentNoteId
        }) || notes[0]
    }

    return (
        <main>
        {
            notes.length > 0
            ?
            <Split
                sizes={[30, 70]}
                direction="horizontal"
                className="split"
            >
                <Sidebar
                    notes={notes}
                    currentNote={findCurrentNote()}
                    setCurrentNoteId={setCurrentNoteId}
                    newNote={createNewNote}
                />
                {
                    currentNoteId &&
                    notes.length > 0 &&
                    <Editor
                        currentNote={findCurrentNote()}
                        updateNote={updateNote}
                    />
                }
            </Split>
            :
            <div className="no-notes">
                <h1>You have no notes</h1>
                <button
                    className="first-note"
                    onClick={createNewNote}
                >
                    Create one now
                </button>
            </div>

        }
        </main>
    )
}
```

</details>

<details>
  <summary>64. Lazy State Initialization</summary>

App.js:

```Javascript
const [notes, setNotes] = React.useState(
        () => JSON.parse(localStorage.getItem("notes")) || []
    )
```

</details>

<details>
  <summary>65. Note Summary Title</summary>

Sidebar.js:

```Javascript
import React from "react"

export default function Sidebar(props) {
    const noteElements = props.notes.map((note, index) => (
        <div key={note.id}>
            <div
                className={`title ${
                    note.id === props.currentNote.id ? "selected-note" : ""
                }`}
                onClick={() => props.setCurrentNoteId(note.id)}
            >
                <h4 className="text-snippet">{note.body.split("\n")[0]}</h4>
            </div>
        </div>
    ))

    return (
        <section className="pane sidebar">
            <div className="sidebar--header">
                <h3>Notes</h3>
                <button className="new-note" onClick={props.newNote}>+</button>
            </div>
            {noteElements}
        </section>
    )
}
```

</details>

<details>
  <summary>66. Bump Recent Note to Top</summary>

App.js:

```Javascript
 function updateNote(text) {
        // Put the most recently-modified note at the top
        setNotes(oldNotes => {
            const newArray = []
            for(let i = 0; i < oldNotes.length; i++) {
                const oldNote = oldNotes[i]
                if(oldNote.id === currentNoteId) {
                    newArray.unshift({ ...oldNote, body: text })
                } else {
                    newArray.push(oldNote)
                }
            }
            return newArray
        })
    }
```

```Javascript
 function updateNote(text) {
        // Try to rearrange the most recently-modified
        // not to be at the top
        setNotes(oldNotes => {
            const content = findCurrentNote()
            const newArray = oldNotes.filter((note)=> note !== content)
            newArray.unshift({ ...content, body: text })
            return newArray
        })
    }
```

</details>

<details>
  <summary>67. Delete Note</summary>

App.js:

```Javascript
import React from "react"
import Sidebar from "./components/Sidebar"
import Editor from "./components/Editor"
import { data } from "./data"
import Split from "react-split"
import {nanoid} from "nanoid"

export default function App() {
    const [notes, setNotes] = React.useState(
        () => JSON.parse(localStorage.getItem("notes")) || []
    )
    const [currentNoteId, setCurrentNoteId] = React.useState(
        (notes[0] && notes[0].id) || ""
    )

    React.useEffect(() => {
        localStorage.setItem("notes", JSON.stringify(notes))
    }, [notes])

    function createNewNote() {
        const newNote = {
            id: nanoid(),
            body: "# Type your markdown note's title here"
        }
        setNotes(prevNotes => [newNote, ...prevNotes])
        setCurrentNoteId(newNote.id)
    }

    function updateNote(text) {
        // Put the most recently-modified note at the top
        setNotes(oldNotes => {
            const newArray = []
            for(let i = 0; i < oldNotes.length; i++) {
                const oldNote = oldNotes[i]
                if(oldNote.id === currentNoteId) {
                    newArray.unshift({ ...oldNote, body: text })
                } else {
                    newArray.push(oldNote)
                }
            }
            return newArray
        })
    }

    function deleteNote(event, noteId) {
        event.stopPropagation()
        setNotes(oldNotes => oldNotes.filter(note => note.id !== noteId))
    }

    function findCurrentNote() {
        return notes.find(note => {
            return note.id === currentNoteId
        }) || notes[0]
    }

    return (
        <main>
        {
            notes.length > 0
            ?
            <Split
                sizes={[30, 70]}
                direction="horizontal"
                className="split"
            >
                <Sidebar
                    notes={notes}
                    currentNote={findCurrentNote()}
                    setCurrentNoteId={setCurrentNoteId}
                    newNote={createNewNote}
                    deleteNote={deleteNote}
                />
                {
                    currentNoteId &&
                    notes.length > 0 &&
                    <Editor
                        currentNote={findCurrentNote()}
                        updateNote={updateNote}
                    />
                }
            </Split>
            :
            <div className="no-notes">
                <h1>You have no notes</h1>
                <button
                    className="first-note"
                    onClick={createNewNote}
                >
                    Create one now
                </button>
            </div>

        }
        </main>
    )
}
```

Sidebar.js:

```Javascript
import React from "react"

export default function Sidebar(props) {
    const noteElements = props.notes.map((note, index) => (
        <div key={note.id}>
            <div

                className={`title ${
                    note.id === props.currentNote.id ? "selected-note" : ""
                }`}
                onClick={() => props.setCurrentNoteId(note.id)}
            >
                <h4 className="text-snippet">{note.body.split("\n")[0]}</h4>
                <button
                    className="delete-btn"
                    onClick={(event) => props.deleteNote(event, note.id)}
                >
                    <i className="gg-trash trash-icon"></i>
                </button>
            </div>
        </div>
    ))

    return (
        <section className="pane sidebar">
            <div className="sidebar--header">
                <h3>Notes</h3>
                <button className="new-note" onClick={props.newNote}>+</button>
            </div>
            {noteElements}
        </section>
    )
}
```

</details>

<details>
  <summary>68. Tenzies Setup</summary>

index.js:

```Javascript
import React from "react"
import ReactDOM from "react-dom"
import App from "./App"

ReactDOM.render(<App />, document.getElementById("root"))
```

App.js:

```Javascript
import React from "react"

export default function App() {
    return (
        <main></main>
    )
}
```

style.css:

```Javascript
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    background-color: #0B2434;
    padding: 20px;
}

main {
    background-color: #F5F5F5;
    height: 400px;
    max-width: 800px;
    border-radius: 5px;
}
```

</details>

<details>
  <summary>69. Die Components</summary>

App.js:

```Javascript
import React from "react"
import Die from "./Die"

export default function App() {
    return (
        <main>
            <div className="dice-container">
                <Die value="1" />
                <Die value="2" />
                <Die value="3" />
                <Die value="4" />
                <Die value="5" />
                <Die value="6" />
                <Die value="1" />
                <Die value="1" />
                <Die value="1" />
                <Die value="1" />
            </div>
        </main>
    )
}
```

Die.js:

```Javascript
import React from "react"

export default function Die(props) {
    return (
        <div className="die-face">
            <h2 className="die-num">{props.value}</h2>
        </div>
    )
}
```

style.css:

```Javascript
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    background-color: #0B2434;
    padding: 20px;
}

main {
    background-color: #F5F5F5;
    height: 400px;
    max-width: 800px;
    border-radius: 5px;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.dice-container {
    display: grid;
    grid-template: auto auto / repeat(5, 1fr);
    gap: 20px;
}

.die-face {
    height: 50px;
    width: 50px;
    box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.15);
    border-radius: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    background-color: white;
}

.die-num {
    font-size: 2rem;
}
```

</details>

<details>
  <summary>70. Generate Arrays of 10 random Numbers</summary>

App.js:

```Javascript
import React from "react"
import Die from "./Die"

export default function App() {
    function allNewDice() {
        const newDice = []
        for (let i = 0; i < 10; i++) {
            newDice.push(Math.ceil(Math.random() * 6))
        }
        return newDice
    }
    console.log(allNewDice())

    return (
        <main>
            <div className="dice-container">
                <Die value="1" />
                <Die value="2" />
                <Die value="3" />
                <Die value="4" />
                <Die value="5" />
                <Die value="6" />
                <Die value="1" />
                <Die value="1" />
                <Die value="1" />
                <Die value="1" />
            </div>
        </main>
    )
}
```

</details>

<details>
  <summary>71. Map Array to Die Components</summary>

App.js:

```Javascript
import React from "react"
import Die from "./Die"

export default function App() {
    const [dice, setDice] = React.useState(allNewDice())

    function allNewDice() {
        const newDice = []
        for (let i = 0; i < 10; i++) {
            newDice.push(Math.ceil(Math.random() * 6))
        }
        return newDice
    }

    const diceElements = dice.map(die => <Die value={die} />)

    return (
        <main>
            <div className="dice-container">
                {diceElements}
            </div>
        </main>
    )
}
```

Die.js:

```Javascript
import React from "react"

export default function Die(props) {
    return (
        <div className="die-face">
            <h2 className="die-num">{props.value}</h2>
        </div>
    )
}
```

</details>

<details>
  <summary>72. Roll Dice Button</summary>

App.js:

```Javascript
import React from "react"
import Die from "./Die"

export default function App() {

    const [dice, setDice] = React.useState(allNewDice())

    function allNewDice() {
        const newDice = []
        for (let i = 0; i < 10; i++) {
            newDice.push(Math.ceil(Math.random() * 6))
        }
        return newDice
    }

    function rollDice() {
        setDice(allNewDice())
    }

    const diceElements = dice.map(die => <Die value={die} />)

    return (
        <main>
            <div className="dice-container">
                {diceElements}
            </div>
            <button className="roll-dice" onClick={rollDice}>Roll</button>
        </main>
    )
}
```

Die.js:

```Javascript
import React from "react"

export default function Die(props) {
    return (
        <div className="die-face">
            <h2 className="die-num">{props.value}</h2>
        </div>
    )
}
```

style.css:

```Javascript
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    background-color: #0B2434;
    padding: 20px;
    font-family: 'Karla', sans-serif;
}

main {
    background-color: #F5F5F5;
    height: 400px;
    max-width: 800px;
    border-radius: 5px;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
}

.dice-container {
    display: grid;
    grid-template: auto auto / repeat(5, 1fr);
    gap: 20px;
}

.die-face {
    height: 50px;
    width: 50px;
    box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.15);
    border-radius: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
    background-color: white;
}

.die-num {
    font-size: 2rem;
}

.roll-dice {
    height: 50px;
    width: 100px;
    border: none;
    border-radius: 6px;
    background-color: #5035FF;
    color: white;
    font-size: 1.2rem;
    font-family: 'Karla', sans-serif;
    cursor: pointer;
}

.roll-dice:focus {
    outline: none;
}

.roll-dice:active {
    box-shadow: inset 5px 5px 10px -3px rgba(0, 0, 0, 0.7);
}

```

</details>

<details>
  <summary>73. Change Dice to Objects</summary>

App.js:

```Javascript
import React from "react"
import Die from "./Die"
import {nanoid} from "nanoid"

export default function App() {

    const [dice, setDice] = React.useState(allNewDice())

    function allNewDice() {
        const newDice = []
        for (let i = 0; i < 10; i++) {
            newDice.push({
                value: Math.ceil(Math.random() * 6),
                isHeld: false,
                id: nanoid()
            })
        }
        return newDice
    }

    function rollDice() {
        setDice(allNewDice())
    }

    const diceElements = dice.map(die => (
        <Die key={die.id} value={die.value} />
    ))

    return (
        <main>
            <div className="dice-container">
                {diceElements}
            </div>
            <button className="roll-dice" onClick={rollDice}>Roll</button>
        </main>
    )
}

```

</details>

<details>
  <summary>74. Styling held Dice</summary>

Die.js:

```Javascript
import React from "react"

export default function Die(props) {
    const styles = {
        backgroundColor: props.isHeld ? "#59E391" : "white"
    }
    return (
        <div className="die-face" style={styles}>
            <h2 className="die-num">{props.value}</h2>
        </div>
    )
}
```

App.js:

```Javascript
import React from "react"
import Die from "./Die"
import {nanoid} from "nanoid"

export default function App() {

    const [dice, setDice] = React.useState(allNewDice())

    function allNewDice() {
        const newDice = []
        for (let i = 0; i < 10; i++) {
            newDice.push({
                value: Math.ceil(Math.random() * 6),
                isHeld: false,
                id: nanoid()
            })
        }
        return newDice
    }

    function rollDice() {
        setDice(allNewDice())
    }

    const diceElements = dice.map(die => (
        <Die key={die.id} value={die.value} isHeld={die.isHeld} />
    ))

    return (
        <main>
            <div className="dice-container">
                {diceElements}
            </div>
            <button className="roll-dice" onClick={rollDice}>Roll</button>
        </main>
    )UKA
}
```

</details>

<details>
  <summary>75. Hold Dice</summary>

App.js:

```Javascript
import React from "react"
import Die from "./Die"
import {nanoid} from "nanoid"

export default function App() {

    const [dice, setDice] = React.useState(allNewDice())

    function allNewDice() {
        const newDice = []
        for (let i = 0; i < 10; i++) {
            newDice.push({
                value: Math.ceil(Math.random() * 6),
                isHeld: false,
                id: nanoid()
            })
        }
        return newDice
    }

    function rollDice() {
        setDice(allNewDice())
    }

    function holdDice(id) {
        console.log(id)
    }

    const diceElements = dice.map(die => (
        <Die key={die.id} value={die.value} isHeld={die.isHeld} holdDice={() => holdDice(die.id)} />
    ))

    return (
        <main>
            <div className="dice-container">
                {diceElements}
            </div>
            <button className="roll-dice" onClick={rollDice}>Roll</button>
        </main>
    )
}
```

```Javascript
import React from "react"

export default function Die(props) {
    const styles = {
        backgroundColor: props.isHeld ? "#59E391" : "white"
    }
    return (
        <div
            className="die-face"
            style={styles}
            onClick={props.holdDice}
        >
            <h2 className="die-num">{props.value}</h2>
        </div>
    )
}
```

</details>

<details>
  <summary>76. Hold Dice 2</summary>

App.js:

```Javascript
import React from "react"
import Die from "./Die"
import {nanoid} from "nanoid"

export default function App() {

    const [dice, setDice] = React.useState(allNewDice())

    function generateNewDie() {
        return {
            value: Math.ceil(Math.random() * 6),
            isHeld: false,
            id: nanoid()
        }
    }

    function allNewDice() {
        const newDice = []
        for (let i = 0; i < 10; i++) {
            newDice.push(generateNewDie())
        }
        return newDice
    }

    function rollDice() {
        setDice(oldDice => oldDice.map(die => {
            return die.isHeld ?
                die :
                generateNewDie()
        }))
    }

    function holdDice(id) {
        setDice(oldDice => oldDice.map(die => {
            return die.id === id ?
                {...die, isHeld: !die.isHeld} :
                die
        }))
    }

    const diceElements = dice.map(die => (
        <Die
            key={die.id}
            value={die.value}
            isHeld={die.isHeld}
            holdDice={() => holdDice(die.id)}
        />
    ))

    return (
        <main>
            <h1 className="title">Tenzies</h1>
            <p className="instructions">Roll until all dice are the same. Click each die to freeze it at its current value between rolls.</p>
            <div className="dice-container">
                {diceElements}
            </div>
            <button className="roll-dice" onClick={rollDice}>Roll</button>
        </main>
    )
}
```

Die.js:

```Javascript
import React from "react"

export default function Die(props) {
    const styles = {
        backgroundColor: props.isHeld ? "#59E391" : "white"
    }
    return (
        <div
            className="die-face"
            style={styles}
            onClick={props.holdDice}
        >
            <h2 className="die-num">{props.value}</h2>
        </div>
    )
}

```

style.css:

```Javascript
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    background-color: #0B2434;
    padding: 20px;
    font-family: 'Karla', sans-serif;
}

main {
    background-color: #F5F5F5;
    height: 400px;
    max-width: 800px;
    border-radius: 5px;
    padding: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
}

.title {
    font-size: 40px;
    margin: 0;
}

.instructions {
    font-family: 'Inter', sans-serif;
    font-weight: 400;
    margin-top: 0;
    text-align: center;
}

.dice-container {
    display: grid;
    grid-template: auto auto / repeat(5, 1fr);
    gap: 20px;
    margin-bottom: 40px;
}

.die-face {
    height: 50px;
    width: 50px;
    box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.15);
    border-radius: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer;
}

.die-num {
    font-size: 2rem;
}

.roll-dice {
    height: 50px;
    width: 100px;
    border: none;
    border-radius: 6px;
    background-color: #5035FF;
    color: white;
    font-size: 1.2rem;
    font-family: 'Karla', sans-serif;
    cursor: pointer;
}

.roll-dice:focus {
    outline: none;
}

.roll-dice:active {
    box-shadow: inset 5px 5px 10px -3px rgba(0, 0, 0, 0.7);
}
```

</details>

<details>
  <summary>77. Every function</summary>

App.js:

```Javascript
import React from "react"
import Die from "./Die"
import {nanoid} from "nanoid"

export default function App() {

    const [dice, setDice] = React.useState(allNewDice())
    const [tenzies, setTenzies] = React.useState(false)

    React.useEffect(() => {
        const allHeld = dice.every(die => die.isHeld)
        const firstValue = dice[0].value
        const allSameValue = dice.every(die => die.value === firstValue)
        if (allHeld && allSameValue) {
            setTenzies(true)
            console.log("You won!")
        }
    }, [dice])

    function generateNewDie() {
        return {
            value: Math.ceil(Math.random() * 6),
            isHeld: false,
            id: nanoid()
        }
    }

    function allNewDice() {
        const newDice = []
        for (let i = 0; i < 10; i++) {
            newDice.push(generateNewDie())
        }
        return newDice
    }


    function rollDice() {
        setDice(oldDice => oldDice.map(die => {
            return die.isHeld ?
                die :
                generateNewDie()
        }))
    }

    function holdDice(id) {
        setDice(oldDice => oldDice.map(die => {
            return die.id === id ?
                {...die, isHeld: !die.isHeld} :
                die
        }))
    }

    const diceElements = dice.map(die => (
        <Die
            key={die.id}
            value={die.value}
            isHeld={die.isHeld}
            holdDice={() => holdDice(die.id)}
        />
    ))

    return (
        <main>
            <h1 className="title">Tenzies</h1>
            <p className="instructions">Roll until all dice are the same. Click each die to freeze it at its current value between rolls.</p>
            <div className="dice-container">
                {diceElements}
            </div>
            <button className="roll-dice" onClick={rollDice}>Roll</button>
        </main>
    )
}

```

</details>

<details>
  <summary>78. Confetti - You Won!</summary>

App.js:

```Javascript
import React from "react"
import Die from "./Die"
import {nanoid} from "nanoid"
import Confetti from "react-confetti"

export default function App() {

    const [dice, setDice] = React.useState(allNewDice())
    const [tenzies, setTenzies] = React.useState(false)

    React.useEffect(() => {
        const allHeld = dice.every(die => die.isHeld)
        const firstValue = dice[0].value
        const allSameValue = dice.every(die => die.value === firstValue)
        if (allHeld && allSameValue) {
            setTenzies(true)
            console.log("You won!")
        }
    }, [dice])

    function generateNewDie() {
        return {
            value: Math.ceil(Math.random() * 6),
            isHeld: false,
            id: nanoid()
        }
    }

    function allNewDice() {
        const newDice = []
        for (let i = 0; i < 10; i++) {
            newDice.push(generateNewDie())
        }
        return newDice
    }


    function rollDice() {
        setDice(oldDice => oldDice.map(die => {
            return die.isHeld ?
                die :
                generateNewDie()
        }))
    }

    function holdDice(id) {
        setDice(oldDice => oldDice.map(die => {
            return die.id === id ?
                {...die, isHeld: !die.isHeld} :
                die
        }))
    }

    const diceElements = dice.map(die => (
        <Die
            key={die.id}
            value={die.value}
            isHeld={die.isHeld}
            holdDice={() => holdDice(die.id)}
        />
    ))

    return (
        <main>
            {tenzies && <Confetti />}
            <h1 className="title">Tenzies</h1>
            <p className="instructions">Roll until all dice are the same. Click each die to freeze it at its current value between rolls.</p>
            <div className="dice-container">
                {diceElements}
            </div>
            <button
                className="roll-dice"
                onClick={rollDice}
            >
                {tenzies ? "New Game" : "Roll"}
            </button>
        </main>
    )
}

```

</details>

<details>
  <summary>79. Tenzies: New Game</summary>

App.js:

```Javascript
import React from "react"
import Die from "./Die"
import {nanoid} from "nanoid"
import Confetti from "react-confetti"

export default function App() {

    const [dice, setDice] = React.useState(allNewDice())
    const [tenzies, setTenzies] = React.useState(false)

    React.useEffect(() => {
        const allHeld = dice.every(die => die.isHeld)
        const firstValue = dice[0].value
        const allSameValue = dice.every(die => die.value === firstValue)
        if (allHeld && allSameValue) {
            setTenzies(true)
        }
    }, [dice])

    function generateNewDie() {
        return {
            value: Math.ceil(Math.random() * 6),
            isHeld: false,
            id: nanoid()
        }
    }

    function allNewDice() {
        const newDice = []
        for (let i = 0; i < 10; i++) {
            newDice.push(generateNewDie())
        }
        return newDice
    }

    function rollDice() {
        if(!tenzies) {
            setDice(oldDice => oldDice.map(die => {
                return die.isHeld ?
                    die :
                    generateNewDie()
            }))
        } else {
            setTenzies(false)
            setDice(allNewDice())
        }
    }

    function holdDice(id) {
        setDice(oldDice => oldDice.map(die => {
            return die.id === id ?
                {...die, isHeld: !die.isHeld} :
                die
        }))
    }

    const diceElements = dice.map(die => (
        <Die
            key={die.id}
            value={die.value}
            isHeld={die.isHeld}
            holdDice={() => holdDice(die.id)}
        />
    ))

    return (
        <main>
            {tenzies && <Confetti />}
            <h1 className="title">Tenzies</h1>
            <p className="instructions">Roll until all dice are the same.
            Click each die to freeze it at its current value between rolls.</p>
            <div className="dice-container">
                {diceElements}
            </div>
            <button
                className="roll-dice"
                onClick={rollDice}
            >
                {tenzies ? "New Game" : "Roll"}
            </button>
        </main>
    )
}

```

</details>

### [5-](#)

<details>
  <summary>80. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>


<details>
  <summary>81. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>


<details>
  <summary>82. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>


<details>
  <summary>83. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>


<details>
  <summary>84. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>


<details>
  <summary>85. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>


<details>
  <summary>86. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>


<details>
  <summary>87. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>


<details>
  <summary>88. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>


<details>
  <summary>89. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>


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
