# Лекция 8.  

# :triangular_flag_on_post: Flex-box

**CSS flexbox (Flexible Box Layout Module)** — модуль макета гибкого контейнера — представляет собой способ компоновки элементов.

Flexbox состоит из **flex-контейнера (flex container)** — родительского контейнера и **гибких элементов (flex items)** — дочерних блоков.


![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex01.png)"width: 600px;"


Итак, оси flexbox — это основное понятие данной модели.

**Главная ось flex-контейнера** — это направление, в котором располагаются его дочерние элементы. У главной оси есть начало и конец (они обозначены на схеме).

**Поперечная ось flex-контейнера** — это направление, перпендикулярное главной оси. У поперечной оси тоже есть начало и конец (отмечены на схеме).

Если вашей актуальной локалью является LTR (left-to-right), то направление главной оси пролегает слева направо. Направление поперечной оси пролегает сверху вниз.

# Основные преимущества flexbox:
*   Блоки легко становятся гибкими, элементы могут сжиматься и растягиваться, заполняя пространство.
*   Неважно, в каком порядке расположены HTML-элементы. Вы можете изменить их порядок через CSS
*   Располагать элементы в одном из четырех направлений: слева направо, справа налево, сверху вниз или снизу вверх.
*   Переопределять порядок отображения элементов.
*   Автоматически определять размеры элементов таким образом, чтобы они вписывались в доступное пространство.
*   Решать проблему с горизонтальным и вертикальным центрированием.
*   Переносить элементы внутри контейнера, не допуская его переполнения.
*   Создавать колонки одинаковой высоты.
*   Создавать прижатый к низу страницы футер


# Свойство `display: flex;`

```
.flex-container {
/*генерирует flex-контейнер уровня блока*/

    display: -webkit-flex; 
    display: flex; 
}

.flex-container {
/*генерирует flex-контейнер уровня строки*/

    display: -webkit-inline-flex;
    display: inline-flex; 
}
```


После установки данных значений свойства каждый дочерний элемент автоматически становится flex-элементом, выстраиваясь в ряд (вдоль главной оси) колонками одинаковой высоты, равной высоте блока-контейнера.

При этом блочные и строчные дочерние элементы ведут себя одинаково, т.е. ширина блоков равна ширине их содержимого с учетом внутренних полей и рамок элемента.


# `flex-direction`

Свойство **flex-direction** определяет, каким образом flex-элементы укладываются во flex-контейнере, задавая направление главной оси flex-контейнера. Они могут располагаться в двух главных направлениях — горизонтально, как строки или вертикально, как колонки. Главная ось по умолчанию идет слева направо. Поперечная – сверху вниз.


![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-direction-row.png)"width: 300px; float: left;"
![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-direction-col.png)"width: 300px;"

@@@ (json)
[
    ["property", "comment"],
    ["**row**", "Значение по умолчанию, слева направо. Flex-элементы выкладываются в строку."],
    ["**row-reverse**", "Направление справа налево. Flex-элементы выкладываются в строку относительно правого края контейнера."],
    ["**column**", "Направление сверху вниз. Flex-элементы выкладываются в колонку."],
    ["**column-reverse**", "Колонка с элементами в обратном порядке, снизу вверх."]
]
@@@

** **

```
.flex-container {
    display: flex;
    flex-direction: row-reverse;
}
```


# `flex-wrap`

Свойство **flex-wrap** управляет тем, как flex-контейнер будет выкладывать flex-элементы — в одну строку или в несколько, и направлением, в котором будут укладываться новые строки. По умолчанию flex-элементы укладываются в одну строку. При переполнении контейнера их содержимое будет выходить за границы flex-элементов. Не наследуется.


@@@ (json)
[
    ["property","image", "comment"],
    ["**nowrap**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-wnw.png)", "Значение по умолчанию. Flex-элементы не переносятся, а располагаются в одну линию слева направо"],
    ["**wrap**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-fww.png)", "Flex-элементы переносятся, располагаясь в несколько горизонтальных рядов"],
    ["**wrap-reverse**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-fwwr.png)", "Flex-элементы переносятся, располагаясь в обратном порядке слева-направо, при этом перенос происходит снизу вверх"]
]
@@@


