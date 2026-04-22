# Лабораторная работа 1
## Вариант на тройку
### Обнаружение и распознавание объектов с использованием YOLOv11

В работе исследуется задача обнаружения объектов на датасете **Chess Pieces (YOLO format)**.
В ноутбуке:
- обучается baseline-модель `YOLO11n`;
- проверяются гипотезы улучшения baseline;
- сравниваются предобученная модель и модель, обученная с нуля;
- реализуется собственная упрощенная модель детекции на `PyTorch`.

## Датасет

Используется датасет **Chess Pieces (YOLO format)**:
[Kaggle](https://www.kaggle.com/datasets/ahmedhaytham/chess-object-detection-yolov5-for-chess)

Ожидаемая структура проекта:
- `train/images`, `train/labels`
- `valid/images`, `valid/labels`
- `test/images`, `test/labels`
- `data.yaml`
- `lab1.ipynb`

Разметка используется в формате YOLO.

## Установка

```powershell
git clone https://github.com/Goida88/CS.git
cd "CS/lab1 CV"

python -m venv .venv
.venv\Scripts\Activate.ps1

python -m pip install --upgrade pip
python -m pip install ultralytics pyyaml notebook jupyter
python -m pip install torch torchvision torchaudio
```

Если планируется запуск на GPU, можно установить CUDA-совместимую сборку PyTorch:

```powershell
python -m pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu128
```

## Запуск

1. Убедиться, что в корне проекта находятся `train`, `valid`, `test`, `data.yaml` и `lab1.ipynb`.
2. Открыть `lab1.ipynb` в VS Code, Cursor или Jupyter.
3. Последовательно выполнить все ячейки ноутбука сверху вниз.

## Что содержится в ноутбуке

Ноутбук включает:
- выбор датасета и метрик качества;
- обучение baseline-модели `YOLO11n`;
- проверку гипотез улучшения baseline;
- сравнение baseline и improved baseline;
- реализацию собственной модели детекции на `PyTorch`;
- сравнение собственной модели с baseline-моделью.

## Используемые метрики

Для оценки качества используются:
- `mAP@0.5`
- `mAP@0.5:0.95`

## Примечание

При запуске на CPU обучение собственных моделей может занимать заметное время.
Для ускорения рекомендуется использовать GPU и CUDA-совместимую версию PyTorch.
