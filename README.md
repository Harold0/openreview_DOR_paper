# Quick Start
Temporary resp for reviewers.



https://user-images.githubusercontent.com/24803435/170527084-3f1573ef-5c63-4342-98c4-1335706e4a6b.mp4



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



