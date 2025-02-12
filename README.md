# Text2Mesh [[Project Page](https://threedle.github.io/text2mesh/)]
[![arXiv](https://img.shields.io/badge/arXiv-Text2Mesh-b31b1b.svg)](https://arxiv.org/abs/2112.03221)
![Pytorch](https://img.shields.io/badge/PyTorch->=1.9.0-Red?logo=pytorch)
![crochet candle](images/vases.gif)
**Text2Mesh** is a method for text-driven stylization of a 3D mesh, as described in "Text2Mesh: Text-Driven Neural Stylization for Meshes" (forthcoming).

## Getting Started
### Making GIF and intermediary results
* argument to save images at n iteration
- --iter_save int (default 100)
* argument to add for making the gif at the end
- --make_gif
* argument to increase delay between the images for the gif
- --gif_delay float (default 0.3)
- Code usage example
```
!python main.py --run branch --obj_path data/source_meshes/shoe.obj --output_dir results/demo/shoe/hike --prompt "a hiking boot" --sigma 5.0  --clamp tanh --n_normaugs 4 --n_augs 1 --normmincrop 0.1 --normmaxcrop 0.1 --geoloss --colordepth 2 --normdepth 2 --iter_save 10 --make_gif --gif_delay 1.0  --frontview --frontview_std 4 --clipavg view --lr_decay 0.9 --clamp tanh --normclamp tanh  --maxcrop 1.0 --save_render --seed 11 --n_iter 200 --learning_rate 0.0005 --normal_learning_rate 0.0005 --background 1 1 1 --frontview_center 0.5 0.6283
```

### Installation

**Note:** The below installation will fail if run on something other than a CUDA GPU machine.
```
conda env create --file text2mesh.yml
conda activate text2mesh
```

System requirements
### System Requirements
- Python 3.7
- CUDA 10.2
- GPU w/ minimum 8 GB ram


### Run examples
Call the below shell scripts to generate example styles. 
```bash
# cobblestone alien
./demo/run_alien_cobble.sh
# shoe made of cactus 
./demo/run_shoe.sh
# lamp made of brick
./demo/run_lamp.sh
# ...
```
The outputs will be saved to `results/demo`, with the stylized .obj files, colored and uncolored render views, and screenshots during training.

#### Outputs
<p float="center">
<img alt="alien" height="135" src="images/alien.png" width="240"/>
<img alt="alien geometry" height="135" src="images/alien_cobble_init.png" width="240"/>
<img alt="alien style" height="135" src="images/alien_cobble_final.png" width="240"/>
</p>

<p float="center">
<img alt="alien" height="135" src="images/alien.png" width="240"/>
<img alt="alien geometry" height="135" src="images/alien_wood_init.png" width="240"/>
<img alt="alien style" height="135" src="images/alien_wood_final.png" width="240"/>
</p>

<p float="center">
<img alt="candle" height="135" src="images/candle.png" width="240"/>
<img alt="candle geometry" height="135" src="images/candle_init.png" width="240"/>
<img alt="candle style" height="135" src="images/candle_final.png" width="240"/>
</p>

<p float="center">
<img alt="person" height="135" src="images/person.png" width="240"/>
<img alt="ninja geometry" height="135" src="images/ninja_init.png" width="240"/>
<img alt="ninja style" height="135" src="images/ninja_final.png" width="240"/>
</p>

<p float="center">
<img alt="shoe" height="135" src="images/shoe.png" width="240"/>
<img alt="shoe geometry" height="135" src="images/shoe_init.png" width="240"/>
<img alt="shoe style" height="135" src="images/shoe_final.png" width="240"/>
</p>

<p float="center">
<img alt="vase" height="135" src="images/vase.png" width="240"/>
<img alt="vase geometry" height="135" src="images/vase_init.png" width="240"/>
<img alt="vase style" height="135" src="images/vase_final.png" width="240"/>
</p>

<p float="center">
<img alt="lamp" height="135" src="images/lamp.png" width="240"/>
<img alt="lamp geometry" height="135" src="images/lamp_init.png" width="240"/>
<img alt="lamp style" height="135" src="images/lamp_final.png" width="240"/>
</p>

<p float="center">
<img alt="horse" height="135" src="images/horse.png" width="240"/>
<img alt="horse geometry" height="135" src="images/horse_init.png" width="240"/>
<img alt="horse style" height="135" src="images/horse_final.png" width="240"/>
</p>

## Other implementations
[Kaggle Notebook](https://www.kaggle.com/neverix/text2mesh/) (by [neverix](https://www.kaggle.com/neverix))


## Citation
```
@article{text2mesh,
    author = {Michel, Oscar
              and Bar-On, Roi
              and Liu, Richard
              and Benaim, Sagie
              and Hanocka, Rana
              },
    title = {Text2Mesh: Text-Driven Neural Stylization for Meshes},
    journal = {arXiv preprint arXiv:2112.03221},
    year  = {2021}
}
```
