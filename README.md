# Knowledge Distillation (Teacher–Student) on CIFAR-100

## Описание
Проект демонстрирует парадигму **ученик–учитель (knowledge distillation)** для обучения нейронных сетей на датасете **CIFAR-100**
Сначала обучается большая модель (*teacher*), затем компактная модель (*student*) обучается как в обычном режиме, так и с использованием подсказок от учителя. Результаты сравниваются по точности

## Что делает код
- Загружает и подготавливает датасет CIFAR-100  
- Обучает модель-учитель (ResNet)  
- Обучает модель-ученик:
  - обычное supervised-обучение  
  - обучение с knowledge distillation (CE + KL + temperature)  
- Строит графики точности на train и test  
- Сравнивает качество baseline и KD  

## Используемые модели
- **Teacher:** ResNet, адаптированная под 32×32 и 100 классов  
- **Student:** компактная CNN (Conv → BatchNorm → ReLU → MaxPool)

## Требования
- Python 3.10+  
- PyTorch 2.5+  
- torchvision  
- numpy  
- matplotlib  
- tqdm  

GPU (CUDA) рекомендуется

## Установка зависимостей
`pip install torch torchvision numpy matplotlib tqdm`

## Запуск
`jupyter notebook kursovaya_mini.ipynb`

