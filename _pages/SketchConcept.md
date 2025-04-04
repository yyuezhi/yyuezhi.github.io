---
layout: none
permalink: /SketchConcept/
title: SketchConcept
description: webpage for SketchConcept
nav: true
nav_order: 2
---


<html lang="en">

<head>
  <!-- Required meta tags -->
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
  <script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
  <script id="MathJax-script" async
          src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
  </script>

  <!-- Bootstrap CSS -->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
    integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">

  <title>SketchConcept</title>


  <style>
    .short-image {
      height: 400px; /* Adjust to your preferred height */
      width: auto;
    }
  </style>

</head>

<body>

  <div class="container">
    <div style="text-align: center; margin-top: 100px;">
      <h2> Discovering Design Concepts for CAD Sketches </h2>
      <div style="margin-top: 15px;">
        <span style="margin-right: 15px; font-size: 1.3em;"><a href="https://yyuezhi.github.io/">Yuezhi Yang<sup>1</sup></a> </span>
        <span style="margin-right: 15px; font-size: 1.3em;"><a href="https://haopan.github.io/">Hao Pan<sup>2</sup></a> </span>
      </div>
      <div style="margin-top: 15px;">
        <span style="margin-right: 20px; font-size: 1.2em;"><sup>1</sup>The University of Hong Kong</span>
        <span style="margin-right: 20px; font-size: 1.2em;"><sup>2</sup>Microsoft Research Asia</span>
      </div>
    </div>

    <div style="margin-top: 15px; text-align: center;">
      <span style="margin-right: 15px; font-size: 1.3em;">
        <a href="https://arxiv.org/abs/2210.14451">[Paper (NeurIPS 2022)]</a>
        <a href="https://github.com/yyuezhi/SketchConcept/">[Code]</a>



  <div style="margin-top: 30px;">
    <div class="text-center">
        <img src="../assets/img/SketchConcept/Teaser.png" 
            class="rounded z-depth-1 short-image" 
            alt="example image" 
            style="max-width: 100%; height: auto; display: block; margin: 0 auto;">
    </div>
    <div style="margin-top: 25px;">
      <p>
        <strong>TLDR:</strong> We formulate the task of discovering modular CAD sketch concepts as program library
        induction and propose a self-supervised deep learning framework that discovers modular libraries with end-to-end training
      </p>
    </div>
  </div>



    <div style="margin-top: 30px;">
      <h3 class="text-center">
        - Overview -
      </h3>
      <div style="margin-top: 25px;">
      <p style="text-align: left; font-size: 18px;">
            Sketch design concepts are recurring patterns found in parametric CAD sketches.
Though rarely explicitly formalized by the CAD designers, these concepts are
implicitly used in design for modularity and regularity. In this paper, we propose a
learning based approach that discovers the modular concepts by induction over raw
sketches. We propose the dual implicit-explicit representation of concept structures
that allows implicit detection and explicit generation, and the separation of structure
generation and parameter instantiation for parameterized concept generation, to
learn modular concepts by end-to-end training. We demonstrate the design concept
learning on a large scale CAD sketch dataset and show its applications for design
intent interpretation and auto-completion.
      </p>
      </div>
    </div>





    <div style="margin-top: 50px;">
      <h3 class="text-center">
        - Method -
      </h3>
      <div class="text-center">
        <img src="../assets/img/SketchConcept/method.png" 
            class="rounded z-depth-1 short-image" 
            alt="example image" 
            style="max-width: 100%; height: auto; display: block; margin: 0 auto;">
      </div>
      <div style="margin-top: 25px;">
        <p style="text-align: left; font-size: 18px;">
            Framework illustration. 
            <strong>(a)</strong> The detection module is a transformer network that detects from the sketch sequence 
            \( [t^0_i] \) implicitly encoded concepts \( [\mathbf{q}_i] \) and their composition \( \mathbf{q}_R \). 
            <strong>(b)</strong> Each \( \mathbf{q} \) is quantized against the concept library \( \mathbf{L}^1 \) 
            to obtain prototype \( \mathbf{q}' \), which is expanded by the structure network into an explicit structure 
            \( \mathbf{T}^1 \) and further instantiated by the parameter network into \( t^1 \). 
            <strong>(c)</strong> The collection of \( [t^1_i] \) are assembled by the composition operator \( R_S \) 
            generated from \( \mathbf{q}_R \) to obtain the final generated sketch graph, which is compared with the 
            input sketch for loss computation.
        </p>
      </div>
    </div>


    <div style="margin-top: 50px; margin-bottom: 30px;">
      <h3 class="text-center">
        - Citation -
      </h3>
      <div style="margin-top: 35px;">
        <pre style="text-align: left; font-size: 14px;"><code>
          @inproceedings{yang2022sketchconcept,
          author = {Yuezhi Yang, Hao Pan},
          booktitle = {Advances in Neural Information Processing Systems},
          title = {Discovering Design Concepts for CAD Sketches},
          volume = {35},
          year = {2022}
          }
        </code></pre>
      </div>
    </div>

