# Inpaiting and FaceSwap
Было дано видео на которое наложили маску. Нужно было восстановить лицо Анджелины Джоли
## План
1. Разбить видео на кадры
2. Восстановить лицо с помощью модели **Inpaiting**
3. Заменить произвести замену лица с помощью **FaceSwap**

##  Сделано
1. Разбил видео на **[КАДРЫ](https://github.com/robertzaraev/GAN/tree/main/Lab%204/frame_folder)**
2. Отправил кадры на восстановление модели **[GPEN](https://github.com/yangxy/GPEN)**
3. Для замены лица я пробовал **[SberFaceSwap](https://github.com/ai-forever/ghost)** и **[SimSwap](https://github.com/neuralchen/SimSwap)**
- **[SberFaceSwap](https://github.com/ai-forever/ghost)** не смог найти лицо, **[SimSwap](https://github.com/neuralchen/SimSwap)** - смог

## Результаты
Результаты Inpaiting можно увидеть [здесь](https://github.com/robertzaraev/GAN/tree/main/Lab%204/results) или в формате [видео здесь](https://github.com/robertzaraev/GAN/blob/main/Lab%204/videoAfterInpaiting.mp4).
Косаемо результатов FaceSwap, нет удовлетворительного результата. Различий не заметил после SimSwap, результат после SimSwap [здесь](https://github.com/robertzaraev/GAN/blob/main/Lab%204/result.mp4).

## Гипотезы
1. Изменить размер маски, сделать ее поменьше. Так как у меня не было исходников, то я не смог поэксперементировать.
2. Возможно, стоило уменьшить кадр подаваемый в модель GPEN, оставить только область где предпологается лицо.
3. Проверить больше сеток, многие сетки требуют наличие GPU, инференс каждой модели переделывать под CPU затратно по времени.

### P.S.
Всю работу с кадрами можно увидеть [здесь](https://github.com/robertzaraev/GAN/blob/main/Lab%204/ProcessWithVideoAndMask.ipynb), только чистовик и только то, что пошло в финальный Pipeline GPEN + SimSwap 