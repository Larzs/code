# Javascript

## Host and iframe communication

Send the message from the iframe:
```markdown
window.top.postMessage('reply', '*');
```
And listen to it in the parent:
```markdown
window.onmessage = function(event) {
    if (event.data == 'reply') {
        console.log('Reply received!');
    }
}
```

## Timeout destructor as callback

```markdown
function animate(div) {
    let counter = 0;
    const interval = setInterval(function () {
        div.innerHTML = "Uploading" + ".".repeat(counter++ % 4)
    }, 500)
    return () =>
        clearInterval(interval)
}

const stopAnimating = animate(document.getElementById("id"));

doSomeThingAsync().then(() => stopAnimating());
```

## Check if the script is run inside iframe

```markdown
function iniFrame() { 
    if ( window.location !== window.parent.location ) 
    { 
      
        // The page is in an iFrames 
        document.write("The page is in an iFrame"); 
    }  
    else { 
          
        // The page is not in an iFrame 
        document.write("The page is not in an iFrame"); 
    } 
} 
  
// Calling iniFrame function 
iniFrame(); 
```

## Debuging

Wrap variables in curly brackets to better see which value belongs to which variable.

```markdown
let width = 100;
let height = 50;
let length = 75;

console.log({ width, height, length });
{ width: 100, height: 50, length: 75 }
```
