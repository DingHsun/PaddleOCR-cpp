# PaddleOCR C++ 使用 opencv 和 onnxruntime 運行
PaddleOCR on C++ using onnxruntime and opencv.  
本專案使用C++實作開發，onnxruntime實現PaddleOCR，可運行x64版本。

提供兩種OCR功能
1. 全圖識別(文字位置)與辨識(文字內容) 
2. 選擇ROI範圍進行辨識
## C++ Packages
* onnxruntime-win-x64-gpu-1.21.0 [ https://github.com/microsoft/onnxruntime/releases ]
* opencv 4.5.0 windows [ https://opencv.org/releases/ ]

放置路徑  
./packages  
    ├─ onnxruntime-win-x64-gpu-1.21.0  
    └─ opencv

## 模型選擇 (轉 .onnx)
PP-OCR系列模型列表

[https://github.com/PaddlePaddle/PaddleOCR/blob/release/2.7/doc/doc_ch/models_list.md](http://www.paddleocr.ai/latest/version3.x/module_usage/module_overview.html)

* python 3.10.10  
* pip install paddle2onnx-2.0.2rc3  
* 下載推理模型並解壓縮  
* 執行以下指令將model轉onnx並放置到下列路徑(放置路徑 ./weights/)，自行修改路徑  
* C:\Python31010-OCR-2onnx\Scripts\paddle2onnx.exe --model_dir "C:\Users\Users\Downloads\en_PP-OCRv5_mobile_rec_infer\en_PP-OCRv5_mobile_rec_infer" --model_filename inference.json --params_filename inference.pdiparams --save_file "C:\Users\Users\Downloads\en_PP-OCRv5_mobile_rec_infer\en_PP-OCRv5_mobile_rec_infer\model.onnx"

修改程式  
* PaddleOCR-cpp.cpp -
* TextDetector detect_model("det onnx model path");
* TextRecognizer rec_model("rec onnx model path", "rec dict.txt path");


## 文字辨識文本下載
範例：PP-OCRv6_medium_rec https://github.com/PaddlePaddle/PaddleOCR/blob/main/configs/rec/PP-OCRv6/PP-OCRv6_medium_rec.yml  
1. 下載推理模型並執行轉 .onnx 步驟
<img width="1084" height="692" alt="image" src="https://github.com/user-attachments/assets/b5f3e947-4b70-4580-9031-3656b2e57369" />

2. 尋找 .yml 檔案中的 character_dict_path 下載 recognition 需要的 dict.txt  
<img width="1113" height="766" alt="image" src="https://github.com/user-attachments/assets/a80119e7-5dca-47a5-80e2-ff2afa1f37a8" />
