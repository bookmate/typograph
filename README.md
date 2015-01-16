Installation
----

First start by adding this gem to your Gemfile:

``` ruby
gem 'ruby_typograph'
```
or
``` ruby
gem 'ruby_typograph', github: 'Tolia/typograph', require: "typograph"
```
And then execute
```
$ bundle
```



# Typograph

Gem for typographing russian and english texts.

##### Привязка союзов, предлогов
``` ruby
Typograph.process 'Я бы в лётчики б пошёл, пусть меня научат.'
> 'Я&nbsp;бы в&nbsp;летчики&nbsp;б пошел, пусть меня научат.'
```

##### Расстановка кавычек
``` ruby
Typograph.process '"Кавычки "второго уровня"" and "Quotes "second level""'
> '«Кавычки “второго уровня”» and “Quotes ‘second level’”'
```

##### Расстановка запятых перед а, но
``` ruby
Typograph.process 'Мало написать а запятые кто за тебя расставит.'
> '"Мало написать, а&nbsp;запятые кто за&nbsp;тебя расставит.'
```

##### Отсутствие запятых у "а"" и "но" после тире
``` ruby
Typograph.process 'Текст до тире – а теперь после'
> 'Текст до&nbsp;тире&nbsp;— а&nbsp;теперь после'
```

##### Расстановка правильного апострофа в английских текстах
``` ruby
Typograph.process "don't"
> 'don’t'
```


- Замена ё на е
- Удаление лишних пробелов
- Расстановка дефиса в предлогах из-за, из-под
- Расстановка дефиса перед -таки
- Расстановка дефиса после кое-, кой-
- Удаление пробела перед символом процент
- Удаление пробелов внутри скобок
- Выделение прямой речи
- Замена (R) на символ зарегистрированной торговой марки
- Замена (c) на символ копирайт
- Замена (tm) на символ торговой марки
- Замена дробей 1/2, 1/4, 3/4 на соответствующие символы
- Расстановка пробелов перед сокращениями см., им.
- Расстановка пробелов перед сокращениями гл., стр., рис., илл.
- Объединение сокращений и др.
- Расстановка пробелов в сокращениях г., ул., пер., д.
- Расстановка пробелов перед сокращениями dpi, lpi

### rspec

``` ruby
Finished in 0.07754 seconds
47 examples, 3 failures

Failed examples:

rspec ./spec/typograph_spec.rb:73 # .process Удаление пробелов перед знаками препинания
rspec ./spec/typograph_spec.rb:79 # .process Расстановка пробелов после знака препинания
rspec ./spec/typograph_spec.rb:103 # .process Выделение прямой речи
```
