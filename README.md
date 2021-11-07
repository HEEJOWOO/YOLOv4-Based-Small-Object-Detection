# YOLOv4-Based-Small-Object-Detection

--------------------------------------------------------------------
  * YOLO v4 : https://arxiv.org/abs/2004.10934
  * RARE : https://arxiv.org/abs/1603.03915
## 큰 도면 내 소형 객체인 철강자재 검출 및 인식

## 철강자재 검출 및 문자인식 전체 과정
![image](https://user-images.githubusercontent.com/61686244/136881085-c6d162b0-5543-4881-a5da-30a1a2e08e91.png)
 
#### (1) DWG to PNG
![image](https://user-images.githubusercontent.com/61686244/140644084-5d54b60f-ade8-44b0-b9b3-9e3cc5544d55.png){: width="350" height="350"}

#### (2) Dataset-Detection
![image](https://user-images.githubusercontent.com/61686244/140644095-83512172-625c-4eee-aaa4-9686b38754aa.png)

#### (3) Dataset-Recognition
![image](https://user-images.githubusercontent.com/61686244/140644111-cd71cba8-5b9e-46fd-8bb9-fedb88c0b3be.png)

#### (4) Train-YOLV4(Detection)
![image](https://user-images.githubusercontent.com/61686244/140644127-ed501c70-55d3-4336-b1ff-95ecf1be7e62.png)

#### (5) Train-RARE(Recognition)
![image](https://user-images.githubusercontent.com/61686244/140644142-fe7c2be5-905b-4391-9a7e-3058d977a17a.png)

#### Detection Result
![image](https://user-images.githubusercontent.com/61686244/140644179-e077828b-6822-48d6-af33-7111086e0280.png)

#### Recognition 전 전처리
![image](https://user-images.githubusercontent.com/61686244/140644237-aec23afc-1ec7-4cf6-8f67-443b550c28aa.png)

#### Recognition save 
![image](https://user-images.githubusercontent.com/61686244/140644254-5a2bf368-bf4d-419f-bd3d-1fb8a6206421.png)

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

