# Emotion-Object-Detection


ubuntu16.04, cuda9.0, cudnn7.0환경에서 진행.\n
해당 프로그램은 Restful-api를 사용하여 파일업로드 및 결과값을 받아볼 수 있는 서버 역할 프로그램.\n
모바일 / 웹 어떤 서비스든지 Rest 방식으로 접근하면 서비스 이용가능.

flask 개념은 미리 숙지해 둘 것.

1. 실행을 위해 해당 git clone하여 다운로드
```
git clone https://github.com/Lo0uis/Emotion-Object-Detection
```

2. 압축풀기
```
unzip darknet.zip
unzip flask-rest.zip
```

2. flask폴더로 이동
```
cd flask-rest
```

3. 파일 실행 
```
python3 flask_upload.py
```

(아마도 설치되지 않은 부분이 많아 실행이 안될 것.)

설치가 전부 완료되었는데도 실행이 안된다면, ```flask_upload.py``` 내부 파일 경로를 수정해볼 것.

****
##Yolo 설치

yolo v3 설치는 https://pjreddie.com/darknet/yolo/ 참고.

```
cd darknet
make
```

이때, make 하기 전에 Makefile을 다음과 같이 수정하면 gpu를 사용할 수 있다.

```
GPU=1
CUDNN=1
CUDNN_HALF=0
OPENCV=1
AVX=0
OPENMP=0
LIBSO=0
```

opencv는 https://webnautes.tistory.com/1030 사이트를 참고하여 설치 가능.

object detection의 weight 와 emotion detection의 weight는 다음과 같이 설치 가능.
```
wget https://pjreddie.com/media/files/yolov3.weights
wget https://www.dropbox.com/s/byi68nnms86onx3/yolov3_emotion.weights
```

다시 처음으로 돌아가 실행하면 정상 작동.
