# MAL
MAL for cvpr765


## install
Get into MAL root folder.
1. Install conda env by `conda env create -f environment.yaml` and activate it by 'conda activate MAL'.
2. Copy https://github.com/facebookresearch/maskrcnn-benchmark/tree/master/maskrcnn_benchmark to this repository.
3. Build maskrcnn_benchmark by run `python setup.py build develop`

## inference for an image
1. Go to `./demo`
2. Run `python image_demo.py`. You can use your own image and change the image path in image_demo.py

## test on COCO dataset
Get into MAL root folder.
For test-dev set, run
`python python -m torch.distributed.launch --nproc_per_node=8 tools/test_net.py --config-file ./config/MAL_X-101-FPN_e2e.yaml MODEL.WEIGHT ./output/models/model_0180000.pth DATASETS.TEST "('coco_test-dev',)"`

For val set, run
`python python -m torch.distributed.launch --nproc_per_node=8 tools/test_net.py --config-file ./config/MAL_X-101-FPN_e2e.yaml MODEL.WEIGHT ./output/models/model_0180000.pth`

## experimental result
mAP = 47.0 on test-dev

## to do
clean the training code
