<div align="center">

# Tracking with ML

<figure>
    <img src="https://raw.githubusercontent.com/HSF-reco-and-software-triggers/Tracking-ML-Exa.TrkX/master/docs/media/final_wide.png" width="250"/>
</figure>
    
### Exa.TrkX Collaboration


[Documentation](https://hsf-reco-and-software-triggers.github.io/Tracking-ML-Exa.TrkX/)

![badge](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/murnanedaniel/acee2761c6c03febc3331296514ff721/raw/test.json) ![ci](https://github.com/HSF-reco-and-software-triggers/Tracking-ML-Exa.TrkX/workflows/ci/badge.svg)


</div>

Welcome to repository and documentation for ML pipelines and techniques by the ExatrkX Collaboration. Here we present a set of templates, best practices and results gathered from significant trial and error, to speed up the development of others in the domain of machine learning for high energy physics. We focus on applications specific to detector physics, but many tools can be applied to other areas, and these are collected in an application-agnostic way in the [Tools](https://hsf-reco-and-software-triggers.github.io/Tracking-ML-Exa.TrkX/tools/overview/) section.

## Intro

To start as quickly as possible, clone the repository, [Install](https://hsf-reco-and-software-triggers.github.io/Tracking-ML-Exa.TrkX/pipelines/quickstart) and follow the steps in [Quickstart](https://hsf-reco-and-software-triggers.github.io/Tracking-ML-Exa.TrkX/pipelines/quickstart). This will get you generating toy tracking data and running inference immediately. Many of the choices of structure will be made clear there. If you already have a particle physics problem in mind, you can apply the [Template](https://hsf-reco-and-software-triggers.github.io/Tracking-ML-Exa.TrkX/pipelines/choosingguide.md) that is most suitable to your use case.

Once up and running, you may want to consider more complex ML [Models](https://hsf-reco-and-software-triggers.github.io/Tracking-ML-Exa.TrkX/models/overview/). Many of these are built on other libraries (for example [Pytorch Geometric](https://github.com/rusty1s/pytorch_geometric)).

<div align="center">
<figure>
  <img src="https://raw.githubusercontent.com/HSF-reco-and-software-triggers/Tracking-ML-Exa.TrkX/master/docs/media/application_diagram_1.png" width="600"/>
</figure>
</div>

## Install

It's recommended to start a conda environment before installation:

```
conda install --name exatrkx-tracking python=3.8
conda activate exatrkx-tracking
```

The repository can be installed and run with GPU or CPU. The installation depends on this compatibility:

<table style="border: 1px solid gray; border-collapse: collapse">
<tr style="border-bottom: 1px solid gray">
<th style="border-bottom: 1px solid gray"> CPU </th>
<th style="border-left: 1px solid gray"> GPU </th>
</tr>
<tr>
<td style="border-bottom: 1px solid gray">

1. Run 
`export CUDA=cpu`
    
</td>
<td style="border-left: 1px solid gray">

1a. Find the GPU version cuda XX.X with `nvcc --version`
    
1b. Run `export CUDA=cuXXX`, with `XXX = 92, 101, 102, 110`

</td>
</tr>
<tr style="border-bottom: 1px solid gray">
<td colspan="2">

2. Install Pytorch and dependencies 

```pip install --user -r requirements.txt -f https://download.pytorch.org/whl/torch_stable.html -f https://pytorch-geometric.com/whl/torch-1.5.0.html```

</td>
</tr>
<tr style="border-bottom: 1px solid gray">
<td colspan="2">

3. Install local packages

```pip install -e .```
    
</td>
</tr>
<tr>
<td style="border-bottom: 1px solid gray">

4. Install CPU-optimized packages

```pip install faiss-cpu```
    
</td>
<td style="border-left: 1px solid gray">

4. Install GPU-optimized packages

```pip install faiss-gpu cupy-cudaXXX```, with ```XXX```
    
</td>
</tr>
</table>