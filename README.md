# Browser Height Calculation

**You can now use `100dvh` instead!**  
`100dvh` provides a more accurate calculation of the full-screen height in most modern browsers. However, the method below is still useful for compatibility with older browsers.

---

* Calculates the height of the scanner.

* In some browsers, problems may occur when using **100vh** as the screen height for full-screen work.

## Function and Usage

**Lang:  `Javascript`**
```
function appHeight() {
    const e = document.documentElement;
    e.style.setProperty("--vh", .01 * window.innerHeight + "px")
}
window.addEventListener("resize", appHeight), appHeight();
```

* To solve this problem, **`height: (calc(var(--vh, 1vh) * 100))`** is used on the **css** side.

* Since the name of the property we added is **`--vh`**, we have to use **`--vh`** when calling on the css side.

**Lang:  `CSS`**

```
body{
    height: (calc(var(--vh, 1vh) * 100));
}
```
