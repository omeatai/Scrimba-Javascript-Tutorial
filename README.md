# Javascript-Tutorial
Javascript Tutorial by Ifeanyi Omeata

## Tutorial

---

### [1-INTRO TO APIS](#)

<details>
  <summary>1. How to use Fetch with json</summary>

```Javascript
fetch('http://example.com/movies.json')
  .then((response) => response.json())
  .then((data) => console.log(data));
```

```Javascript
var myRequest = new Request('products.json');//GET
var myRequest = new Request('products.json', {method: "post"});//POST

fetch(myRequest)
  .then(response => response.json())
  .then(data => {
    console.log(data);
  })
  .catch(console.error);
```

</details>

<details>
  <summary>2. API Fetch</summary>

index.js:

```Javascript
fetch("https://dog.ceo/api/breeds/image/random")
    .then(response => response.json())
    .then(data => {
        console.log(data)
        document.getElementById("image-container").innerHTML = `
            <img src="${data.message}" />
        `
    })
```

```Javascript
fetch("https://apis.scrimba.com/bored/api/activity")
    .then(response => response.json())
    .then(data => {
        console.log(data)
        document.getElementById("activity-name").textContent = data.activity
    })
```

</details>

<details>
  <summary>3. Bored-Bot Javascript</summary>

index.js:

```Javascript
document.getElementById("get-activity").addEventListener("click", function() {
  fetch("https://apis.scrimba.com/bored/api/activity")
    .then(response => response.json())
    .then(data => {
      document.getElementById("activity").textContent = data.activity
    })
})

```

</details>

<details>
  <summary>4. Extra Styling</summary>

Index.js:

```Javascript
document.getElementById("get-activity").addEventListener("click", function() {
  fetch("https://apis.scrimba.com/bored/api/activity")
    .then(response => response.json())
    .then(data => {
      document.getElementById("activity").textContent = data.activity
      document.getElementById("title").textContent = "🦾 HappyBot🦿"
      document.body.classList.add("fun")
    })
})

```

Index.css:

```Javascript
body {
    /* uigradients.com */
    background: #bdc3c7;  /* fallback for old browsers */
    background: -webkit-linear-gradient(to top, #2c3e50, #bdc3c7);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to top, #2c3e50, #bdc3c7); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
    background-repeat: no-repeat;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    font-family: Oxygen, sans-serif;
}

button {
    height: 100px;
    width: 100px;
    border-radius: 50%;
    background-color: red;
    border: 1px solid darkred;
    cursor: pointer;
}

.fun {
    /* CSS generated from https://uigradients.com */
    background: #fc4a1a;  /* fallback for old browsers */
    background: -webkit-linear-gradient(to left, #f7b733, #fc4a1a);  /* Chrome 10-25, Safari 5.1-6 */
    background: linear-gradient(to left, #f7b733, #fc4a1a); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

```

</details>

### [2-URLs & REST](#)

<details>
  <summary>5. GET Method</summary>

index.js:

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/todos", {method: "GET"})
    .then(res => res.json())
    .then(data => console.log(data))
```

</details>

<details>
  <summary>6. Get first 5 blog Posts</summary>

index.js:

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        const postsArr = data.slice(0, 5)
        console.log(postsArr)
    })
```

</details>

<details>
  <summary>7. Display Blogs on Page</summary>

index.js:

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        const postsArr = data.slice(0, 5)
        let html = ""
        for (let post of postsArr) {
            html += `
                <h3>${post.title}</h3>
                <p>${post.body}</p>
                <hr />
            `
        }
        document.getElementById("blog-list").innerHTML = html
    })

```

</details>

<details>
  <summary>8. BlogSpace - Adding Navbar</summary>

index.html:

```html
<html>
    <head>
        <link rel="preconnect" href="https://fonts.gstatic.com">
        <link href="https://fonts.googleapis.com/css2?family=Karla:wght@200;400;700&display=swap" rel="stylesheet">
        <link rel="stylesheet" href="index.css">
    </head>
    <body>
        <nav>
            <h3>BlogSpace</h3>
        </nav>
        <div id="blog-list"></div>
        <script src="index.js"></script>
    </body>
