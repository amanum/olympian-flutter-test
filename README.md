# Тестовое задание на позицию Flutter-разработчика

Это тестовое задание на вакансию ведущего Flutter разработчика в компанию One Clue. У вас должен быть практический опыт разработки приложений. В этой задаче я ожидаю умение погружаться в существующий проект, реализовывать новую логику в существующем приложения и формулировать свои мыли и решения в текстовом виде.
Для разработки обязательно иметь установленный эмулятор iOS либо реальное устройство.

## Задача
Необходимо добавить анимацию на игровое поле. Анимация должна отображаться до того момента как слово угадают.
[Screen как должно выглядеть](https://github.com/imakarov/olympian-flutter-test/blob/master/test-flutter.png)

## Что сделать:
1. Развернуть приложение на локальном окружении, запустить на ios в эмуляторе или реальном устройстве. После установке при нажатии на кнопку Play вы должны оказаться на экране с 3мя дощечками.

2. Добавить lottie анимацию на экран как показано на изобажении выше (см. Задача). Данная анимация должна появляться только на первом уровне и только на левой верхней дощечке. После того как пользователь отагадает первое слово ("камень", слово может меняться) анимация отображаться не должна.

3. Обосновать свое решение в текстовом виде, положительные и отрицательные моменты реализации на ваш взгляд. Закоммитить в корневой Readme.

### Решение:
1. Добавил пакет lottie
2. Написал условия для показа анимации в area_screen, чтобы не тащить зависимости в WordItem
3. Прокинул условия в WordItem и вставил анимацию
Не могу выделить положительные или отрицательные моменты в моей реализации, т.к. написанного кода слишком мало.

## Дополнительное задание (опционально):
Сформулиромать в текстовом виде 3 предложения по рефакторингу чтобы вы хотели изменить в приложении, и обоснование почему считаете что это необходимо сделать. Закоммитить в Readme.

### Мои предложения по рефакторингу:
1. Во view сликом много логики и сама верстка выглядит громоздкой, вижу здесь 2 решения:
    - Добавление отдельных view model для разгрузки view от логики
    - Дробление верстки на отдельные виджеты и вынос их в отдельные файлы
2. Добавить функциям типы возвращаемых объектов, чтобы было сразу понятно, что вернется.
Пример:
```
_getBgImage(WordModel word, context) {
    final vm = Provider.of<GameViewModel>(context, listen: false);
    final state = word.state;

    if (state == WordState.input) {
      return 'assets/images/word_input.png';
    }...
  }
```
3. (minor) Можно вынести все пути до assets в абстрактный класс со статичными переменными для удобства и во избежание ошибок

## Как выполнять?
1. Вы можете форкнуть этот репозиторий или клонировать к себе его код
2. После выполнения задания отправляйте ссылку на ваш репозиторий в телеграм [@makarovilya](https://t.me/makarovilya) 

## Ссылки:
1. [Lottie Animation](https://raw.githubusercontent.com/imakarov/olympian-flutter-test/master/Animation.json)
2. [Preview Lottie Animation](https://app.lottiefiles.com/preview)
3. [GitHub](https://github.com/imakarov/olympian_flutter_test)