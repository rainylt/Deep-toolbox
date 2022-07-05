# Visualizing the Effective Receptive Field

We have released our script to visualize and analyze the Effective Receptive Field (ERF). For example, to automatically download the ResNet-101 from torchvision and obtain the aggregated contribution score matrix,
```
python erf/visualize_erf.py --model resnet101 --data_path /path/to/imagenet-1k --save_path resnet101_erf_matrix.npy
```
Then calculate the high-contribution area ratio and visualize the ERF by
```
python erf/analyze_erf.py --source resnet101_erf_matrix.npy --heatmap_save resnet101_heatmap.png
```
Note this plotting script works with matplotlib 3.3. If you use a higher version of matplotlib, see the comments [here](https://github.com/DingXiaoH/RepLKNet-pytorch/blob/main/erf/analyze_erf.py#L40).

To visualize your own model, first define a model that outputs the last feature map rather than the logits (following [this example](https://github.com/DingXiaoH/RepLKNet-pytorch/blob/main/erf/resnet_for_erf.py#L25)), add the code for building model and loading weights [here](https://github.com/DingXiaoH/RepLKNet-pytorch/blob/main/erf/visualize_erf.py#L74), then
```
python erf/visualize_erf.py --model your_model --weights /path/to/your/weights --data_path /path/to/imagenet-1k --save_path your_model_erf_matrix.npy
```

# Reference
* [RepLKNet](https://github.com/DingXiaoH/RepLKNet-pytorch)
