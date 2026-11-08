# Анализ архитектуры детекции: Deformable DETR

Ruslan Papina, группа М25-555

Домашнее задание: разобрать современную архитектуру детекции объектов. Выбрал Deformable DETR (ICLR 2021): какую проблему DETR она решает, как устроена, что показывают эксперименты и ablation в статье. Плюс запуск pretrained-модели на 15 картинках и разбор ошибок.

Отчёт: [report.pdf](report.pdf)

## Структура

- `detection.ipynb` - запуск Deformable DETR, single-scale версии и обычного DETR на картинках, визуализации, ошибки
- `make_report.py`, `report_lib.py` - сборка `report.pdf`
- `images/` - 15 картинок (11 из COCO val2017, 4 с Wikimedia Commons)
- `paper/` - рисунки из статьи (Figure 1-3)
- `results/` - картинки с детекциями, `summary.csv` (число боксов по картинкам и моделям), `time.csv`

## Запуск

```
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter nbconvert --to notebook --execute --inplace detection.ipynb
python make_report.py
```

Веса скачиваются с Hugging Face при первом запуске. Считалось на CPU (MacBook M2), ноутбук выполняется пару минут.

## Ссылки

- статья: https://arxiv.org/abs/2010.04159, https://openreview.net/forum?id=gZ9hCDWe6ke
- официальный код: https://github.com/fundamentalvision/Deformable-DETR
- веса: [SenseTime/deformable-detr](https://huggingface.co/SenseTime/deformable-detr), [SenseTime/deformable-detr-single-scale](https://huggingface.co/SenseTime/deformable-detr-single-scale), [facebook/detr-resnet-50](https://huggingface.co/facebook/detr-resnet-50)

## Картинки

| файл | источник |
|---|---|
| 01-11 | COCO val2017: 785, 79188, 60855, 724, 25560, 1000, 2299, 139, 397133, 1761, 50165 |
| 12_kangaroos | Eastern Grey Kangaroos at Geehi NSW, Barfguts, CC BY-SA 4.0 |
| 13_lynx | Portrait of a Carpathian Lynx, Wilfredor, CC0 |
| 14_bruegel | Pieter Bruegel the Elder, Hunters in the Snow, public domain |
| 15_parking_aerial | Chorzów plac przed Planetarium aerial 2025, Adrian Tync, CC BY-SA 4.0 |

Картинки 12-15 с Wikimedia Commons, уменьшены до 640 по длинной стороне.
