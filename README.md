# Stable Diffusion Save N before last image 

A custom extension for [AUTOMATIC1111/stable-diffusion-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui) that implements saving N-X images.

Overtrained models and/or overfitting by sampling algorithms can cause the output image to look worse compared to the N-1 or N-2 result, 
this extention works around that by allowing you to save N-X results.

Note that N-X is not the same is doing less steps. So if steps==20 will give a bad result, steps==19 will not look better.
Also steps==20 does not mean the sampler is actually going to do 20 steps, some algorithms will bail out earlier if the result is considered complete.

So want this script will do is keep track of the last N (specified by you) images and save it once the final step is done.

<img src="images/extension.jpg"/>

## Installation

The extension can be installed directly from within the **Extensions** tab within the Webui.

You can also install it manually by running the following command from within the webui directory:

	git clone https://github.com/janwilmans/sd_savvy_images/ extensions/sd_savvy_images


## Limitations
Does not work with DDIM and PLMS

## Output

Once the image generation is completed, the N-X image(s) will be saved under \outputs\(*txt2img or img2img*)-images\savvy directory.

Please be aware that **Image creation progress preview mode** in the webui's settings affects how and especially at what size the intermediate images are created.