</html>

```

Index.css:

```css
body {
    font-family: 'Karla', sans-serif;
    margin: 0;
    padding: 0;
}

nav {
    background-color: beige;
    padding: 5px;
    height: 30px;
    display: flex;
    align-items: center;
    position: fixed;
    width: 100%;
}

nav > h3 {
    margin: 0;
}

#blog-list {
    padding: 30px 10px 10px;
}

```

Index.js:

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        const postsArr = data.slice(0, 5)
        let html = ""
        for (let post of postsArr) {
            html += `
                <h3>${post.title}</h3>
                <p>${post.body}</p>
                <hr />
            `
        }
        document.getElementById("blog-list").innerHTML = html
    })

```

</details>

<details>
  <summary>9. BlogSpace - Adding Style to Form</summary>

index.css:

```css
body {
    font-family: 'Karla', sans-serif;
    margin: 0;
    padding: 0;
}

nav {
    background-color: beige;
    padding: 5px;
    height: 30px;
    display: flex;
    align-items: center;
    position: fixed;
    width: 100%;
}

nav > h3 {
    margin: 0;
}

#blog-list {
    padding: 10px;
}

form {
    padding: 60px 10px 10px;
    display: grid;
    background-color: lightblue;
}

input#post-title, textarea#post-body {
    margin-bottom: 10px;
}

button {
    padding: 10px;
    font-size: 18px;
    cursor: pointer;
}

```

index.html:

```html
<html>
    <head>
        <link rel="preconnect" href="https://fonts.gstatic.com">
        <link href="https://fonts.googleapis.com/css2?family=Karla:wght@200;400;700&display=swap" rel="stylesheet">
        <link rel="stylesheet" href="index.css">
    </head>
    <body>
        <nav>
            <h3>BlogSpace</h3>
        </nav>
        <form>
            <label for="post-title">Title:</label>
            <input id="post-title" type="text" />
            <label for="post-body">Body:</label>
            <textarea id="post-body"></textarea>
            <button>Post</button>
        </form>
        <div id="blog-list"></div>
        <script src="index.js"></script>
    </body>
</html>

```

Index.js:

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        const postsArr = data.slice(0, 5)
        let html = ""
        for (let post of postsArr) {
            html += `
                <h3>${post.title}</h3>
                <p>${post.body}</p>
                <hr />
            `
        }
        document.getElementById("blog-list").innerHTML = html
    })

```

</details>

<details>
  <summary>10. BlogSpace - Form prevent Default</summary>

Index.js:

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        const postsArr = data.slice(0, 5)
        let html = ""
        for (let post of postsArr) {
            html += `
                <h3>${post.title}</h3>
                <p>${post.body}</p>
                <hr />
            `
        }
        document.getElementById("blog-list").innerHTML = html
    })

document.getElementById("new-post").addEventListener("submit", function(e) {
    e.preventDefault()
    const postTitle = document.getElementById("post-title").value
    const postBody = document.getElementById("post-body").value
    const data = {
        title: postTitle,
        body: postBody
    }
    console.log(data)
})

```

</details>

<details>
  <summary>11. Requests - Body & Headers</summary>

Index.js:

```Javascript
    method: 'POST', // *GET, POST, PUT, DELETE, etc.
    mode: 'cors', // no-cors, *cors, same-origin
    cache: 'no-cache', // *default, no-cache, reload, force-cache, only-if-cached
    credentials: 'same-origin', // include, *same-origin, omit
    headers: {
      'Content-Type': 'application/json'
      // 'Content-Type': 'application/x-www-form-urlencoded',
    },
    redirect: 'follow', // manual, *follow, error
    referrerPolicy: 'no-referrer', // no-referrer, *no-referrer-when-downgrade, origin, origin-when-cross-origin, same-origin, strict-origin, strict-origin-when-cross-origin, unsafe-url
    body: JSON.stringify(data) // body data type must match "Content-Type" header

```

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/todos", {
    method: "POST",
    body: JSON.stringify({
        title: "Buy Milk",
        completed: false
    }),
    headers: {
        "Content-Type": "application/json"
    }
})
    .then(res => res.json())
    .then(data => console.log(data))

