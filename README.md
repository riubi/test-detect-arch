# Анализ архитектуры детекции: Deformable DETR

Ruslan Papina, группа М25-555

Домашнее задание: разбор Deformable DETR (ICLR 2021) и запуск pretrained-модели на 15 картинках.

Отчёт: [report.pdf](report.pdf), код: [detection.ipynb](detection.ipynb)

## Запуск

```
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute --inplace detection.ipynb
python make_report.py
```

## Ссылки

- статья: https://arxiv.org/abs/2010.04159
- код авторов: https://github.com/fundamentalvision/Deformable-DETR

## Картинки

01-11 из COCO val2017 (785, 79188, 60855, 724, 25560, 1000, 2299, 139, 397133, 1761, 50165), 12-15 с Wikimedia Commons, уменьшены до 640:

| файл | источник |
|---|---|
| 12_kangaroos | Eastern Grey Kangaroos at Geehi NSW, Barfguts, CC BY-SA 4.0 |
| 13_lynx | Portrait of a Carpathian Lynx, Wilfredor, CC0 |
| 14_bruegel | Pieter Bruegel the Elder, Hunters in the Snow, public domain |
| 15_parking_aerial | Chorzów plac przed Planetarium aerial 2025, Adrian Tync, CC BY-SA 4.0 |
