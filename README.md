# amax
## install packages
```conda install pytorch=1.7.1 torchvision cudatoolkit=11.0 -c pytorch```

it seems that only pytorch 1.13 will be `cpu` version.

In amax A6000, we cannot install cuda 10.2, this will make it incompatible with `Task2_point_generation`

## Comparasion Experiments

In `/mnt/ChillDisk/personal_data/lizc/2023/exp`, the input data in `dataloader` is \[radar_depth, rgb\]. The image's shape and the gt_depth's shape are both `512x1024`.

Thus, the dataloader donot need modify. \(The `dataloader` in `autodl`, image's shape is `512x1024`, gt_depth's shape is `256x512`, need to modify the `dataloader` code, specifically.\)

The comparasion experiments we selected are: `Sparse depth completion` and `sparse to dense`.

### Select depth pixel location

### Transform depth map to points
