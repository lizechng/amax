# amax
## install packages
```conda install pytorch=1.7.1 torchvision cudatoolkit=11.0 -c pytorch```

it seems that only pytorch 1.13 will be `cpu` version.

In amax A6000, we cannot install cuda 10.2, this will make it incompatible with `Task2_point_generation`

\(Thus, we need to retrain the PG4RNet, or move files to TITANXP in `autodl`, `torch 1.6.0` `cuda 10.2`\)

## Comparasion Experiments

In `/mnt/ChillDisk/personal_data/lizc/2023/exp`, the input data in `dataloader` is \[radar_depth, rgb\]. The image's shape and the gt_depth's shape are both `512x1024`.

Thus, the dataloader donot need modify. \(The `dataloader` in `autodl`, image's shape is `512x1024`, gt_depth's shape is `256x512`, need to modify the `dataloader` code, specifically.\)

Why the `Dset2` only have 152 training samples and 148 validate samples?

- `Dset` is the total samples, `Dset2` is the mini dataset, `Dset2_mini` is only with just one sample. 

- The experiments training process, selected `Dset2` as the training data.

- Still select the landmark_data? No.

Retrain the experiment model and PG4RNet.

The comparasion experiments we selected are: `Sparse depth completion` and `sparse to dense`.

### Select depth pixel location

### Transform depth map to points
