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
let lifelong=[];
let nextstate=[];
function setup() {
  createCanvas(400, 400);
  frameRate(10);
  
  columns=width/gridsize;
  rows=height/gridsize;
  for(let i=0;i<columns;i++){
    let r=[];
    let n=[];
    let l=[];
    for(let j=0;j<rows;j++){
      r.push(floor(random(2)));
      n.push(0);
      l.push(0);
    }
    cells.push(r);
    nextstate.push(n);
    lifelong.push(l);
  }
  //console.log(cells)
}

function draw() {
  background(255);
  for(let i=0;i<columns;i++){
    for(let j=0;j<rows;j++){
       //console.log(cells[i][j]);
       NextState(i,j);
       fill((1-lifelong[i][j]*0.1)*255);
       square(i*gridsize,j*gridsize,gridsize);
    }  
  }
  for(let i=0;i<columns;i++){
    for(let j=0;j<rows;j++){
      cells[i][j]=nextstate[i][j]
    }  
  }
}
function NextState(c,r){
   let left=c-1;
   if(left<0){left=columns-1;}
   let right=c+1;
   if(right>=columns){right=0;}
   let up=r-1;
   if(up<0){up=rows-1;}
   let down=r+1;
   if(down>=rows){down=0;}
  
   let aliveneighbour=
   cells[left][up]+cells[left][r]+cells[left][down]+
   cells[c][up]+cells[c][down]+
   cells[right][up]+cells[right][r]+cells[right][down];
  
   if (cells[c][r] == 1) {
    if (aliveneighbour < 2 || aliveneighbour > 3) {
      nextstate[c][r] = 0;
      lifelong[c][r] = 0;
    } else {
      nextstate[c][r] = 1;
      lifelong[c][r] += 1;
    }
  } else {
    if (aliveneighbour == 3) {
      nextstate[c][r] = 1;
      lifelong[c][r] += 1;
    } else {
      nextstate[c][r] = 0;
      lifelong[c][r] = 0;
    }
  }
}
```
## Result
