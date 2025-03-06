---
layout: none
permalink: /GenVDM/
title: GenVDM
description: webpage for GenVDM
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

  <title>GenVDM</title>


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
      <h2> GenVDM: Generating Vector Displacement Maps From a Single Image </h2>
      <div style="margin-top: 15px;">
        <span style="margin-right: 15px; font-size: 1.3em;"><a href="https://yyuezhi.github.io/">Yuezhi Yang<sup>1</sup></a> </span>
        <span style="margin-right: 15px; font-size: 1.3em;"><a href="https://qiminchen.github.io/">Qimin Chen<sup>2</sup></a> </span>
        <span style="margin-right: 15px; font-size: 1.3em;"><a href="http://www.vovakim.com/">Vladimir G. Kim<sup>3</sup></a> </span>
        <span style="font-size: 1.3em;"><a href="https://www.cse.iitb.ac.in/~sidch/">Siddhartha Chaudhuri<sup>3</sup></a> </span>
        <span style="font-size: 1.3em;"><a href="https://www.cs.utexas.edu/~huangqx/">Qixing Huang<sup>1</sup></a> </span>
        <span style="margin-right: 15px; font-size: 1.3em;"><a href="https://czq142857.github.io/">Zhiqin Chen<sup>2</sup></a> </span>
      </div>
      <div style="margin-top: 15px;">
        <span style="margin-right: 20px; font-size: 1.2em;"><sup>1</sup>The University of Texas at Austin</span>
        <span style="margin-right: 20px; font-size: 1.2em;"><sup>2</sup>Simon Fraser University</span>
        <span style="margin-right: 20px; font-size: 1.2em;"><sup>3</sup>Adobe Research</span>
      </div>
    </div>

    <div style="margin-top: 15px; text-align: center;">
      <span style="margin-right: 15px; font-size: 1.3em;">
        <a href="https://www.arxiv.org/abs/2503.00605">[Paper (CVPR 2025)]</a>
        <a href="https://github.com/yyuezhi/GenVDM/">[Code]</a>
        <a href="https://github.com/yyuezhi/GenVDM/">[Data]</a>


  <div style="margin-top: 30px;">
    <div class="text-center">
      <img src="../assets/img/GenVDM/Teaser.png" class="img-fluid rounded z-depth-1 short-image" alt="example image">
    </div>
    <div style="margin-top: 25px;">
      <p>
        <strong>TLDR:</strong> We introduce GenVDM, a method that can generate
        a highly detailed Vector Displacement Map (VDM) from a single
         image. The generated VDMs can be directly applied to mesh
        surfaces to create intricate geometric details.
      </p>
    </div>
  </div>

    <div style="margin-top: 30px;">
      <h3 class="text-center">
        - Interactive Modeling -
      </h3>
    <img src="../assets/img/GenVDM/demo.gif" 
     class="rounded z-depth-1 short-image" 
     alt="example animation" 
     style="max-width: 100%; height: auto; display: block; margin: 0 auto;">

      <div style="margin-top: 25px;">
      <p style="text-align: left; font-size: 18px;">
      Given input image shown on top-right, our method could generate VDM in .exr format, which could directly be used in blender for interactive modelling.
      </p>
      </div>
    </div>    

    <div style="margin-top: 30px;">
      <h3 class="text-center">
        - Overview -
      </h3>
      <div style="margin-top: 25px;">
      <p style="text-align: left; font-size: 18px;">
            We introduce the first method for generating Vector Displacement Maps (VDMs): parameterized, detailed geometric stamps commonly used in 3D modeling. Given a single input image, our method first generates multi-view normal maps and then reconstructs a VDM from the normals via a novel reconstruction pipeline. We also propose an efficient algorithm for extracting VDMs from 3D objects, and present the first academic VDM dataset. Compared to existing 3D generative models focusing on complete shapes, we focus on generating parts that can be seamlessly attached to shape surfaces. The method gives artists rich control over adding geometric details to a 3D shape. Experiments demonstrate that our approach outperforms existing baselines. Generating VDMs offers additional benefits, such as using 2D image editing to customize and refine 3D details. 
      </p>
      </div>
    </div>





    <div style="margin-top: 50px;">
      <h3 class="text-center">
        - Method -
      </h3>
      <div class="text-center">
        <img src="../assets/img/GenVDM/pipeline.png" 
            class="rounded z-depth-1 short-image" 
            alt="example image" 
            style="max-width: 100%; height: auto; display: block; margin: 0 auto;">
      </div>
      <div style="margin-top: 25px;">
      <p style="text-align: left; font-size: 18px;">
          Our image-to-VDM pipeline. Given an input image, we first utilize a multi-view image diffusion model to generate six normal maps with predefined camera pose. We then reconstruct an accurate (but perhaps noisy) mesh from the multi-view normals with differentiable rendering and neural SDF representation. Then we parameterize the mesh by fitting a deformable square to it with a neural deformation field. An VDM image can thus be obtained by discretizing the square into pixels and infer each pixel’s displacement from the neural deformation field.
      </p>
      </div>
    </div>


    <div style="margin-top: 50px;">
      <h3 class="text-center">
        - Data Preparation -
      </h3>
      <div class="text-center">
        <img src="../assets/img/GenVDM/data_preparation.png" 
            class="rounded z-depth-1 short-image" 
            alt="example image" 
            style="max-width: 100%; height: auto; display: block; margin: 0 auto;">
      </div>

      <div style="margin-top: 10px;">
        <p style="text-align: left; font-size: 18px;">
          Our data preparation pipeline. For each interesting object from Objaverse (a), we use a 3D lasso tool to segment out interesting parts. For each part, we densely sample points on the part's surface and then perform Screened Poisson Surface Reconstruction to obtain a single connected mesh (b). We then stitch the mesh to a square mesh with an algorithm inspired by Poisson Image Editing (c). Afterwards, we can color the part and render RGB images (d) and normal maps (e) for training the image diffusion model.
        </p>
      </div>
    </div>


    <div style="margin-top: 50px; margin-bottom: 30px;">
      <h3 class="text-center">
        - Citation -
      </h3>
      <div style="margin-top: 35px;">
        <pre style="text-align: left; font-size: 14px;"><code>
    @inproceedings{yang2025GenVDM,
      title={GenVDM: Generating Vector Displacement Maps From a Single Image},
      author = {Yang, Yuezhi and Chen, Qimin and Kim, Vladimir G. and Chaudhuri, Siddhartha and Huang, Qixing and Chen, Zhiqin},
      booktitle={Conference on Computer Vision and Pattern Recognition},
      year={2025},
    }
        </code></pre>
      </div>
    </div>

