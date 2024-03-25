<h1 align="center"> TABLEAU </h1> 

<h3 align="center"> Дашборды, итоговый проект (pet-project), домашние задания с курса, проверка гипотез | Dashboards, final project (pet-project), homework from the course, hypothesis testing </h3>

Проекты находятся в онлайн-формате в моем <a href="https://public.tableau.com/app/profile/marinaborisenko/vizzes/">Tableau Public аккаунте.</a> 
<br>
1. Pet-project.<br>
<br>
Это итоговый проект с курса по анализу данных. Находится он в файле "pet-project.twbx" или в <a href="https://public.tableau.com/views/_17112963223430/GENERAL?:language=en-US&:sid=&:display_count=n&:origin=viz_share_link">онлайн-формате.</a> Работа состояла в том, чтобы проанализировать базу данных магазина, продающего по всей России технику от флешек USB до мониторов. Необходимо было найти точки роста и точки убытка (категории, регионы, орпделённые клиенты, всё, что приносит больше убытка, чем прибыли). База данных была предоставлена в файле формата .xlsx от заказчицы, она находится в файле под названием "database.xlsx". У неё же я собрала требования и показала ей намеченный скетч дашбордов. Как только я собрала требования и заказчица одобрила план работы, я начала с очистки данных в Python, проверила дубли и пропуски, проверила полноту данных, посчитала корреляции между столбцами, выдвинула первые гипотезы и начала проверять их в Tableau (т.к. построение графиков там быстрее и проще). Далее построила около 60 графиков, из которых собрала 4 дашброада. высчитала KPI продаж, прибыли, среднего чека, затрат, кол-во клиентов, кол-во заказов, кол-во проданных товаров, средняя продолжительность доставки в днях, профит от каждого покупателя с прогнозом на год и обзор на каждого покупателя с кол-вом заказов и общим профитом с клиента, сортированный по кол-ву заказов для первого дашборда под названием "Sales, profit, KPI overview", фильтры по годам, виду клиента и категориям. Второй дашборд отражает информацию по категориям и подкатегориям, а также детализированную таблицу продаж. Здесь я наглядно показала какая категория, подкатегория, вид клиента убыточны и сколько за период было продано в общей сложности товаров по категориям, выводы и рекомендации я приведу в конце, фильтры второго дашборда под названием "Sales, profit, quantity per ctaegory & subcategory overview" по годам, виду клиента и категориям. Третий дашборд показывает более подробную информацию по регионам и служит информативной основой для региональных менеджеров, которым, по условию задачи, необходим отчет по их региону, чтобы принимать решения и мониторить локальные KPI. Здесь я отразила выраженность средней прибыли по категориям по регионам, по линии "Средний профит" ("Avg Profit - Most profitable") в серой зоне наиболее прибыльные регионы, справа общие KPI, которые, как и предыдущий график, отражают региональную статистику при выборе фильтра Federal subject. В нижней части дашборда график в виде карты, где можно вручную выбирать любое кол-во интересующих регионов по продажам, например, чтобы выбрать топ-20 убыточных регионов, необходимо выбрать "Is it BOTTOM" = "bottom", "Choose bottom N" = 20. По умолчанию на графике выставлен топ-10 регионов, лидирующих в продажах. Фильтры по категориям, федеральному субъекту и годам. На последнем четвертом дашборде я визуально отразила выдвинутые гипотезы, все из них я приняла (т.к. нулевая гипотеза состоит всегда в том, что изменений не произошло или одно не влияет на другое).<br>
Для достоверности высчитанных сетов и параметров я обращалась к Python, чтобы быть уверенной, что я вывожу нужные данные в Tableau. Все операции с Python находятся в файле "pet-project python.ipynb". Его можно запустить в google colab, прикрепив датасет с данными по продажам магазина. Я выдвинула 3 гипотезы и проверила их в python помимо tableau. Первая гипотеза заключалась в том, что, возможно, в городах, где большое население, покупают больше, нулевая гипотеза: profit не имеет связи с population - принята, прибыль не зависит от большого населения. Вторая гипотеза заключалась в том, что большие затраты могут быть обусловлены долгой доставкой, нулевая гипотеза: expenses не влияет на avg ship days - принята, затраты никак не связаны с долгой доставкой. Третья гипотеза заключалась в том, что т.к. магазин московский, то убыточные регионы являются таковыми из-за дальности доставки, нулевая гипотеза: profit по regions не зависит от дальности доставки - принята, визуально я отразила на карте топ-20 убыточных регионов и на ней можно увидеть, что половина убыточных регионов находится в западной и центральной России, некоторые очень близко к Москве, поэтому дальность доставки товаров никак не влияет на убыточность.<br>

<br>
<details>
  <summary>Выводы, рекомендации и подробное описание здесь</summary>
  <p>Требования canvas:<br>

<br>