```
.flex-container {
    display: flex;
    flex-wrap: wrap;
}
```



# `justify-content`

Свойство **justify-content** выравнивает flex-элементы по ширине flex-контейнера, распределяя оставшееся свободное пространство, незанятое flex-элементами.

@@@ (json)
[
    ["property", "image", "comment"],
    ["**flex-start**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-jcfs.png)", "Значение по умолчанию. Flex-элементы позиционируются от начала flex-контейнера."],
    ["**flex-end**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-jcfe.png)", "Flex-элементы позиционируются относительно правой границы flex-контейнера."],
    ["**center**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-jcc.png)", "Flex-элементы выравниваются по главной оси, свободное место между ними распределяется следующим образом: первый блок располагается в начале flex-контейнера, последний блок – в конце, все остальные блоки равномерно распределены в оставшемся пространстве, а свободное пространство равномерно распределяется между элементами."],
    ["**space-around**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-jcsa.png)", "Flex-элементы выравниваются по главной оси, а свободное место делится поровну, добавляя отступы справа и слева."],
    ["**space-between**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-jcsb.png)", "Flex-элементы выравниваются по главной оси, а свободное место делится поровну, добавляя отступы справа и слева."]
]
@@@

```
.flex-container {
    display: flex;
    justify-content: space-between;
}
```

# `align-items`


Свойство **align-items** выравнивает flex-элементы, в том числе и анонимные flex-элементы по перпендикулярной оси (по высоте).

```
.flex-container {
    display: flex;
    align-items: flex-start;
}
```

@@@ (json)
[
    ["property", "image", "comment"],
    ["**stretch**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-fias.png)", "**_Значение по умолчанию_**. Flex-элементы **_растягиваются_**, занимая все пространство по высоте."],
    ["**flex-start**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-faifs.png)", "Flex-элементы выравниваются по левому краю flex-контейнера **_относительно верхнего края блока-контейнера_**."],
    ["**flex-end**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-faife.png)", "Flex-элементы выравниваются по левому краю flex-контейнера относительно **_нижнего края блока-контейнера._**"],
    ["**center**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-faic.png)",  "Flex-элементы выравниваются **_по центру_** flex-контейнера."],
    ["**baseline**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-fiab.png)", "Флексы выравниваются по их базовой линии."]
]
@@@



# `align-content`

Свойство CSS **align-content** выравнивает линии контейнера flex в контейнере flex при наличии дополнительного пространства на перекрестной оси.

Это свойство не имеет никакое влияние на однострочные гибкие блоки.

@@@ (json)
[
    ["property", "image", "comment"],
    ["**flex-start**","![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-acfs.png)", "Линии упорядочиваются  начиная  с cross-start. Поперечная кромка первой линии и поперечная кромка контейнера flex сбрасываются вместе. Каждая следующая строка совпадает с предыдущей."],
    ["**flex-end**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-acfe.png)", "Линии  упорядочиваются начиная cross-end. Кросс-энд последней линии и кросс-энд контейнера гибкого блока сбрасываются вместе. Каждая предыдущая строка очищается следующей строкой."],
    ["**center**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-acc.png)", "Линии упакованы к центру контейнера Flex. Линии выравниваются по центру контейнера flex. Расстояние между кросс-стартовым краем контейнера flex и первой линией, а также между кросс-эндом контейнера flex и последней линией одинаково."],
    ["**space-between**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-acsb.png)", "Линии равномерно распределены в контейнере. Интервал делается так, чтобы расстояние между двумя соседними элементами было одинаковым. Поперечная кромка и поперечная кромка гибкого контейнера распределяются соответственно первой и последней кромками линии."],
    ["**space-around**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-acsa.png)", "Линии равномерно распределены таким образом, что пространство между двумя соседними линиями одинаковые. Пустое пространство перед первой и после последней строки равняется половине расстояния между двумя смежными линиями."],
    ["**stretch**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-acs.png)", "Линии растягиваются, чтобы использовать оставшееся пространство. Свободное пространство разделено поровну между всеми линиями."],
    ["**space-evenly**", "![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-acse.png)", "Строки равномерно распределяются таким образом, чтобы пространство между двумя соседними строками, а также пространство перед первой строкой и после последней строки было одинаковым."]
]
@@@


