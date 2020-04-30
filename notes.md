### Fixes made in Windows 10 to get things up and running

1) I had to copy-paste gpt2 conda environment folder to new 'dain' folder (D:\anaconda3\envs)
2) conda activate gain 
3) change scipy version to the older one: conda install scipy=1.2.0


### Training / fine-tuning 
TODO: Make sure it's needed. My small experiment with interpolating Lapenko video 
based on pre-trained and not optimized model gives some glitchy frames but nevertheless 
the overall results are pretty satisfying.
 

### Interpolating
The original script ```colab_interpolate.py``` has a bug: interpolated images are 3 pixels wide.
I've fixed it, so now when the script is finished, in the output folder interpolated images have are even-numbered.
For example: if you have two source images ```0001.png``` and ```0002.png```, in the output folder you will have 
```0001.png```, ```0002.png```, ```0003.png``` where ```0003.png``` is the renamed original ```0002.png``` 
and the resulting ```0002.png``` is the interpolation of two originals. 

After the run of the script, the number of resulting images is doubled compared to the original, 
which means x2 increase of FPS. 


```
python colab_interpolate.py --frame_input_dir <SRC_DIR> --frame_output_dir <DST_DIR> --time_step 0.5 --end_frame <LAST FRAME NUMBER - 1> 2>error.log
```