![канвас](https://github.com/marina-bor-23/tableau/assets/164322986/7ad376fa-e6dc-40ae-a53f-10f8164c612d)


<br>
  Общая динамика положительная. Наиболее прибыльный год последний из данных, 2021. Не следует смотреть на кол-во заказов, т.к. их большое кол-во не означает большую прибыль, это можно увидеть из нижнего графика слева на 1 дашборде. Большое кол-во убыточных кл., которым, возможно, стоит поднять цену за доставку, а наиболее прибыльным можно было бы ее снизить или предложить другие акции. Средняя прибыль с кл. положительная и растёт в динамике и прогнозе, дела идут хорошо. Если брать в расчёт настоящие события 2020 года, то рост продаж можно связать с тем, что все были вынуждены сидеть дома и заказывать технику на дом, т.к. появилась надобность ею пользоваться и пользоваться дома, а не в школе или офисе. Также в тот год увеличилось среднее кол-во дней на доставку, что может быть связано с тем, что перевозки между городами тормозились ковидными ограничениями и появилась большая нагрузка на них, т.к. самовывоз уменьшился, а спрос на доставки на дом увеличился. Расходы везде возрастают и падают зависимо от продаж (продажи выросли, выросли и расходы и наоборот), что естественно и доказывает правильность датасета с точки зрения достоверности заносимых данных.<br>
Касаемо категорий – стоит серьезно задуматься о категории «мониторы», т.к. несет за собой много затрат, но все еще прибыльна. Самая прибыльная категория – компьютеры. Наиболее популярная же по кол-ву проданных товаров «остальные устройства». То есть, необходимо разработать акционные предложения для повышения прибыли с мониторов либо сменить представляемую продукцию. Продажи по мониторам заметно проседают последние 2 года в 3 квартале – возможно, акции можно связать с черной пятницей и предновогодними неделями. Та же ситуация с проседанием у категории «компьютеры». Остальные устройства растут ежегодно, здесь стоит обратить внимание только на иногда проседающий средний чек. Также стоит поменять ценовую политику либо отказаться вовсе от предоставления продукции «мониторы, подкатегория 28,1’ и 19,1’ – 23’» - это можно связать с тем, что такие большие мониторы трудно доставлять, а спрос на них низкий, они не являются стандартными экранами для компьютеров. Возможно, стоит оставить только первые 2 позиции мониторов, а от остальных отказаться. Затраты в категории мониторы в принципе наиболее высокие в сравнении с остальными категориями, нужна более детальная статистика по затратам.<br>
С «остальными устройствами» проблем не наблюдается, они не громоздкие и легки в доставке, часто нужны на замену и т.д., их прибыльность легко объясняется, убыточность ПО связана с непопулярностью покупки официального ПО и большой популярностью ставить «неофициальные» виндовсы, качать пиратские программы. Возможно, стоит отказаться от этой категории и увеличить ассортимент «остальных устройств».
Наиболее спорная категория – комьютеры, ПК и ноутбуки приносят прибыль по причине высокой стоимости на перечисленные товары, но мобильные телефоны несут за собой много затрат, возможно, они доставляются из-за границы и труды в доставке, а стоят при этом не так много, как ПК и ноутбуки. Стоит пересмотреть ассортимент либо повысить цены на телефоны, но это может быть чревато снижением продаж на телефоны либо стимулировать самовывоз из магазина. <br>
Если предположить, что в затраты входит починка и годовая гарантия на товар, которая в итоге была использована, тогда принять решение об отказе от определенных видов продукции станет еще проще, например, треть от всего кол-ва купленных мониторов принесла отрицательный профит – возможно, их вернули и убытки понесла компания. Больше всего мониторов с отрицательным профитом у ФЛ – это можно объяснить большим кол-вом проданных товаров для ФЛ в принципе, но также и неаккуратным личным пользованием либо доставка для ФЛ обычно в кол-во 1-2 шт. и она значительно затратнее, чем доставлять сразу несколько штук для ИП или корпоративных кл.<br>
По корпоративному сегменту – индивидуальные клиенты (физические лица) совершают больше всего заказов, они же самые прибыльные, стоит делать на них упор и дальше, запускать акции и скидки. Наименее прибыльными в течение 3 лет из 4 были ИП, стоит пересмотреть условия доставки и стоимости товара для такой категории кл., возможно, стимулировать повышение продаж акциями. У корпоративных легко объясняется прибыльность компьютеров и остальных устройств – нужные для офиса вещи, что подтверждает достоверность вносимых в БД записей. Однако мониторы по затратам близки к прибыли, что говорит о том, чтобы пересмотреть условия доставки либо поддержки после покупки. Меньше всего мониторов покупают ИП – они им не нужны для демонстраций, для отделов в компании и пр., стараться в этой категории для этого сегмента кл. не смысла.
Самые убыточные регионы (топ 10 по среднему профиту): Рязанская область, Якутия, Татарстан, Марий Эл, Новгородская, Амурская области, Карачаево-Черкесская республика, Тверская область, Удмуртия и Алтай. Многие отдалены от западной части России (где наибольшее население), однако, корреляции между днями на доставку и профитом нет, как и корреляции между затратами и днями на доставку, но стоит либо повысить цены на доставку в эти регионы, либо отказаться от продажи убыточных категорий в эти регионы. Топ 30 по продажам находится в центральной части России, на них и стоит делать упор. На дашборде директорки или директоры по продажам в регионах уже сами смогут оценить бизнес дела компании в своем выбранном регионе.<br>
Таким образом, несмотря на положительную динамику и рост по всем основным KPI, прибыль можно было бы увеличить, пересмотрев ассортимент убыточных категорий и подкатегорий, поменяв ценовую политику/условия доставки/условия поддержки и гарантии/применив скидки, акционные предложения для описанных выше сегментов кл.<br>
    </p>
</details>



