# YOLOv4-Based-Small-Object-Detection

--------------------------------------------------------------------
  * YOLO v4 : https://arxiv.org/abs/2004.10934
  * RARE : https://arxiv.org/abs/1603.03915
  * 건설 설계 도면 내 자체 데이터 셋을 구축한 뒤 YOLOv4와 OCR RARE를 통해 객체 검출 및 문자 인식 파이프라인을 설계하여 철강재료를 적산할 수 있는 기술 개발
  * 플랫폼 및 사용 기술 : Anaconda, Pytorch, OpenCV, Numpy, openpyxl
  * 자체 Custom 데이터 셋 구축
    * 객체 검출 셋
        * train : 761장, val : 26장, test : 80장
    * 문자 인식 셋
        * train : 1만장, val : 3천장, test : 4천장
  * YOLOv4, OCR RARE Network 분석
  * 데이터 복제 증강 기법 및 공간 집중 모듈을 활용한 큰 도면 내 소형 객체 검출 성능 향상
  * 객체 검출 및 문자 인식 파이프라인 설계


## 철강자재 검출 및 문자인식 전체 과정
![image](https://user-images.githubusercontent.com/61686244/136881085-c6d162b0-5543-4881-a5da-30a1a2e08e91.png)
 
#### (1) DWG to PNG
<img src=https://user-images.githubusercontent.com/61686244/140644084-5d54b60f-ade8-44b0-b9b3-9e3cc5544d55.png width="700" height="350"/>


#### (2) Dataset-Detection
<img src=https://user-images.githubusercontent.com/61686244/140644095-83512172-625c-4eee-aaa4-9686b38754aa.png width="700" height="350"/>

#### (3) Dataset-Recognition
<img src=https://user-images.githubusercontent.com/61686244/140644111-cd71cba8-5b9e-46fd-8bb9-fedb88c0b3be.png width="700" height="350"/>

#### (4) Train-YOLV4(Detection)
<img src=https://user-images.githubusercontent.com/61686244/140644127-ed501c70-55d3-4336-b1ff-95ecf1be7e62.png width="700" height="350"/>

#### (5) Train-RARE(Recognition)
<img src=https://user-images.githubusercontent.com/61686244/140644142-fe7c2be5-905b-4391-9a7e-3058d977a17a.png width="700" height="350"/>

#### Detection Result
<img src=https://user-images.githubusercontent.com/61686244/140644179-e077828b-6822-48d6-af33-7111086e0280.png width="700" height="350"/>

#### Recognition 전 전처리
<img src=https://user-images.githubusercontent.com/61686244/140644237-aec23afc-1ec7-4cf6-8f67-443b550c28aa.png width="500" height="250"/>

#### Recognition save 
<img src=https://user-images.githubusercontent.com/61686244/140644254-5a2bf368-bf4d-419f-bd3d-1fb8a6206421.png width="700" height="350"/>

### Train
<pre>
<code>
$ python train_oversampling.py --single-cls --device '원하는 gpu' (복제augmentation추가원하면 입력->"--srmix --srimx-alpha '원하는횟수' ") 
</code>
</pre>

### Test
<pre>
<code>
$ python detect_edit.py  --device '원하는 gpu' --weights '원하는 학습 pt파일' --save-txt
</code>
</pre>

