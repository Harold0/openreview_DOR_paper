# Quick Start
Temporary resp for reviewers.



## 0. dependency
We use docker to solve dependency: 
[SetupDocker](./SetupDocker.md)

Please read SetupDocker.md, then set up the container using:
```bash
$ docker run -itd   --name  hmp-$USER \
--net host \
--gpus all \
--shm-size=16G \
fureplaceanonymous/hmp:latest
```

## 1. testing
```
git pull && python main.py --cfg ZHECKPOINT/adca-demo/test.json
git pull && python main.py --cfg ZHECKPOINT/basic-ma-40-demo/test.json
```
When the testing starts, open revealed url for monitoring. The front end is done by JavaScript and ThreeJS.
```
--------------------------------
JS visualizer online: http://172.18.116.150:aRandomPort
JS visualizer online (localhost): http://localhost:aRandomPort
--------------------------------
```



https://user-images.githubusercontent.com/24803435/170528233-0303608c-a12b-43bf-a34e-395fcb5c5a06.mp4

https://user-images.githubusercontent.com/24803435/171123157-01b3c73d-8af9-401a-8c89-c8a7c9f633bc.mp4


https://user-images.githubusercontent.com/24803435/170527084-3f1573ef-5c63-4342-98c4-1335706e4a6b.mp4

https://user-images.githubusercontent.com/24803435/170528239-a9152d03-8eb0-45a8-a9e1-bef57baec13e.mp4

https://user-images.githubusercontent.com/24803435/170528256-e5cf430f-26de-474a-b23f-71dc6e66bb8f.mp4







## 2. training
```
git pull && python main.py --cfg ZHECKPOINT/adca-demo/train.json
git pull && python main.py --cfg ZHECKPOINT/basic-ma-40-demo/train.json
```

## 3. running qmix

- extract ThirdParty/pymarl2forqmix.zip into "/home/fureplaceanonymous/pymarl2/pymarl2src".
- make sure the main.py of pymarl2 can be find in "/home/fureplaceanonymous/pymarl2/pymarl2src/main.py"
- run 
```
git pull && python main.py --cfg run_qmix_basicma.jsonc
```



