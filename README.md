>이번 시험 및 과제를 해결하며 변환행렬을 통해 이미지를 기하학적으로 보정하는 원리와 보정하는 과정 등을 공부할 수 있었고 이를 코드로 작성할 수 있었습니다. 또 예제로 주어진 이미지를 입력하여 p5.js로 이미지를 THRESH_OTSU 방식으로 이진화 하고 이를 기하학적으로 보정하는 코드를 아무런 도움 없이 이때동안 학습한 내용만으로, 특히 가장 짧은 코드로 작성하여 내심 기뻤습니다.

```
let img;

function preload() {
  img = loadImage('test.png');
}

function setup() {
  createCanvas(img.width*2, img.height*2);
  img.filter(THRESHOLD, 0.7); //p5.js 내부 THRESH_OTSU 방식 이진화
  let m = [1, -0.15, 0.1, 1, 0, 0]; //기하학적 보정값
  applyMatrix(m[0], m[1], m[2], m[3], m[4], m[5]); //applyMatrix 함수를 통해 변환 행렬 적용
  image(img, 0, 0); 
}
```
