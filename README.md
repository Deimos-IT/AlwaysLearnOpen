# AlwaysLearnOpen
```javascript
function moveRightToLeft() {
        // Get left and right containers
        let leftContainer = document.getElementById('left-container');
        let rightContainer = document.getElementById('right-container');

        // Get all elements in the right container
        let rightProducts = rightContainer.children;
        // Loop through each element in the right container
        for (let i = 0; i < rightProducts.length; i++) {
            // Clone the product
            let clonedProduct = rightProducts[i].cloneNode(true);
            // Set the id of the cloned product to the id of the replaced element
            let replacedId = leftContainer.children[i].id;
            clonedProduct.id = replacedId;
            setTimeout(function () {
                leftContainer.replaceChild(clonedProduct, leftContainer.children[i]);
                clonedProduct.classList.add('green-border-pulse-once');
            }, i * 100); // Replace each child after 0.1 second (100 milliseconds)
        }
    }
```
```css
@keyframes green-pulse {
  0% {
    border-color: rgb(37, 255, 52);
    transform: scale(1);
  }

  50% {
    border-color: rgb(37, 255, 52);
    transform: scale(1.1);
  }

  100% {
    border-color: rgb(37, 255, 52);
    transform: scale(1);
  }
}

.green-border-pulse-once {
  animation: green-pulse 0.5s ease-out 1;
  border: 2px solid transparent;
  /* Adjust the border as per your requirement */
  border-radius: 5px;
  /* Adjust the border radius as per your requirement */
}
```
# disappear
```js
function moveRightToLeft() {
    // Get left and right containers
    let leftContainer = document.getElementById('left-container');
    let rightContainer = document.getElementById('right-container');

    // Get all elements in the right container
    let rightProducts = rightContainer.children;
    // Loop through each element in the right container
    for (let i = 0; i < rightProducts.length; i++) {
        // Clone the product
        let clonedProduct = rightProducts[i].cloneNode(true);
        // Set the id of the cloned product to the id of the replaced element
        let replacedId = leftContainer.children[i].id;
        clonedProduct.id = replacedId;

        // Apply the disappear animation
        clonedProduct.classList.add('disappear-animation');

        // Replace the corresponding element in the left container with the cloned product after a delay
        setTimeout(function() {
            leftContainer.replaceChild(clonedProduct, leftContainer.children[i]);
            // Add the class after the replacement to trigger the animation
        }, i * 100); // Replace each child after 0.1 second (100 milliseconds)
    }
}
```
```css
@keyframes disappear {
    0% {
        opacity: 1;
    }
    100% {
        opacity: 0;
    }
}

.disappear-animation {
    animation: disappear 0.5s ease forwards;
}
```
