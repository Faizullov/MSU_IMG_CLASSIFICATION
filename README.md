# MSU_IMG_CLASSIFICATION

# Работа по классификации изображений на 9 классов.

## LB 1
 Изменил изначальный класс Dataset следиющим образом: перевел картинки и лейблы в torch тензоры

## LB 2
  Пример вывода изображения

## LB 3
  Самописный Data Loader. В котором релизована аугментация и разбитие датасета на батчи. Аугментация: горизонтальный переворот, вертикальный переворот, поворот от 0 до 30 градусов, небольшое приближение картинки в случайных местах и расширение получившейся картинки до разморов 224 x 224, нормализация изображения. Значения для нормализации были получены в ноутбуке.

## LB 4
  Использовал wandb для визаулизации параметров модели и визуализации ошибки на тестовом датасете. График accuracy на тестовом датасете можно посомтреть по ссылке: https://api.wandb.ai/links/airat-fayzullov-40/binpdr0i . График изменения learning rate: https://wandb.ai/airat-fayzullov-40/my-awesome-project_MSU/reports/lr-23-11-27-02-05-03---Vmlldzo2MDg1NDYw . 
  Об обучении и модели: использовал модель resnet34, т.к. мне нравится её архитектура (и я считаю её наиболее эффективной) предоставляющая некую вариацию ансамблирования при обучении. Для модели использовал претрейн и поменял только последний слой и первые 3 эпохи обучал только последний слой, чтобы ускорить обучение. Сохранял результаты модели после каждого этапа обучения в checkpoint.pth. Обучение шло 30 эпох. Learning rate убывает по косинусу
