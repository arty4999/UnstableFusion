# UnstableFusion but using a different model
A Stable Diffusion desktop frontend with inpainting, img2img and more!

https://user-images.githubusercontent.com/6392321/191858568-0550f52d-e89c-4b37-aa07-23df605b4807.mp4

## How to run locally?
1. Install the dependencies (for example using `pip`). The dependencies include :
* `PyQt5`, `numpy`, `pytorch`, `Pillow`, `opencv-python`, `requests`, `flask`, `diffusers`, `transformers`, `protobuf`

Note that if you want to run StableDiffusion on Windows locally, use requirements-localgpu-win64.txt
```
pip install -r requirements-localgpu-win64.txt
```

Note: On linux, if you encounter `Could not load the Qt platform plugin "xcb"` error, run this:
```
pip uninstall opencv-python     (solve a xcb compatibility issue)
pip install opencv-python-headless     (solve a xcb compatibility issue)
```

2. Create a huggingface account and an [access token](https://huggingface.co/settings/tokens), if you haven't done so already.
Request access to the StableDiffusion model at [CompVis/stable-diffusion-v1-4](https://huggingface.co/CompVis/stable-diffusion-v1-4).

3. Clone this repository and run `python unstablefusion.py`


## How to use?

* You can select a box by clicking on the screen. All of your operations will be limited to this box. You can resize the box using mouse wheel.
* You can erase the selected box by right clicking, or paint into it by middle clicking (the paint color can be configured using `Select Color` button)
* To generate an image, select the destination box, enter the prompt in the `prompt` text field and press the `Generate button` (inpainting and reimagining work similarly)
* You can undo/redo by pressing the `undo`/`redo` button or pressing `Control+Z`/`Control+Shift+Z` on your keyboard. In fact most other functions are bound to keys as well (you can configure them in `keys.json` file)
* `Increase Size`/`Decrease Size` buttons adjust the size of the image by adding/removing extra space in the margins (and not by scaling, this is useful when you want to add more detail around an image)
* You can open a scratchpad by pressing `Show Scratchpad` button. This window is capable of doing everything the main window can (using keyboard shortcuts only). The selected box in scratch pad will be mirrored and scaled into the selected box in the main window.
This is useful when trying to import another generated/local image into the main image.