```

```Javascript
fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        const postsArr = data.slice(0, 5)
        let html = ""
        for (let post of postsArr) {
            html += `
                <h3>${post.title}</h3>
                <p>${post.body}</p>
                <hr />
            `
        }
        document.getElementById("blog-list").innerHTML = html
    })

document.getElementById("new-post").addEventListener("submit", function(e) {
    e.preventDefault()
    const postTitle = document.getElementById("post-title").value
    const postBody = document.getElementById("post-body").value
    const data = {
        title: postTitle,
        body: postBody
    }

    const options = {
        method: "POST",
        body: JSON.stringify(data),
        headers: {
            "Content-Type": "application/json"
        }
    }

    fetch("https://apis.scrimba.com/jsonplaceholder/posts", options)
        .then(res => res.json())
        .then(data => console.log(data))
})

```

</details>

<details>
  <summary>12. BlogSpace - Add new posts </summary>

Index.js:

```Javascript
let postsArray = []

function renderPosts() {
    let html = ""
    for (let post of postsArray) {
        html += `
            <h3>${post.title}</h3>
            <p>${post.body}</p>
            <hr />
        `
    }
    document.getElementById("blog-list").innerHTML = html
}

fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        postsArray = data.slice(0, 5)
        renderPosts()
    })

document.getElementById("new-post").addEventListener("submit", function(e) {
    e.preventDefault()
    const postTitle = document.getElementById("post-title").value
    const postBody = document.getElementById("post-body").value
    const data = {
        title: postTitle,
        body: postBody
    }

    const options = {
        method: "POST",
        body: JSON.stringify(data),
        headers: {
            "Content-Type": "application/json"
        }
    }

    fetch("https://apis.scrimba.com/jsonplaceholder/posts", options)
        .then(res => res.json())
        .then(post => {
            postsArray.unshift(post)
            renderPosts()
        })
})
```

</details>

<details>
  <summary>13. BlogSpace - Reset Form</summary>

Index.js:

```Javascript
let postsArray = []
const titleInput = document.getElementById("post-title")
const bodyInput = document.getElementById("post-body")
const form = document.getElementById("new-post")

function renderPosts() {
    let html = ""
    for (let post of postsArray) {
        html += `
            <h3>${post.title}</h3>
            <p>${post.body}</p>
            <hr />
        `
    }
    document.getElementById("blog-list").innerHTML = html
}

fetch("https://apis.scrimba.com/jsonplaceholder/posts")
    .then(res => res.json())
    .then(data => {
        postsArray = data.slice(0, 5)
        renderPosts()
    })

form.addEventListener("submit", function(e) {
    e.preventDefault()
    const postTitle = titleInput.value
    const postBody = bodyInput.value
    const data = {
        title: postTitle,
        body: postBody
    }

    const options = {
        method: "POST",
        body: JSON.stringify(data),
        headers: {
            "Content-Type": "application/json"
        }
    }

    fetch("https://apis.scrimba.com/jsonplaceholder/posts", options)
        .then(res => res.json())
        .then(post => {
            postsArray.unshift(post)
            renderPosts()
            titleInput.value = ""
            bodyInput.value = ""
            // form.reset()
        })
})

```

</details>

<details>
  <summary>14. URL Query Strings</summary>

```markdown
1. Get a list of all bike racks sold on the site?
/bikeracks

2. Get a list of all bike racks available in the physical store right now?
   (Assume a query called "available" that is a boolean true/false)
/bikeracks?available=true  ==> {available: "true"} (Will be parsed as a string)

3. Get a list of all "Thule"-brand bike racks that can hold 4 bikes?
   (Assume there are "brand" and "numBikes" queries)
/bikeracks?brand=thule&numBikes=4

```

</details>

### [3-ASYNC JAVASCRIPT](#)

<details>
  <summary>15. Install pygments</summary>

Index.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>16. Install pygments</summary>

Index.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>17. Install pygments</summary>

Index.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>18. Install pygments</summary>

Index.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>19. Install pygments</summary>

Index.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>20. Install pygments</summary>

Index.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

### [5-AIRBNB CLONE](#)

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
