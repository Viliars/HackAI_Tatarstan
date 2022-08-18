# HackAI_Tatarstan
Решение Михаил Притугина

```git clone --recurse-submodules https://github.com/Viliars/HackAI_Tatarstan```

Все команды из инструкции выполняются внутри папки yolo7.

---
## How to use my model
1) Скачать мою модель по [ссылке](https://disk.yandex.ru/d/oH3dAowCKgrl9g)

2) Использовать команду:

```python3 detect.py --weights hack_best_model.pt --conf <conf> --img-size 1280 --source <img>```

---
## How to Test
1) Подготовить тестовые данные в формате Yolo

2) Запустить тестирование командой:

```python3 test.py --data data/dataset.yaml --img 1280 --batch 32 --conf 0.001 --iou 0.65 --device 0 --weights best.pt --name yolov7-e6e-hack```

3) Использовать `make_solution.ipynb` для формирования решения после тестирования

---
## How to Train
1) Подготовить данные в формате Yolo

2) Скачать предобученные веса [yolov7-e6e_training.pt](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7-e6e_training.pt)

3) Обучить модель в режиме transfer learning командой:

```python3 train_aux.py --workers 2 --device 0 --batch-size 4 --data data/dataset.yaml --img 1280 1280 --cfg cfg/training/yolov7-e6e-hack.yaml --weights 'yolov7-e6e_training.pt' --name yolov7-e6e-hack --hyp data/hyp.scratch.custom.yaml```

