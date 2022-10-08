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
  <summary>3. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>4. Install pygments</summary>

components/Card.js:

```Javascript


```

```Javascript


```

```Javascript


```

</details>

<details>
  <summary>5. Install pygments</summary>

components/Card.js:

```Javascript


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
