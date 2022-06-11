# **Лабораторна робота №1**

---

## Необхідні ресурси:

- Встановлена бібліотека `pydocstyle`.
- Встановлений компілятор для Python.

## Інформація про пакет програми:

- Знайшов пакет `w2n2w` на PYPI , який може перетворювати числа в слова .
- Додано `requirements.txt` в якому знаходяться бібліотеки.
- Створино пакет з логікою який розподілений між кількома модулями.
- Додано документацію, яка відповідає стандартним правилам `pydocstyle`.
- Налаштовано виконання за допомогою команди `python -m num2word`.

## Макет Python проекту

```text
.                           <- the root project directory
├── num2word                <- a package
│   ├── __init__.py         <- special module, says "num2word" is the package
│   ├── __main__.py         <- a default execution
│   ├── w2n2w               <- an inner package
│   │   └── __init__.py     <- special module, says "w2n2w" is the inner package for "num2word"
│   └── phrases.py          <- a module of "num2word" package
├── README.md               <- a description
└── requirements.txt        <- used packages
```

## Перевірка чи відповідає проект стандартним правилам `pydocstyle`:

```text
falcon@Makohons-MBP Lab_1 % sudo python3 -m pydocstyle num2word
Password:
num2word/w2n2w/__init__.py:1 at module level:
        D104: Missing docstring in public package
num2word/w2n2w/__init__.py:117 in public class `Word2Number`:
        D204: 1 blank line required after class docstring (found 0)
num2word/w2n2w/__init__.py:117 in public class `Word2Number`:
        D300: Use """triple double quotes""" (found '''-quotes)
num2word/w2n2w/__init__.py:117 in public class `Word2Number`:
        D400: First line should end with a period (not 's')
num2word/w2n2w/__init__.py:120 in public method `split_by_magnitude`:
        D300: Use """triple double quotes""" (found '''-quotes)
num2word/w2n2w/__init__.py:120 in public method `split_by_magnitude`:
        D401: First line should be in imperative mood (perhaps 'Split', not 'Splits')
num2word/w2n2w/__init__.py:156 in public method `group_by_magnitude_order`:
        D205: 1 blank line required between summary line and description (found 0)
num2word/w2n2w/__init__.py:156 in public method `group_by_magnitude_order`:
        D300: Use """triple double quotes""" (found '''-quotes)
num2word/w2n2w/__init__.py:156 in public method `group_by_magnitude_order`:
        D401: First line should be in imperative mood (perhaps 'Group', not 'Groups')
num2word/w2n2w/__init__.py:193 in public method `process_chunk`:
        D205: 1 blank line required between summary line and description (found 0)
num2word/w2n2w/__init__.py:193 in public method `process_chunk`:
        D300: Use """triple double quotes""" (found '''-quotes)
num2word/w2n2w/__init__.py:193 in public method `process_chunk`:
        D401: First line should be in imperative mood (perhaps 'Process', not 'Processes')
num2word/w2n2w/__init__.py:348 in public function `word_to_num`:
        D205: 1 blank line required between summary line and description (found 0)
num2word/w2n2w/__init__.py:348 in public function `word_to_num`:
        D300: Use """triple double quotes""" (found '''-quotes)
num2word/w2n2w/__init__.py:348 in public function `word_to_num`:
        D401: First line should be in imperative mood (perhaps 'Convert', not 'Converts')
num2word/w2n2w/__init__.py:473 in public function `num_to_word`:
        D300: Use """triple double quotes""" (found '''-quotes)
num2word/w2n2w/__init__.py:473 in public function `num_to_word`:
        D400: First line should end with a period (not 's')
num2word/w2n2w/__init__.py:473 in public function `num_to_word`:
        D401: First line should be in imperative mood (perhaps 'Convert', not 'Converts')
falcon@Makohons-MBP Lab_1 %
```

Виправлення стосуються тільки завантаженого пакету `w2n2w` з PYPI.

## Приклад запуску програми на основі ОС Linux:

- При введені коректних значень виводиться число записане словом:

```text
falcon@Makohons-MBP Lab_1 % python3 -m num2word
Hello!
Please, enter a floating point number: 123
Number to Word: one hundred and twenty three
falcon@Makohons-MBP Lab_1 % python3 -m num2word
Hello!
Please, enter a floating point number: -452
Number to Word: negative four hundred and fifty two
falcon@Makohons-MBP Lab_1 % python3 -m num2word
Hello!
Please, enter a floating point number: 0.478
Number to Word: zero point four seven eight
falcon@Makohons-MBP Lab_1 % python3 -m num2word
Hello!
Please, enter a floating point number: -1
Number to Word: negative one
falcon@Makohons-MBP Lab_1 % python3 -m num2word
Hello!
Please, enter a floating point number: 1000
Number to Word: thousand
falcon@Makohons-MBP Lab_1 %
```

- При введені некоректних значень виводиться напис "Could not convert data to an type 'float'. Please, enter a floating point number.", а в новому рядку записується цифра "0" у вигляді слова:

```text
falcon@Makohons-MBP Lab_1 % python3 -m num2word
Hello!
Please, enter a floating point number: two
Could not convert data to an type 'float'. Please, enter a floating point number.
Number to Word: zero
falcon@Makohons-MBP Lab_1 % python3 -m num2word
Hello!
Please, enter a floating point number: ^&^&*
Could not convert data to an type 'float'. Please, enter a floating point number.
Number to Word: zero
falcon@Makohons-MBP Lab_1 %
```
