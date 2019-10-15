# The Challenge
Explained in the video http://j.mp/tutorChallenge

# Demo the challenge solution
The demo of desired behavior: http://j.mp/shortFunc

[](https://share.vidyard.com/watch/2Uc7z85XKuJB39H2yaToss?)

![Check out this Video](https://cdn.vidyard.com/thumbnails/5907559/u56bZg27l2cBTCuouj-8kg_play_button_small.jpg)

Check out this video: [https://share.vidyard.com/watch/2Uc7z85XKuJB39H2yaToss?](https://share.vidyard.com/watch/2Uc7z85XKuJB39H2yaToss?)
# The Solution
```javascript

document.body.style.zoom = "250%";
px = window.scrollX + document.getElementById('pyStdout').getBoundingClientRect().left // X
py = window.scrollY + document.getElementById('pyStdout').getBoundingClientRect().top // Y
document.onkeyup = async function(e) {
  function sleep(ms) {
    return new Promise(resolve => setTimeout(resolve, ms));
  }
  if (e.which == 75) {
    let b = document.getElementById("jmpStepBack");
    b.click();
  } else if (e.which == 74) {
    let b = document.getElementById("jmpStepFwd");
    await b.click();
    await sleep(2000);
    let v = document.getElementById("curLineArrow");
    v.focus();
    v.scrollIntoView();
  } else if (e.which == 80) {
    let tbox = document.getElementById("heapHeader");
    tbox.focus();
    tbox.scrollIntoView();
    tbox = document.getElementById("progOutputs");
    window.scrollTo(px, py);
    tbox.focus();
    tbox.scrollIntoView();
  } else if (e.which == 49) {
    let b = document.getElementById("jmpFirstInstr");
    await b.click();
    await sleep(1000);
    let v = document.getElementById("curLineArrow");
    v.focus();
    v.scrollIntoView();
  } else if (e.ctrlKey && e.altKey && e.shiftKey && e.which == 85) {
    alert("Ctrl + Alt + Shift + U shortcut combination was pressed");
  }
};
```

## Explanation
1. The code does not have comments, purposely.  
2. This enables it be used as a bookmarklet - which can be automatically launched by some other app (say [TaperMonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=en)?)
	- to install this code as a bookmarklet, see [this]([https://mreidsma.github.io/bookmarklets/installing.html](https://mreidsma.github.io/bookmarklets/installing.html))
4. Using `async` to enable Promises code so that `sleep` works properly. 


