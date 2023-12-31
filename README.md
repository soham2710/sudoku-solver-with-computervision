

<div>
    <a href="https://www.loom.com/share/ef452960b65140339ad150bd0abcb57e">
      <p>Real Time Sudoku Solver</p>
    </a>
    <a href="https://www.loom.com/share/ef452960b65140339ad150bd0abcb57e">
      <img style="max-width:300px;" src="https://cdn.loom.com/sessions/thumbnails/ef452960b65140339ad150bd0abcb57e-with-play.gif">
    </a>
  </div>


## Overview
Sudoku is one of the most popular puzzle of all time.The goal of Sudoku is to fill 9x9 grid such that each row,each column and 3x3 grid contains all of the digits between 1 to 9. In this project we aim to create a real time Sudoku solver which recognise the elements of Sudoku puzzle and providing a digital solution using Computer vision. 

## Steps
1. Grab the Sudoko Grid from the Webcam Image
2. Extract and Detect the Digits
2. Solve the puzzel and Print the Solution

## 1. Grab the Sudoko Grid from the Webcam Image

<summary><b>Extracting the Contour with biggest area</b></summary>
<ol>
  <li>Convert image to Gray scale <i>(cv2.cvtColor)</i></li>
  <li>Blur the image using Gaussian Blur <i>(cv2.GaussianBlur)</i></li>
  <li>Apply adaptive thresholding <i>(cv2.adaptiveThreshold)</i></li>
  <li>Extract the contour with biggest area <i>(cv2.contourArea)</i></i></li>
</ol>


<p align="center">
  <img src="https://github.com/soham2710/sudoku-solver-with-computervision/blob/main/Images/original.png" width="300" height="250" />
</p>


## 2. Extract and Detect the Digits


<summary><b>Process the Extracted Grid</b></summary>
  Use <i>cv2.morphologyEx</i> and Invert the image
 
 
 <p align="center">
  <img src="https://github.com/soham2710/sudoku-solver-with-computervision/blob/main/Images/p-window.png" width="300" height="300" />
  <img src="https://github.com/soham2710/sudoku-solver-with-computervision/blob/main/Images/invert%20image.png" width="300" height="300" />
</p>


<summary><b>Get Individual Cells of the grid and Predict the Digit</b></summary>
  <p>Model used for prediction has been trained on subset of <i>Chars4K Dataset</i> which contains digits only (0-9).
  Model can be viewed <a href="[Real-Time-Sudoku-Solver.ipynb](https://github.com/soham2710/sudoku-solver-with-computervision/blob/main/Real-Time-Sudoku-Solver.ipynb)">here</a></p>
  <p>While predicting the digits, blank cells would be predicted as 0.
    Blank cells can be identified by calculating sum of all the pixels (sum would be large)</p>


## 3. Solve the puzzle and Print the Solution

<summary><b>Solution and Final Result</b></summary>
<p>To solve Sudoku, backtracking has been used. Sudoku Backtracking is a recursive algorithm which goes through each cells and sequentially assigns numbers from 1 to 9 if the cell is empty. Notebook for the same can be viewed <a href="https://github.com/soham2710/sudoku-solver-with-computervision/tree/main">here</a>.</p>
  <p>To display the result use <i>cv2.putText</i>.</p>


<p align="center">
  <img src="https://github.com/soham2710/sudoku-solver-with-computervision/blob/main/Images/result.png" width="300" height="250" />
</p>