# `order`

Свойство **order** определяет порядок, в котором flex-элементы отображаются внутри flex-контейнера. По умолчанию для всех flex-элементов задан порядок order: 0; и они следуют друг за другом по мере добавления во flex-контейнер. Самый первый flex-элемент по умолчанию расположен слева. Чтобы поставить любой flex-элемент в начало строки, ему нужно назначить order: -1; в конец строки — order: 1.

![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-order.png)"width: 400px;"


```
.flex-container {
    display: flex;
}

.flex-item {
    order: 1;
}
```


# `flex-grow`

Свойство **flex-grow** определяет то, на сколько отдельный flex-блок может быть больше соседних элементов, если это необходимо. Он определяет, какое количество <span style="text-decoration:underline;">доступного пространства</span> внутри гибкого контейнера должно занимать элемент.

Например, если все flex-блоки внутри flex-контейнера имеют flex-grow:1, то они будут одинакового размера. Если один из них имеет flex-grow:2, то он будет в 2 раза больше, чем все остальные.

Применяется к: конкретному flex блоку.

![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/img-flex-grow.png)"width: 400px;"

Данное свойство входит в свойство-сокращение flex.

Значение по умолчанию: 0.

```
.flex-item {
	flex-grow: положительное число;
}
```


# `flex-basis`

CSS свойство flex-basis задает базовый размер флекс элемента по основной оси. Это свойство определяет размер контент-бокса, если не задано иначе через [box-sizing](https://developer.mozilla.org/ru/docs/Web/CSS/box-sizing).


```
.flex-item {
  flex-basis: <length> | auto; /* default auto */
}
```


# Дополнительный материал

1. [https://css-tricks.com/snippets/css/a-guide-to-flexbox/](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
2. [https://jonibologna.com/blog/flexbox-cheatsheet](https://jonibologna.com/blog/flexbox-cheatsheet)
3. [flex-box тренажер №1](http://www.flexboxdefense.com/)
4. [flex-box тренажер №2](https://flexboxfroggy.com/#ru)
5. [разница между width и flex-basis](https://medium.com/@stasonmars/%D1%80%D0%B0%D0%B7%D0%BD%D0%B8%D1%86%D0%B0-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-width-%D0%B8-flex-basis-f34e658ce6a2)
6. [подробнее о flex-shrink](https://medium.com/@stasonmars/%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-flex-shrink-%D0%B2-css-%D0%BF%D0%BE%D0%B4%D1%80%D0%BE%D0%B1%D0%BD%D0%BE%D0%B5-%D1%80%D1%83%D0%BA%D0%BE%D0%B2%D0%BE%D0%B4%D1%81%D1%82%D0%B2%D0%BE-c41e40767194)


# :house: HomeWork

!!! Все задания максимально выполняем с помощью flex-box свойств


**1.Первый уровень (“делаем каркас”)**

Делаем верстку макета вашего будущего сайта ([перейди по ссылке](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/hw-8.png)).

Требования: 
* элементы в хедере выровнены (вертикально и горизонтально) с помощью flex-box
* ширина боковых колонок 210px;
* footer прибит к низу страницы (т.е. контент занимает всю свободную высоту)
* учитываем такую особенность верстки контента: более важный контент должен стоять в потоке выше (а боковые части с aside - соответственно ниже в потоке)

---

**2.Второй уровень(“наполняем контентом”)**

Дополняем предыдущее задание [контентом](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/hw-8.2.png) (для выравнивания и расположения блоков используем свойства flex-box !)

Делаем ховер “карточек” внутри контента на свое усмотрение.

---

**3.Третий уровень("только флекс")**

У вас есть следующий код:
```
<div class="holder">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
  <div class="item">5</div>
</div>
```
С помощью стилей привести блоки в такой вид:
![](https://github.com/olgamaslovaolga/Alevel-Markup/raw/master/images/hw-8.3.png)"width: 400px;"
