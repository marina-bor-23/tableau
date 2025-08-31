<h1 align="center"> DASHBOARDS </h1> 

<h3 align="center"> Рабочие дашборды с предыдущего места работы, итоговый проект (pet-project) после курса, проверка гипотез<br> | Work dashboards from a previous job, final project (pet-project) after the course, hypothesis testing </h3>

Проекты находятся в онлайн-формате в моем <a href="https://public.tableau.com/app/profile/marinaborisenko/vizzes/">Tableau Public аккаунте.</a> 
<br>

<h3 align="left">  Дашборды с предыдущего места работы  </h3> 

Дашборды-отчеты после окончания акций от отдела маркетинга: ![дашборды](https://cloud.mail.ru/public/GiM2/1FaU55wiw) <br>



<h3 align="left">  1. Pet-project №1.  </h3> 

Это итоговый проект с курса по анализу данных. Находится он в файле "pet-project.twbx" или в <a href="https://public.tableau.com/views/_17112963223430/GENERAL?:language=en-US&:sid=&:display_count=n&:origin=viz_share_link">онлайн-формате.</a> Работа состояла в том, чтобы проанализировать базу данных магазина, продающего по всей России технику от флешек USB до мониторов. Необходимо было найти точки роста и точки убытка (категории, регионы, орпделённые клиенты, всё, что приносит больше убытка, чем прибыли). База данных была предоставлена в файле формата .xlsx от заказчицы, она находится в файле под названием "database.xlsx". У неё же я собрала требования и показала ей намеченный скетч дашбордов.   
<p>Требования canvas:<br>

![канвас пустой](https://github.com/marina-bor-23/tableau/assets/164322986/e5dda1bc-de5b-4ac0-be14-f541a6933da0)


![канвас](https://github.com/marina-bor-23/tableau/assets/164322986/7ad376fa-e6dc-40ae-a53f-10f8164c612d)





Как только я собрала требования и заказчица одобрила план работы, я начала с очистки данных в Python, проверила дубли и пропуски, проверила полноту данных, посчитала корреляции между столбцами, выдвинула первые гипотезы и начала проверять их в Tableau (т.к. построение графиков там быстрее и проще). Далее построила около 60 графиков, из которых собрала 4 дашброада. высчитала KPI продаж, прибыли, среднего чека, затрат, кол-во клиентов, кол-во заказов, кол-во проданных товаров, средняя продолжительность доставки в днях, профит от каждого покупателя с прогнозом на год и обзор на каждого покупателя с кол-вом заказов и общим профитом с клиента, сортированный по кол-ву заказов для первого дашборда под названием "Sales, profit, KPI overview", фильтры по годам, виду клиента и категориям. Второй дашборд отражает информацию по категориям и подкатегориям, а также детализированную таблицу продаж. Здесь я наглядно показала какая категория, подкатегория, вид клиента убыточны и сколько за период было продано в общей сложности товаров по категориям, выводы и рекомендации я приведу в конце, фильтры второго дашборда под названием "Sales, profit, quantity per ctaegory & subcategory overview" по годам, виду клиента и категориям. Третий дашборд показывает более подробную информацию по регионам и служит информативной основой для региональных менеджеров, которым, по условию задачи, необходим отчет по их региону, чтобы принимать решения и мониторить локальные KPI. Здесь я отразила выраженность средней прибыли по категориям по регионам, по линии "Средний профит" ("Avg Profit - Most profitable") в серой зоне наиболее прибыльные регионы, справа общие KPI, которые, как и предыдущий график, отражают региональную статистику при выборе фильтра Federal subject. В нижней части дашборда график в виде карты, где можно вручную выбирать любое кол-во интересующих регионов по продажам, например, чтобы выбрать топ-20 убыточных регионов, необходимо выбрать "Is it BOTTOM" = "bottom", "Choose bottom N" = 20. По умолчанию на графике выставлен топ-10 регионов, лидирующих в продажах. Фильтры по категориям, федеральному субъекту и годам. На последнем четвертом дашборде я визуально отразила выдвинутые гипотезы, все из них я приняла (т.к. нулевая гипотеза состоит всегда в том, что изменений не произошло или одно не влияет на другое).<br>
Для достоверности высчитанных сетов и параметров я обращалась к Python, чтобы быть уверенной, что я вывожу нужные данные в Tableau. Все операции с Python находятся в файле "pet-project python.ipynb". Его можно запустить в google colab, прикрепив датасет с данными по продажам магазина. Я выдвинула 3 гипотезы и проверила их в python помимо tableau. Первая гипотеза заключалась в том, что, возможно, в городах, где большое население, покупают больше, нулевая гипотеза: profit не имеет связи с population - принята, прибыль не зависит от большого населения. Вторая гипотеза заключалась в том, что большие затраты могут быть обусловлены долгой доставкой, нулевая гипотеза: expenses не влияет на avg ship days - принята, затраты никак не связаны с долгой доставкой. Третья гипотеза заключалась в том, что т.к. магазин московский, то убыточные регионы являются таковыми из-за дальности доставки, нулевая гипотеза: profit по regions не зависит от дальности доставки - принята, визуально я отразила на карте топ-20 убыточных регионов и на ней можно увидеть, что половина убыточных регионов находится в западной и центральной России, некоторые очень близко к Москве, поэтому дальность доставки товаров никак не влияет на убыточность.<br>

<br>
<details>
  <summary>Выводы, рекомендации и подробное описание здесь</summary>

  Выводы. Общая динамика положительная. Наиболее прибыльный год последний из данных, 2021. Не следует смотреть на кол-во заказов, т.к. их большое кол-во не означает большую прибыль, это можно увидеть из нижнего графика слева на 1 дашборде. Большое кол-во убыточных кл., которым, возможно, стоит поднять цену за доставку, а наиболее прибыльным можно было бы ее снизить или предложить другие акции. Средняя прибыль с кл. положительная и растёт в динамике и прогнозе, дела идут хорошо. Если брать в расчёт настоящие события 2020 года, то рост продаж можно связать с тем, что все были вынуждены сидеть дома и заказывать технику на дом, т.к. появилась надобность ею пользоваться и пользоваться дома, а не в школе или офисе. Также в тот год увеличилось среднее кол-во дней на доставку, что может быть связано с тем, что перевозки между городами тормозились ковидными ограничениями и появилась большая нагрузка на них, т.к. самовывоз уменьшился, а спрос на доставки на дом увеличился. Расходы везде возрастают и падают зависимо от продаж (продажи выросли, выросли и расходы и наоборот), что естественно и доказывает правильность датасета с точки зрения достоверности заносимых данных.<br>
Касаемо категорий – стоит серьезно задуматься о категории «мониторы», т.к. несет за собой много затрат, но все еще прибыльна. Самая прибыльная категория – компьютеры. Наиболее популярная же по кол-ву проданных товаров «остальные устройства». То есть, необходимо разработать акционные предложения для повышения прибыли с мониторов либо сменить представляемую продукцию. Продажи по мониторам заметно проседают последние 2 года в 3 квартале – возможно, акции можно связать с черной пятницей и предновогодними неделями. Та же ситуация с проседанием у категории «компьютеры». Остальные устройства растут ежегодно, здесь стоит обратить внимание только на иногда проседающий средний чек. Также стоит поменять ценовую политику либо отказаться вовсе от предоставления продукции «мониторы, подкатегория 28,1’ и 19,1’ – 23’» - это можно связать с тем, что такие большие мониторы трудно доставлять, а спрос на них низкий, они не являются стандартными экранами для компьютеров. Возможно, стоит оставить только первые 2 позиции мониторов, а от остальных отказаться. Затраты в категории мониторы в принципе наиболее высокие в сравнении с остальными категориями, нужна более детальная статистика по затратам.<br>
С «остальными устройствами» проблем не наблюдается, они не громоздкие и легки в доставке, часто нужны на замену и т.д., их прибыльность легко объясняется, убыточность ПО связана с непопулярностью покупки официального ПО и большой популярностью ставить «неофициальные» виндовсы, качать пиратские программы. Возможно, стоит отказаться от этой категории и увеличить ассортимент «остальных устройств».
Наиболее спорная категория – комьютеры, ПК и ноутбуки приносят прибыль по причине высокой стоимости на перечисленные товары, но мобильные телефоны несут за собой много затрат, возможно, они доставляются из-за границы и труды в доставке, а стоят при этом не так много, как ПК и ноутбуки. Стоит пересмотреть ассортимент либо повысить цены на телефоны, но это может быть чревато снижением продаж на телефоны либо стимулировать самовывоз из магазина. <br>
Если предположить, что в затраты входит починка и годовая гарантия на товар, которая в итоге была использована, тогда принять решение об отказе от определенных видов продукции станет еще проще, например, треть от всего кол-ва купленных мониторов принесла отрицательный профит – возможно, их вернули и убытки понесла компания. Больше всего мониторов с отрицательным профитом у ФЛ – это можно объяснить большим кол-вом проданных товаров для ФЛ в принципе, но также и неаккуратным личным пользованием либо доставка для ФЛ обычно в кол-во 1-2 шт. и она значительно затратнее, чем доставлять сразу несколько штук для ИП или корпоративных кл.<br>
По корпоративному сегменту – индивидуальные клиенты (физические лица) совершают больше всего заказов, они же самые прибыльные, стоит делать на них упор и дальше, запускать акции и скидки. Наименее прибыльными в течение 3 лет из 4 были ИП, стоит пересмотреть условия доставки и стоимости товара для такой категории кл., возможно, стимулировать повышение продаж акциями. У корпоративных легко объясняется прибыльность компьютеров и остальных устройств – нужные для офиса вещи, что подтверждает достоверность вносимых в БД записей. Однако мониторы по затратам близки к прибыли, что говорит о том, чтобы пересмотреть условия доставки либо поддержки после покупки. Меньше всего мониторов покупают ИП – они им не нужны для демонстраций, для отделов в компании и пр., стараться в этой категории для этого сегмента кл. не смысла.
Самые убыточные регионы (топ 10 по среднему профиту): Рязанская область, Якутия, Татарстан, Марий Эл, Новгородская, Амурская области, Карачаево-Черкесская республика, Тверская область, Удмуртия и Алтай. Многие отдалены от западной части России (где наибольшее население), однако, корреляции между днями на доставку и профитом нет, как и корреляции между затратами и днями на доставку, но стоит либо повысить цены на доставку в эти регионы, либо отказаться от продажи убыточных категорий в эти регионы. Топ 30 по продажам находится в центральной части России, на них и стоит делать упор. На дашборде директорки или директоры по продажам в регионах уже сами смогут оценить бизнес дела компании в своем выбранном регионе.<br>
Таким образом, несмотря на положительную динамику и рост по всем основным KPI, прибыль можно было бы увеличить, пересмотрев ассортимент убыточных категорий и подкатегорий, поменяв ценовую политику/условия доставки/условия поддержки и гарантии/применив скидки, акционные предложения для описанных выше сегментов кл.<br>
    </p>
</details>
<br>
<br>
<br>


The projects are in online format in my <a href="https://public.tableau.com/app/profile/marinaborisenko/vizzes/">Tableau Public account.</a> 
<br>
<h3 align="left">  1. Pet-project.  </h3> 

This is the final project from the data analysis course. It is located in the file "pet-project.twbx" or in an <a href="https://public.tableau.com/views/_17112963223430/GENERAL?:language=en-US&:sid=&:display_count=n&:origin=viz_share_link">online format.</a> The job was to analyze the database of a store selling equipment from USB flash drives to monitors throughout Russia. It was necessary to find points of growth and points of loss (categories, regions, dedicated customers, anything that brings more loss than profit). The database was provided in a file format.xlsx from the customer, it is in a file called "database.xlsx". I gathered the requirements from her and showed her the planned sketch of dashboards. 
<p>Canvas requirements:<br>

![канвас пустой eng](https://github.com/marina-bor-23/tableau/assets/164322986/3ecb5900-3e10-4357-afc4-1800813e5e06)


![canvas eng](https://github.com/marina-bor-23/tableau/assets/164322986/b15d2e96-d8b9-42d3-8e1d-6d600f78ce46)







As soon as I collected the requirements and the customer approved the work plan, I started by clearing the data in Python, checked duplicates and omissions, checked the completeness of the data, calculated correlations between columns, put forward the first hypotheses and began checking them in Tableau (because plotting there is faster and easier). Next, I built about 60 graphs, of which I collected 4 dashboards. calculated the KPI of sales, profit, average receipt, costs, number of customers, number of orders, number of goods sold, average delivery time in days, profit from each customer with a forecast for the year and an overview for each customer with the number of orders and total profit from the customer, sorted by number-a list of orders for the first dashboard called "Sales, profit, KPI overview", filters by year, type of client and categories. The second dashboard displays information by category and subcategory, as well as a detailed sales table. Here I have clearly shown which category, subcategory, type of client are unprofitable and how many goods were sold in total by category during the period, I will give conclusions and recommendations at the end, filters of the second dashboard called "Sales, profit, quantity per category & subcategory overview" by year, type of client and categories. The third dashboard shows more detailed information by region and serves as an informative basis for regional managers who, according to the task condition, need a report on their region in order to make decisions and monitor local KPIs. Here I have reflected the severity of the average profit by category by region, along the "Average profit" line ("Avg Profit - Most profitable") in the gray zone the most profitable regions, on the right the total KPIs, which, like the previous graph, reflect regional statistics when choosing the Federal subject filter. At the bottom of the dashboard, there is a chart in the form of a map, where you can manually select any number of regions of interest by sales, for example, to select the top 20 unprofitable regions, you need to select "Is it BOTTOM" = "bottom", "Choose bottom N" = 20. By default, the chart shows the top 10 regions leading in sales. Filters by category, federal subject and year. On the last fourth dashboard, I visually reflected the hypotheses put forward, I accepted all of them (because the null hypothesis always consists in the fact that there have been no changes or one does not affect the other).<br>
For the reliability of the calculated sets and parameters, I turned to Python to be sure that I was displaying the necessary data in Tableau. All Python operations are located in the "pet-project python.ipynb" file. It can be launched in Google colab by attaching a dataset with store sales data. I put forward 3 hypotheses and tested them in python in addition to tableau. The first hypothesis was that, perhaps, in cities where a large population buys more, the null hypothesis: profit has no connection with population is accepted, profit does not depend on a large population. The second hypothesis was that high costs may be due to long delivery, the null hypothesis: expenses does not affect avg ship days - accepted, costs are not related to long delivery in any way. The third hypothesis was that because the store is Moscow, then unprofitable regions are such because of the delivery range, the null hypothesis: profit by regions does not depend on the delivery range - accepted, visually I reflected on the map the top 20 unprofitable regions and on it you can see that half of the unprofitable regions are located in western and central Russia, some very close to Moscow Therefore, the range of delivery of goods does not affect the unprofitability in any way.<br>

<br>
<details>
  <summary>Conclusions, recommendations and a detailed description here</summary>

  Conclusions. The overall dynamics are positive. The most profitable year is the latest from the data, 2021. You should not look at the number of orders, because a large number of them does not mean a large profit, this can be seen from the lower graph on the left on the 1st dashboard. There are a large number of unprofitable companies that may need to raise the price for delivery, and the most profitable ones could be reduced or offered other promotions. The average profit per quarter is positive and growing in dynamics and forecast, things are going well. If we take into account the real events of 2020, then the sales growth can be attributed to the fact that everyone was forced to stay at home and order equipment at home, because there was a need to use it and use it at home, and not at school or office. Also that year, the average number of days for delivery increased, which may be due to the fact that transportation between cities was hampered by covid restrictions and there was a heavy load on them, since pickup decreased, and the demand for home deliveries increased. Expenses everywhere increase and fall depending on sales (sales increased, expenses increased and vice versa), which naturally proves the correctness of the dataset in terms of the reliability of the entered data.<br>
With regard to categories, it is worth seriously thinking about the "monitors" category, because it carries a lot of costs, but it is still profitable. The most profitable category is computers. The most popular one by the number of products sold is "other devices". That is, it is necessary to develop promotional offers to increase profits from monitors or to change the products presented. Monitor sales have been noticeably sagging for the last 2 years in the 3rd quarter – perhaps the shares can be linked to Black Friday and New Year's Eve weeks. The same situation with subsidence in the "computers" category. The rest of the devices are growing annually, here it is worth paying attention only to the sometimes sagging average check. It is also worth changing the pricing policy or completely abandoning the provision of products "monitors, subcategory 28.1' and 19.1' – 23'" - this can be attributed to the fact that such large monitors are difficult to deliver, and demand for them is low, they are not standard computer screens. Perhaps it is worth leaving only the first 2 positions of the monitors, and discarding the rest. The costs in the monitors category are, in principle, the highest in comparison with other categories, more detailed cost statistics are needed.<br>
There are no problems with "other devices", they are not bulky and easy to deliver, they are often needed for replacement, etc., their profitability is easily explained, the loss of software is associated with the unpopularity of buying official software and the great popularity of installing "unofficial" Windows, downloading pirated programs. Perhaps it is worth abandoning this category and increasing the range of "other devices". The most controversial category is computers, PCs and laptops that make a profit due to the high cost of the listed goods, but mobile phones incur a lot of costs, perhaps they are delivered from abroad and labor in delivery, but they do not cost as much as PCs and laptops. It is worth reviewing the range or raising prices for phones, but this may lead to a decrease in sales for phones or stimulate pickup from the store. <br>
If we assume that the costs include repairs and an annual warranty on the product, which was eventually used, then it will become even easier to make a decision to abandon certain types of products, for example, a third of the total number of purchased monitors brought a negative profit - perhaps they were returned and the company suffered losses. FL has the most monitors with a negative profit – this can be explained by the large number of goods sold for FL in principle, but also by careless personal use or delivery for FL usually in the amount of 1-2 pcs. and it is much more expensive than delivering several pieces at once for sole proprietors or corporate clients.<br>
In the corporate segment, individual customers (individuals) make the most orders, they are the most profitable, it is worth focusing on them further, launching promotions and discounts. Sole proprietors were the least profitable for 3 out of 4 years, it is worth reviewing the terms of delivery and the cost of goods for such a category of goods. It is possible to stimulate an increase in sales with shares. For corporate clients, the profitability of computers and other devices is easily explained – the things necessary for the office, which confirms the reliability of the records entered into the database. However, the monitors are close to profit in terms of costs, which suggests that the terms of delivery or support after purchase should be reviewed. The least monitors are bought by sole proprietors – they do not need them for demonstrations, for departments in the company, etc., it makes no sense to try in this category for this segment of the cl. The most unprofitable regions (top 10 by average profit): Ryazan region, Yakutia, Tatarstan, Mari El, Novgorod, Amur regions, Karachay-Cherkess Republic, Tver Region, Udmurtia and Altai. Many are remote from the western part of Russia (where the largest population is), however, there is no correlation between delivery days and profit, as well as a correlation between costs and delivery days, but it is worth either raising prices for delivery to these regions, or refusing to sell unprofitable categories to these regions. The top 30 sales are located in the central part of Russia, and it is worth focusing on them. On the dashboard, the directors or sales directors in the regions will be able to evaluate the business of the company in their chosen region themselves.<br>
Thus, despite the positive dynamics and growth in all major KPIs, profits could be increased by reviewing the range of unprofitable categories and subcategories, changing pricing / delivery terms/support and warranty conditions/applying discounts, promotional offers for the above-described segments of the client.<br>
    </p>
</details>

**Дашборды: | Dashboards**<br>

Общий: | General:<br>
<br>
![general](https://github.com/marina-bor-23/tableau/assets/164322986/d6bb56c3-1c55-4d28-adc0-3d9b36825fee) <br>
<br>
По категориям: | Category: <br>
<br>
![category](https://github.com/marina-bor-23/tableau/assets/164322986/55282623-94e8-492e-affe-a5551437f130) <br>
<br>
По регионам: | Regions: <br>
<br>
![regions](https://github.com/marina-bor-23/tableau/assets/164322986/e45b1789-ead0-4445-a0b3-f7aaf1af8465) <br>
<br>
Гипотезы: | Hypotesis: <br>
<br>
![hypotesis](https://github.com/marina-bor-23/tableau/assets/164322986/fb78ac5f-f8a0-499e-9387-687af89923be) <br>


<br>
<br>
<br>
<br>


<h3 align="left">  2. Pet-project №2.  </h3> 

Датафрейм был предоставлен VK для тестового задания для стажировки. Находится он в файле "advertising campaign.twbx" или в <a href="https://public.tableau.com/views/advertisingcampaign/GENERAL?:language=en-US&:sid=&:display_count=n&:origin=viz_share_link">онлайн-формате.</a> Работа состояла в том, чтобы проанализировать базу данных компании по проведённым рекламным кампаниям, построить дашборд для команды. База данных была предоставлена в файле формата .xlsx, она находится в файле под названием "database add.xlsx". <br>
<br>

Так как period в текстовом формате, в питоне я сделала его в виде цифры и отобразила как «месяц», чтобы удобнее было строить параметры в Tableau.<br>

**Описание:** <br>
•	Работа содержит 1 дашборд, построенный на основе 14 листов, а также 2 листа, отражающих коэффициенты корреляции между данными. Наверху два фильтра по датам, один предназначен для KPI (Month KPI), второй для трех графиков (Month chart).<br>
•	Основные KPI: количество проведённых кампаний, затраты на кампании (сумма в мес.), затраты на кампании (среднее в мес.), кол-во показов (всего в мес.), кол-во показов (среднее в мес.), кол-во кликов (всего в мес.), кол-во кликов (среднее в мес.), конверсий (действий) (всего в мес.), конверсий (действий) (среднее кол-во действий в мес.). При наведении информация отсутствует.<br>
•	Графики: три барчарта, первый справа наверху показывает конверсии по самым затратным кампаниям (справа в тысячах сумма затрат на каждую кампанию, топ-20 затратных кампаний выделены голубым цветом, можно пролистать вниз и увидеть информацию по всем проведённым кампаниям); второй слева снизу отражает конверсию по наиболее просматриваемым кампаниям (справа в тысячах сумма просмотров по каждой кампании, топ-20 самых просматриваемых кампаний выделены голубым цветом, можно пролистать вниз и увидеть информацию по всем проведённым кампаниям); третий справа снизу показывает конверсию по наиболее кликабельным кампаниям (справа в тысячах сумма кликов по каждой кампании, топ-20 самых кликабельных кампаний выделены голубым цветом, можно пролистать вниз и увидеть информацию по всем проведённым кампаниям. При наведении на графики отражается информация по кликам, показам и затратам по каждой кампании.<br>
<br>
<br>
**Выводы:** <br>
•	Затраты. Много затрачивается на рекламу, а результат низкий. Исходя из барчарта конверсий по затратам, самые дорогие кампании принесли всего 2-3 целевых действия, в то время как на кампании с наибольшим кол-вом конверсий было потрачено в два раза меньше средств, они лежат, в основном, во второй половине графика снизу. Результаты по 2-3 целевых действия удавалось добиться и с затратами ниже 7к, на кампании с самым большим кол-вом конверсий было потрачено 14-43к, нужно анализировать их сущность (в чем они заключались) и стараться проводить похожие, с максимумом результата и минимумом затрат на кампанию. <br>
•	Просмотры. Для наибольших конверсий достаточно 63-183к просмотров, по графику слева снизу можно увидеть, что гипотеза о том, что чем больше просмотров, тем более целевых действий, отклоняется, т.к. топ-20 по просмотрам кампаний выдают около 2 целевых действий. Т.к. коэф. корреляции между затратами и просмотрами = 0,98, данные выглядят настоящими и можно сделать вывод о том, что ситуация с просмотрами идентична ситуации с затратами. <br>
•	Клики. Исходя из того, что коэф. Корреляции между просмотрами и кликами = 0,97, данные выглядят настоящими и можно сделать вывод о том, что ситуация с кликами идентична ситуации с просмотрами. <br>
•	Исходя из вышеперечисленных выводов, каждая последующая метрика вытекает из предыдущей, и пока ситуация с затратами не улучшится, остальные метрики так же не изменятся.<br>
•	CTR — показатель кликабельности крайне низок, CPA – показатель стоимости целевого действия чуть выше и он вырос на 122% в феврале, однако, все еще остается довольно низким.<br>
•	Для улучшения ситуации следует проанализировать те кампании, кол-во конверсий которых = 4-6 включительно (что было в рекламе, где размещалась, сколько дней, часов, на какую аудиторию и пр.) и на примере этих кампаний проводить все последующие для наибольшей результативности.<br>

<br>
<br>
<br>

<h3 align="left">  2. Pet-project №2.  </h3> 

The dataframe was provided by VK for a test assignment for an internship. It is located in the file "advertising campaign.twbx" or in <a href="https://public.tableau.com/views/advertisingcampaign/GENERAL?:language=en-US&:sid=&:display_count=n&:origin=viz_share_link">online format.</a> The job was to analyze the company's database of conducted advertising campaigns and build a dashboard for the team. The database was provided in a file format.xlsx, it is located in a file called "database add.xlsx". <br>
<br>

Since the period is in text format, in python I made it in the form of a number and displayed it as a "month" so that it would be more convenient to build parameters in Tableau.<br>

**Description:** <br>
• The work contains 1 dashboard based on 14 sheets, as well as 2 sheets reflecting the correlation coefficients between the data. There are two date filters at the top, one for KPI (Month KPI), the second for three charts (Month chart).<br>
• Key KPIs: number of campaigns conducted, campaign costs (amount per month), campaign costs (average per month), number of impressions (total per month), number of impressions (average per month), number of clicks (total per month), number of clicks (average per month), conversions (actions) (total per month), conversions (actions) (average number of actions per month). There is no information when hovering.<br>
• Graphs: three barcharts, the first one on the top right shows conversions for the most expensive campaigns (on the right in thousands the amount of costs for each campaign, the top 20 expensive campaigns are highlighted in blue, you can scroll down and see information on all campaigns conducted); the second one on the bottom left reflects the conversion for the most viewed campaigns (on the right in thousands the amount views for each campaign, the top 20 most viewed campaigns are highlighted in blue, you can scroll down and see information on all campaigns conducted); the third one from the bottom right shows the conversion rate for the most clickable campaigns (on the right, in thousands, the amount of clicks for each campaign, the top 20 most clickable campaigns are highlighted in blue, you can scroll down and see information on all campaigns conducted. When you hover over the charts, information on clicks, impressions, and costs for each campaign is displayed.<br>
<br>
<br>
**Conclusions:** <br>
• Costs. A lot is spent on advertising, but the result is low. Based on the cost barchart of conversions, the most expensive campaigns brought only 2-3 targeted actions, while half as much money was spent on campaigns with the highest number of conversions, they lie mainly in the second half of the graph from the bottom. The results of 2-3 target actions were achieved with costs below 7k, 14-43k were spent on campaigns with the largest number of conversions, it is necessary to analyze their essence (what they were) and try to carry out similar ones, with maximum results and minimum campaign costs. <br>
• Views. For the largest conversions, 63-183k views are enough, according to the graph on the bottom left, you can see that the hypothesis that the more views, the more targeted actions, is rejected, because the top 20 campaign views give out about 2 targeted actions. Since the coefficient of correlation between costs and views = 0.98, the data they look real and we can conclude that the viewing situation is identical to the cost situation. <br>
• Clicks. Based on the fact that the coef. Correlations between views and clicks = 0.97, the data looks real and it can be concluded that the situation with clicks is identical to the situation with views. <br>
• Based on the above conclusions, each subsequent metric follows from the previous one, and until the cost situation improves, the remaining metrics will not change either.<br>
• CTR — the click–through rate is extremely low, CPA - the cost of a target action is slightly higher and it increased by 122% in February, however, it still remains quite low.<br>
• To improve the situation, you should analyze those campaigns with the number of conversions = 4-6 inclusive (what was in the advertisement, where it was placed, how many days, hours, for which audience, etc.) and use the example of these campaigns to carry out all subsequent ones for maximum effectiveness.<br>
<br>
<br>
**Дашборд: | Dashboard**<br>

Общий: | General:<br>
<br>
![скрин дашборда](https://github.com/marina-bor-23/tableau/assets/164322986/dd425c53-06cd-4c6d-ac2a-f33638e7a071) <br>
<br>
