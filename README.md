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

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>6. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>7. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>8. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>9. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>10. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

### [3-AIRBNB CLONE](#)

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
