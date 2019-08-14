## Dependencies:

- [RXJS](https://rxjs-dev.firebaseapp.com)
- [React Hooks](https://pt-br.reactjs.org/docs/hooks-intro.html)

### Install project dependencies:
```
$ cd your-react-project
$ yarn add rxjs
```

### Add in your CSS file
```
.draggable{
  transition: box-shadow 0.25s ease-in-out;
  transition: box-shadow 0.25s ease-in-out;
  transition: box-shadow 0.25s ease-in-out, transform 0.25s ease-in-out;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  box-shadow: 0;
  position:absolute;
  z-index:100;
  padding:10px;
  text-align:center;

  &.rx-focus {
    box-shadow: 1px 2px 3px #888;
    cursor: move;
    z-index:102;
  }
}

```


### Example

```
import React, { useEffect } from 'react';
import useDragAndDrop from 'your-path/useDragAndDrop';

const YourComponent = () => {
   const initialPosition = { x: 25, y: 25 }; // x = left, y = top
   // or   const initialPosition = { x: 25, y: 25, reversed: true }; //Reversed option will change  x = right, y = bottom

   const [currentPosition] = useDragAndDrop(`#selector`, initialPosition); //initial position is optional

   useEffect(() => {
     console.log(`Current position >>> ${currentPosition}`)
  }, [currentPosition]);

   return (<div id="selector" className="draggable">
      I'm dragging!!
   </div>);
}

export default YourComponent;

```


