# PaddleOCR C++ 使用 opencv 和 onnxruntime 運行
PaddleOCR on C++ using onnxruntime and opencv.  
本專案使用C++實作開發，onnxruntime實現PaddleOCR，可運行x64和x86版本。  

提供兩種OCR功能
1. 全圖識別(文字位置)與辨識(文字內容) 
2. 選擇ROI範圍進行辨識
## Packages
* Microsoft.ML.OnnxRuntime.1.12.1
* Microsoft.ML.OnnxRuntime.Gpu.1.12.1
* opencv 4.5.0
* OpencvX86 4.4.0

放置路徑README.md同目錄下  
https://drive.google.com/file/d/1t0dXe50Z05Vv6ja6cywRnbrGPFrQ51dD/view?usp=sharing

## 模型選擇
PP-OCR系列模型列表

https://github.com/PaddlePaddle/PaddleOCR/blob/release/2.7/doc/doc_ch/models_list.md

下載後至 https://github.com/PaddlePaddle/Paddle2ONNX 執行model轉onnx並放置到下列路徑(放置路徑 ./weights/)

修改程式
* text_det.cpp - string model_path = your_model.onnx
* text_rec.cpp - string model_path = your_model.onnx
* text_angle_cls.cpp - string model_path = your_model.onnx

## 文字辨識文本下載
xxx.txt放置main.cpp同目錄下。
範例：中文識別模型ch_PP-OCRv4_rec
![tempsnip](https://github.com/DingHsun/PaddleOCR-cpp/assets/110473288/e2c09df1-882f-4458-9bff-f5cadcd01682) 
![tempsnip1](https://github.com/DingHsun/PaddleOCR-cpp/assets/110473288/a81544da-11fe-4887-8e9c-9cb063826a1a)
