
# VideoCrafter：A Toolkit for Text-to-video Generation and Editing 


## 🔆 Introduction
🤗🤗🤗 VideoCrafter is an open-source video generation and editing toolbox for crafting video content.   
It currently includes the following THREE types of models:

### 1. LV Diffusion: Generic Text-to-video Generation Models
LV Diffusion is a base text-to-video (T2V) generation model based on the latent video diffusion models ([LVDM](https://yingqinghe.github.io/LVDM/)). 
It can synthesize realistic videos based on the input text descriptions.

<table class="center">
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <tr>
  <td><img src=assets/summary/t2v/005.gif width="170"></td>
  <td><img src=assets/summary/t2v/006.gif width="170"></td>
  <td><img src=assets/summary/t2v/008.gif width="170"></td>
  <td><img src=assets/summary/t2v/004.gif width="170"></td>
  </tr>
</table >

<br>  

### 2. VideoLoRA: Personalized Text-to-Video Generation with LoRA

Based on the pretrained LV Diffusion, we can create our **own** video generation models by finetuning it on a set of video clips or images describing a certain concept.

We adopt [LoRA](https://arxiv.org/abs/2106.09685) to implement the finetuning as it is eary to train and require less computational resources.

Below are generation results from our **four VideoLoRA models** that are trained on four different styles of video clips.

By providing a sentence describing the video content along with a LoRA trigger word (specified during LoRA training), it can generate videos with the desired style(or subject/concept).


Results of inputting `A monkey is playing a piano, ${trigger_word}` to the four VideoLoRA models:   
<table class="center">
  <td><img src=assets/summary/1/001_loving_vincent.gif width="170"></td>
  <td><img src=assets/summary/1/002_frozen.gif width="170"></td>
  <td><img src=assets/summary/1/003_your_name.gif width="170"></td>
  <td><img src=assets/summary/1/004_coco.gif width="170"></td>
  </tr>
  <td style="text-align:center;" width="170">"Loving Vincent style"</td>
  <td style="text-align:center;" width="170">"frozenmovie style"</td>
  <td style="text-align:center;" width="170">"MakotoShinkaiYourName style"</td>
  <td style="text-align:center;" width="170">"coco style"</td>
  <tr>
</table >
The trigger word for each VideoLoRA is annotated below the generation result.

<br>  

### 3. VideoControl: Video Generation with More Conditions
To enhance the controllable abilities of the T2V model, we developed T2V adapter that is inspired by [T2I-adapter](https://github.com/TencentARC/T2I-Adapter).
By pluging a lightweight adapter module to the T2V model, we can obtained generation results with more detailed control signals such as depth.

input text: `Ironman is fighting against the enemy, big fire in the background, photorealistic, 4k`
<table class="center">
  <td><img src=assets/adapter/6_GIF/input_5_randk1.gif width="170"></td>
  <td><img src=assets/adapter/6_GIF/depth_5_randk1.gif width="170"></td>
  <td><img src=assets/adapter/6_GIF/0008.gif width="170"></td>
  <td><img src=assets/adapter/6_GIF/0006.gif width="170"></td>
  <td><img src=assets/adapter/6_GIF/0004.gif width="170"></td>
  </tr>
</table >


🤗🤗🤗 We will keep updating this repo and add more features and models.


<!-- ## Gallery
### ☝️ Text-to-Video Generation
<table class="center">
  <td style="text-align:center;" width="170">Loving Vincent</td>
  <td style="text-align:center;" width="170">Frozen</td>
  <td style="text-align:center;" width="170">Your Name</td>
  <td style="text-align:center;" width="170">CoCo</td>
  <tr>
  <td><img src=assets/001_loving_vincent.gif width="170"></td>
  <td><img src=assets/002_frozen.gif width="170"></td>
  <td><img src=assets/003_your_name.gif width="170"></td>
  <td><img src=assets/004_coco.gif width="170"></td>
</tr> -->
</table >

<br>  

## 📝 Changelog
- __[2023.04.04]__: release pretrained text-to-video models and inference code
<br>

<!--  -->
## ⏳ TODO
- [ ] Huggingface demo
- [ ] Release training code for VideoLoRA
- [ ] Technical report
- [ ] More customized models

<br>  

## 🥳 Gallery of VideoLoRA Models
#### Loving Vincent Style
<table class="center">
  <!-- <td style="text-align:center;" width="50">Input Text</td> -->
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <tr>
  <td><img src=assets/lora/1_vangogh/013.gif width="170"></td>
  <td><img src=assets/lora/1_vangogh/002.gif width="170"></td>
  <td><img src=assets/lora/1_vangogh/001.gif width="170"></td>
  <td><img src=assets/lora/1_vangogh/011.gif width="170"></td>
</tr>
</table >

#### Frozen
<table class="center">
  <!-- <td style="text-align:center;" width="50">Input Text</td> -->
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <tr>
  <td><img src=assets/lora/2_frozen/001.gif width="170"></td>
  <td><img src=assets/lora/2_frozen/012.gif width="170"></td>
  <td><img src=assets/lora/2_frozen/011.gif width="170"></td>
  <td><img src=assets/lora/2_frozen/004.gif width="170"></td>
</tr>
</table >

#### Your Name
<table class="center">
  <!-- <td style="text-align:center;" width="50">Input Text</td> -->
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <tr>
  <td><img src=assets/lora/3_your_name/012.gif width="170"></td>
  <td><img src=assets/lora/3_your_name/011.gif width="170"></td>
  <td><img src=assets/lora/3_your_name/007.gif width="170"></td>
  <td><img src=assets/lora/3_your_name/004.gif width="170"></td>
</tr>
</table >

#### CoCo
TOBEDONE
<table class="center">
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <tr>
  <td><img src=assets/lora/3_your_name/007.gif width="170"></td>
  <td><img src=assets/lora/3_your_name/007.gif width="170"></td>
  <td><img src=assets/lora/3_your_name/007.gif width="170"></td>
  <td><img src=assets/lora/3_your_name/007.gif width="170"></td>
</tr>
</table >


## ⚙️ Installation


<details><summary>CLICK ME For Mannual Installation </summary>

```bash
conda create -n lvdm python=3.8.5
conda activate lvdm
pip install torch==1.12.1+cu113 torchvision==0.13.1+cu113 -f https://download.pytorch.org/whl/torch_stable.html
pip install pytorch-lightning==1.8.3 omegaconf==2.1.1 einops==0.3.0
pip install opencv-python==4.1.2.30 imageio==2.9.0 imageio-ffmpeg==0.4.2
pip install transformers==4.25.1
```  

</details>


## 🌟 Inference Text-to-Video
run `bash sample_text2video.sh` in terminal OR
<details><summary>CLICK ME For running commands </summary>


```bash
python scripts/sample_text2video.py \
    --ckpt_path $BASE_PATH \
    --config_path $CONFIG_PATH \
    --prompt $PROMPT \
    --save_dir $OUTDIR \
    --n_samples 1 \
    --batch_size 1 \
    --seed 1000
```
</details>
<br>


## 🌟 Inference VideoLoRA
run `bash sample_videolora.sh` in terminal OR
<details><summary>CLICK ME For running commands </summary>


```bash
python scripts/sample_text2video.py \
    --ckpt_path $BASE_PATH \
    --config_path $CONFIG_PATH \
    --prompt $PROMPT \
    --save_dir $OUTDIR \
    --n_samples 1 \
    --batch_size 1 \
    --seed 1000 \
    --inject_lora \
    --lora_scale 1.0 \
    --lora_trigger_word $TAG
```
</details>
<br>

### Difference LoRA scales
<table class="center">
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <td style="text-align:center;" width="170">xxx</td>
  <!-- <td style="text-align:center;" width="170">xxx</td> -->
  <tr>
  <td><img src=assets/diffscale/astronaut_riding_a_horse,_Loving_Vincent_style_000_scale0.gif width="170"></td>
  <td><img src=assets/diffscale/astronaut_riding_a_horse,_Loving_Vincent_style_000_scale0.25.gif width="170"></td>
  <td><img src=assets/diffscale/astronaut_riding_a_horse,_Loving_Vincent_style_000_scale0.5.gif width="170"></td>
  </tr>
  <td><img src=assets/diffscale/astronaut_riding_a_horse,_Loving_Vincent_style_000_scale0.75.gif width="170"></td>
  <td><img src=assets/diffscale/astronaut_riding_a_horse,_Loving_Vincent_style_000_scale1.0.gif width="170"></td>
  <td><img src=assets/diffscale/astronaut_riding_a_horse,_Loving_Vincent_style_000_scale1.5.gif width="170"></td>
</table >


## 🥳 Gallery of VideoControl

<table class="center">
  <td colspan="5" >Text Prompt: "A camel walking on the snow field, Miyazaki Hayao anime style"</td>
  </tr>
  <td><img src=assets/adapter/5_GIF/input_4_randk0.gif width="170"></td>
  <td><img src=assets/adapter/5_GIF/depth_4_randk0.gif width="170"></td>
  <td><img src=assets/adapter/5_GIF/0000.gif width="170"></td>
  <td><img src=assets/adapter/5_GIF/0008.gif width="170"></td>
  <td><img src=assets/adapter/5_GIF/0006.gif width="170"></td>
  <!-- <td><img src=assets/adapter/5_GIF/0001.gif width="170"></td> -->
  </tr>
  <td colspan="5" >Text Prompt: "Ironman playing hockey on the field, photorealistic, 4k"</td>
  </tr>
  <td><img src=assets/adapter/2_GIF/input_2_randk1.gif width="170"></td>
  <td><img src=assets/adapter/2_GIF/depth_2_randk1.gif width="170"></td>
  <td><img src=assets/adapter/2_GIF/0003.gif width="170"></td>
  <td><img src=assets/adapter/2_GIF/0004.gif width="170"></td>
  <td><img src=assets/adapter/2_GIF/0008.gif width="170"></td>
  </tr>
  
  <td colspan="5" >Text Prompt: "An ostrich walking in the desert, photorealistic, 4k"</td>
  </tr>
  <td><img src=assets/adapter/1_GIF/input_1_randk1.gif width="170"></td>
  <td><img src=assets/adapter/1_GIF/depth_1_randk1.gif width="170"></td>
  <td><img src=assets/adapter/1_GIF/0003.gif width="170"></td>
  <td><img src=assets/adapter/1_GIF/0002.gif width="170"></td>
  <td><img src=assets/adapter/1_GIF/0009.gif width="170"></td>
  </tr>
  <td colspan="5" >Text Prompt: "A car turning around on a countryside road, snowing heavily, ink wash painting"</td>
  </tr>
  <td><img src=assets/adapter/7_GIF/input_5_randk0.gif width="170"></td>
  <td><img src=assets/adapter/7_GIF/depth_5_randk0.gif width="170"></td>
  <td><img src=assets/adapter/7_GIF/0003.gif width="170"></td>
  <td><img src=assets/adapter/7_GIF/0004.gif width="170"></td>
  <td><img src=assets/adapter/7_GIF/0009.gif width="170"></td>
  </tr>
  
</table >



## 📋 Techinical Report
⏳⏳⏳ Comming soon. We are still working on it.💪
<br>

<!-- ## 💗 Related Works -->
## 📭 Contact
If your have any comments or questions, feel free to contact [Yingqing He](yhebm@connect.ust.hk), [Haoxin Chen](jszxchx@126.com) or [Menghan Xia](menghanxyz@gmail.com).

## 📢 Disclaimer
We develop this repository for RESEARCH purposes, so it can only be used for personal/research/non-commercial purposes.
