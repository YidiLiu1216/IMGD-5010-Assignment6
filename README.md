# IMGD-5010-Assignment6
## Link
[Link to the Page](https://editor.p5js.org/YidiLiu1216/sketches/XyU1s74Mn)
## Description
This code implement the game of life and 
## Code
```
let gridsize=20;
let columns;
let rows;
let cells=[];
let nextstate=[];
function setup() {
  createCanvas(400, 400);
  frameRate(10);
  
  columns=width/gridsize;
  rows=height/gridsize;
  for(let i=0;i<columns;i++){
    let r=[];
    for(let j=0;j<rows;j++){
      r.push(floor(random(2)));
    }
    cells.push(r);
    nextstate.push(r);
  }
  //console.log(cells)
}

function draw() {
  background(255);
  for(let i=0;i<rows;i++){
    for(let j=0;j<columns;j++){
       console.log(cells[i][j]);
       fill((1-cells[i][j])*255);
       square(i*gridsize,j*gridsize,gridsize);
    }  
  }
function NextState(r,c){
   
}
}

```
## Result
