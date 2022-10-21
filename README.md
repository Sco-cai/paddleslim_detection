# paddleslim_detection
修改了原来的paddleslim_develop的paddle_inference_eval.py，使得原来不能用于image_file的代码能用来预测
# 示例：
python paddle_inference_eval.py \
      --model_path=models/ppyoloe_crn_l_300e_coco_quant \
      --reader_config=configs/yoloe_reader.yml \
      --use_trt=True \
      --precision=int8
      
      # 其他参数：
      参数名	含义
# model_path	inference 模型文件所在目录，该目录下需要有文件 model.pdmodel 和 model.pdiparams 两个文件
# reader_config	eval时模型reader的配置文件路径
# image_file	如果只测试单张图片效果，直接根据image_file指定图片路径
# device	使用GPU或者CPU预测，可选CPU/GPU
# use_trt	是否使用 TesorRT 预测引擎
# use_mkldnn	是否启用MKL-DNN加速库，注意use_mkldnn与use_gpu同时为True时，将忽略enable_mkldnn，而使用GPU预测
# cpu_threads	CPU预测时，使用CPU线程数量，默认10
# precision	预测精度，包括fp32/fp16/int8
