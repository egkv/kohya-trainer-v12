# Kohya Trainer V12
![GitHub Repo stars](https://img.shields.io/github/stars/Linaqruf/kohya-trainer?style=social)</a> <img src="https://visitor-badge.glitch.me/badge?page_id=linaqruf.kohya-repo-trainer" alt="visitor badge"/>

### Github Repository for [kohya-ss/sd-scripts](https://github.com/kohya-ss/sd-scripts) colab notebook implementation
| Notebook Name | Description | Link |
| --- | --- | --- |
| [Kohya LoRA Dreambooth](https://github.com/Linaqruf/kohya-trainer/blob/main/kohya-LoRA-dreambooth.ipynb) | LoRA Training (Dreambooth method) | [![](https://img.shields.io/static/v1?message=Open%20in%20Colab&logo=googlecolab&labelColor=5c5c5c&color=0f80c1&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/kohya-trainer/blob/main/kohya-LoRA-dreambooth.ipynb) |
| [Kohya LoRA Fine-Tuning](https://github.com/Linaqruf/kohya-trainer/blob/main/kohya-LoRA-finetuner.ipynb) | LoRA Training (Fine-tune method) | [![](https://img.shields.io/static/v1?message=Open%20in%20Colab&logo=googlecolab&labelColor=5c5c5c&color=0f80c1&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/kohya-trainer/blob/main/kohya-LoRA-finetuner.ipynb) |
| [Kohya Trainer](https://github.com/Linaqruf/kohya-trainer/blob/main/kohya-trainer.ipynb) | Native Training | [![](https://img.shields.io/static/v1?message=Open%20in%20Colab&logo=googlecolab&labelColor=5c5c5c&color=0f80c1&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/kohya-trainer/blob/main/kohya-trainer.ipynb) |
| [Kohya Dreambooth](https://github.com/Linaqruf/kohya-trainer/blob/main/kohya-dreambooth.ipynb) | Dreambooth Training | [![](https://img.shields.io/static/v1?message=Open%20in%20Colab&logo=googlecolab&labelColor=5c5c5c&color=0f80c1&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/kohya-trainer/blob/main/kohya-dreambooth.ipynb) |
| Kohya Textual Inversion  | Textual Inversion Training | SOON |

## Become a supporter
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/linaqruf)
<a href="https://saweria.co/linaqruf"><img alt="Saweria" src="https://img.shields.io/badge/Saweria-7B3F00?style=for-the-badge&logo=ko-fi&logoColor=white"/></a>

## Updates
##### v12 (02/05):
__What Changes?__
- Refactored the 4 notebooks (again)
- Restored the `--learning_rate` function in `kohya-LoRA-dreambooth.ipynb` and `kohya-LoRA-finetuner.ipynb` [#52](https://github.com/Linaqruf/kohya-trainer/issues/52)
- Fixed the cell for inputting custom tags [#48](https://github.com/Linaqruf/kohya-trainer/issues/48) and added the `--keep_tokens` function to prevent custom tags from being shuffled.
- Added a cell to check if all LoRA modules have been trained properly.
- Added descriptions for each notebook and links to the relevant notebooks to prevent "training on the wrong notebook" from happening again.
- Added a cell to check the metadata in the LoRA model.
- Added a cell to change the transparent background in the train data.
- Added a cell to upscale the train data using R-ESRGAN
- Divided the Data Annotation section into two cells:
  - Removed BLIP and replaced it with `Microsoft/GIT` as the auto-captioning for natural language (git-large-textcaps is the default model).
  - Updated the Waifu Diffusion 1.4 Tagger to version v2 (SwinV2 is the default model).
    - The user can adjust the threshold for general tags. It is recommended to set the threshold higher (e.g. `0.85`) if you are training on objects or characters, and lower the threshold (e.g. `0.35`) for training on general, style, or environment.
    - The user can choose from three available models.
- Added a field for uploading to the Huggingface organization account.
- Added the `--min_bucket_reso=320` and `--max_bucket_reso=1280` functions for training resolutions above 512 (e.g. 640 and 768), Thanks Trauter!

Training script Changes([kohya_ss](https://github.com/kohya-ss))
- Please read [Updates 3 Feb. 2023, 2023/2/3](https://github.com/kohya-ss/sd-scripts/blob/fb230aff1b434a21fc679e4902ac1ff5aab1d76b/README.md) for recent updates.

## Useful Links
- Official repository : [kohya-ss/sd-scripts](https://github.com/kohya-ss/sd-scripts)
- Gradio Web UI Implementation : [bmaltais/kohya_ss](https://github.com/bmaltais/kohya_ss)
- Automatic1111 Web UI extensions : [dPn08/kohya-sd-scripts-webui](https://github.com/ddPn08/kohya-sd-scripts-webui)

## Overview
- Fine tuning of Stable Diffusion's U-Net using Diffusers
- Addressing improvements from the NovelAI article, such as using the output of the penultimate layer of CLIP (Text Encoder) instead of the last layer and learning at non-square resolutions with aspect ratio bucketing.
- Extends token length from 75 to 225 and offers automatic caption and automatic tagging with BLIP, DeepDanbooru, and WD14Tagger
- Supports hypernetwork learning and is compatible with Stable Diffusion v2.0 (base and 768/v)
- By default, does not train Text Encoder for fine tuning of the entire model, but option to train Text Encoder is available.
- Ability to make learning even more flexible than with DreamBooth by preparing a certain number of images (several hundred or more seems to be desirable).

## Original post for each dedicated script:
- [gen_img_diffusers](https://note.com/kohya_ss/n/n2693183a798e)
- [merge_vae](https://note.com/kohya_ss/n/nf5893a2e719c)
- [convert_diffusers20_original_sd](https://note.com/kohya_ss/n/n374f316fe4ad)
- [detect_face_rotate](https://note.com/kohya_ss/n/nad3bce9a3622)
- [diffusers_fine_tuning](https://note.com/kohya_ss/n/nbf7ce8d80f29)
- [train_db_fixed](https://note.com/kohya_ss/n/nee3ed1649fb6)
- [merge_block_weighted](https://note.com/kohya_ss/n/n9a485a066d5b)

## Change Logs:

#### 2023

##### v11.5 (31/01):
__What Changes?__
- Refactored the 4 notebooks, removing unhelpful comments and making some code more efficient.
- Removed the `download and generate` regularization images function from `kohya-dreambooth.ipynb` and `kohya-LoRA-dreambooth.ipynb`.
- Simplified cells to create the `train_folder_directory` and `reg_folder_directory` folders in `kohya-dreambooth.ipynb` and `kohya-LoRA-dreambooth.ipynb`.
- Improved the download link function from outside `huggingface` using `aria2c`.
- Set `Anything V3.1` which has been improved CLIP and VAE models as the default pretrained model.
- Fixed the `parameter table` and created the remaining tables for the dreambooth notebooks.
- Added `network_alpha` as a supporting hyperparameter for `network_dim` in the LoRA notebook.
- Added the `lr_scheduler_num_cycles` function for `cosine_with_restarts` and the `lr_scheduler_power` function for `polynomial`.
- Removed the global syntax `--learning_rate` in each LoRA notebook because `unet_lr` and `text_encoder_lr` are already available.
- Fixed the `upload to hf_hub` cell function.

Training script Changes([kohya_ss](https://github.com/kohya-ss))
- Please read [release version 0.4.0](https://github.com/kohya-ss/sd-scripts/releases/tag/v0.4.0) for recent updates.

##### v11 (19/01):
- Reformat notebook, 
  - Added `%store` IPython magic command to store important variable
  - Now you can change the active directory only by editing directory path in `1.1. Clone Kohya Trainer` cell, and save it using `%store` magic command.
  - Deleted `unzip` cell and adjust `download zip` cell to do auto unzip as well if it detect path startswith /content/
  - Added `--flip_aug` to Buckets and Latents cell.
  - Added `--output_name (your-project)` cell to save Trained Model with custom nam.
  - Added ability to auto compress `train_data_dir`, `last-state` and `training_logs` before upload them to Huggingface
- Added `colab_ram_patch` as temporary fix for newest version of Colab after Ubuntu update to `load Stable Diffusion model in GPU instead of RAM`

Training script Changes([kohya_ss](https://github.com/kohya-ss))
- Please read [release version 0.3.0](https://github.com/kohya-ss/sd-scripts/releases/tag/v0.3.0) for recent updates.

##### v10 (02/01) separate release

- Added a function to automatically download the BLIP weight in `make_caption.py`
- Added functions for LoRA training and generation
- Fixed issue where text encoder training was not stopped
- Fixed conversion error for v1 Diffusers->ckpt in `convert_diffusers20_original_sd.py`
- Fixed npz file name for images with dots in `prepare_buckets_latents.py`

Colab UI changes:
- Integrated the repository's format with kohya-ss/sd-script to facilitate merging
- You can no longer choose older script versions in the clone cell because the new format does not support it
- The requirements for both blip and wd tagger have been merged into one requirements.txt file
- The blip cell has been simplified because `make_caption.py` will now automatically download the BLIP weight, as will the wd tagger
- A list of sdv2 models has been added to the "download pretrained model" cell
- The "v2" option has been added to the bucketing and training cells
- An image generation cell using `gen_img_diffusers.py` has been added below the training cell

#### 2022
##### v9 (17/12):
- Added the `save_model_as` option to `fine_tune.py`, which allows you to save the model in any format.
- Added the `keep_tokens` option to `fine_tune.py`, which allows you to fix the first n tokens of the caption and not shuffle them.
- Added support for left-right flipping augmentation in `prepare_buckets_latents.py` and `fine_tune.py` with the `flip_aug` option.

##### v8 (13/12):
- Added support for training with fp16 gradients (experimental feature). This allows training with 8GB VRAM on SD1.x. See "Training with fp16 gradients (experimental feature)" for details.
- Updated WD14Tagger script to automatically download weights.

##### v7 (7/12):
- Requires Diffusers 0.10.2 (0.10.0 or later will work, but there are reported issues with 0.10.0 so we recommend using 0.10.2). To update, run `pip install -U diffusers[torch]==0.10.2` in your virtual environment.
- Added support for Diffusers 0.10 (uses code in Diffusers for `v-parameterization` training and also supports `safetensors`).
- Added support for accelerate 0.15.0.
- Added support for multiple teacher data folders. For caption and tag preprocessing, use the `--full_path` option. The arguments for the cleaning script have also changed, see "Caption and Tag Preprocessing" for details.

##### v6 (6/12):
- Temporary fix for an error when saving in the .safetensors format with some models. If you experienced this error with v5, please try v6.

##### v5 (5/12):
- Added support for the .safetensors format. Install safetensors with `pip install safetensors` and specify the `use_safetensors` option when saving.
- Added the `log_prefix` option.
- The cleaning script can now be used even when one of the captions or tags is missing.

##### v4 (14/12):
- The script name has changed to fine_tune.py.
- Added the option `--train_text_encoder` to train the Text Encoder.
- Added the option `--save_precision` to specify the data format of the saved checkpoint. Can be selected from float, fp16, or bf16.
- Added the option `--save_state` to save the training state, including the optimizer. Can be resumed with the `--resume` option.

##### v3 (29/11):
- Requires Diffusers 0.9.0. To update it, run `pip install -U diffusers[torch]==0.9.0`.
- Supports Stable Diffusion v2.0. Use the `--v2` option when training (and when pre-acquiring latents). If you are using 768-v-ema.ckpt or stable-diffusion-2 instead of stable-diffusion-v2-base, also use the `--v_parameterization` option when training.
- Added options to specify the minimum and maximum resolutions of the bucket when pre-acquiring latents.
- Modified the loss calculation formula.
- Added options for the learning rate scheduler.
- Added support for downloading Diffusers models directly from Hugging Face and for saving during training.
- The cleaning script can now be used even when only one of the captions or tags is missing.
- Added options for the learning rate scheduler.

##### v2 (23/11):
- Implemented Waifu Diffusion 1.4 Tagger for alternative DeepDanbooru for auto-tagging
- Added a tagging script using WD14Tagger.
- Fixed a bug that caused data to be shuffled twice.
- Corrected spelling mistakes in the options for each script.

## Conclusion
> While Stable Diffusion fine tuning is typically based on CompVis, using Diffusers as a base allows for efficient and fast fine tuning with less memory usage. We have also added support for the features proposed by Novel AI, so we hope this article will be useful for those who want to fine tune their models.

 — kohya_ss 

## Credit
[Kohya](https://twitter.com/kohya_ss) | [Lopho](https://github.com/lopho/stable-diffusion-prune) for prune script | Just for my part




