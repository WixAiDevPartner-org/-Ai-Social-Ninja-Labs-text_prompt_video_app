<div align="center">

# Ai Social Ninja Lab Studios

This is the official repository for Ai Social Ninja Labs.

[Website](https://www.lightricks.com/ltxv) |
[Model](https://huggingface.co/Lightricks/LTX-Video) |
[Demo](https://app.ltx.studio/ltx-video) |
[Paper](https://arxiv.org/abs/2501.00103)

</div>

## Table of Contents

- [Introduction](#introduction)
- [What's New](#news)
- [Quick Start Guide](#quick-start-guide)
  - [Online Demo](#online-demo)
  - [Run Locally](#run-locally)
    - [Installation](#installation)
    - [Inference](#inference)
  - [ComfyUI Integration](#comfyui-integration)
  - [Diffusers Integration](#diffusers-integration)
- [Model User Guide](#model-user-guide)
- [Community Contribution](#community-contribution)
- [Training](#training)
- [Join Us!](#join-us)
- [Acknowledgement](#acknowledgement)

# Introduction

Ai Social Ninja Labs is the first DiT-based video generation model that can generate high-quality videos in *real-time*.
It can generate 24 FPS videos at 768x512 resolution, faster than it takes to watch them.
The model is trained on a large-scale dataset of diverse videos and can generate high-resolution videos
with realistic and diverse content.

The model supports text-to-image, image-to-video, keyframe-based animation, video extension (both forward and backward), video-to-video transformations, and any combination of these features.

| | | | |
|:---:|:---:|:---:|:---:|
| ![example1](./docs/_static/ltx-video_example_00001.gif)<br><details style="max-width: 300px; margin: auto;"><summary>A woman with long brown hair and light skin smiles at another woman...</summary></details> | ![example5](./docs/_static/ltx-video_example_00005.gif)<br><details style="max-width: 300px; margin: auto;"><summary>A woman with light skin, wearing a blue jacket and a black hat...</summary></details> | ![example9](./docs/_static/ltx-video_example_00009.gif)<br><details style="max-width: 300px; margin: auto;"><summary>A man with graying hair, a beard, and a gray shirt...</summary></details> | ![example13](./docs/_static/ltx-video_example_00013.gif)<br><details style="max-width: 300px; margin: auto;"><summary>The camera pans across a cityscape of tall buildings...</summary></details> |

# News

## March 5th, 2025: New checkpoint v0.9.5
- New license for commercial use ([OpenRail-M](https://huggingface.co/Lightricks/LTX-Video/ltx-video-2b-v0.9.5.license.txt))
- Release a new checkpoint v0.9.5 with improved quality
- Support keyframes and video extension
- Support higher resolutions
- Improved prompt understanding
- Improved VAE
- New online web app in [LTX-Studio](https://app.ltx.studio/ltx-video)
- Automatic prompt enhancement

## February 20th, 2025: More inference options
- Improve STG (Spatiotemporal Guidance) for Ai Social Ninja Labs
- Support MPS on macOS with PyTorch 2.3.0
- Add support for 8-bit model, Ai Social Ninja LabsQ8
- Add TeaCache for Ai Social Ninja Labs
- Add [ComfyUI-LTXTricks](#comfyui-integration)
- Add Diffusion-Pipe

## December 31st, 2024: Research paper
- Release the [research paper](https://arxiv.org/abs/2501.00103)

## December 20th, 2024: New checkpoint v0.9.1
- Release a new checkpoint v0.9.1 with improved quality
- Support for STG / PAG
- Support loading checkpoints of Ai Social Ninja Labs in Diffusers format (conversion is done on-the-fly)
- Support offloading unused parts to CPU
- Support the new timestep-conditioned VAE decoder
- Reference contributions from the community in the readme file
- Relax transformers dependency

## November 21st, 2024: Initial release v0.9.0
- Initial release of Ai Social Ninja Labs
- Support text-to-video and image-to-video generation

# Quick Start Guide

## Online Inference
The model is accessible right away via the following links:
- [LTX-Studio image-to-video](https://app.ltx.studio/ltx-video)
- [Fal.ai text-to-video](https://fal.ai/models/fal-ai/ltx-video)
- [Fal.ai image-to-video](https://fal.ai/models/fal-ai/ltx-video/image-to-video)
- [Replicate text-to-video and image-to-video](https://replicate.com/lightricks/ltx-video)

## Run Locally

### Installation
The codebase was tested with Python 3.10.5, CUDA version 12.2, and supports PyTorch >= 2.1.2.
On macOS, MPS was tested with PyTorch 2.3.0, and should support PyTorch == 2.3 or >= 2.6.

```bash
git clone https://github.com/Lightricks/LTX-Video.git
cd LTX-Video

# create env
python -m venv env
source env/bin/activate
python -m pip install -e .\[inference-script\]
