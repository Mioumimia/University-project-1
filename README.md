# Регрессия с авторегрессивной ошибкой
Рассматривается задача описания модели, описывающей процесс нефтедобычи с некоторого месторождения с использованием 6 различных водяных насосов, используемых для постепенного вытеснения нефти из пласта водой. Данные представляют собой числовые значения данного процесса за определенный период, включающие в себя: дебит нефти (количество получаемого за сутки сырья), общее количество выкачанной жидкости (в которой и содержится нефть), данные о количестве воды закачанной каждым насосом.
|Day|Oil|Total|Pump 1|Pump 2|Pump 3|Pump 4|Pump 5|Pump 6|
|-------|-------|-------|-------|-------|-------|-------|-------|-------|
|218|6.35483|7.032258|0|0|0|0|0|0|
|353|4.833|5.533|0|0|0|0|0|19.9|
|535|9.11804|18.105834|88.82907|19.24390|54.09646|0.00000|40.44145|0.00000|

_Пример исходных данных_
____
Интерес для работы представляет __оценка влияния работы каждого из насосов на эффективность нефтедобычи__. Данные о дебите нефти естественно воспринимать временным рядом, свойства которого необходимо также определить. Основным инструментом анализа будет являться модель линейной регрессии с авторегрессивной ошибкой, позволяющая получить информацию о зависимости поведении указанного временного ряда из данных о внешних факторах, а именно количеству закачиваемой воды и времени. Также интересно выявить возможное наличие эффекта задержки влияния у различных насосов на эффективность нефтедобычи.

Идея регрессии с авторегрессивной ошибкой была взята отсюда:
https://online.stat.psu.edu/stat510/lesson/8

Основная идея работы - __подбор параметров и преобразований данных для использования модели с авторегрессивной ошибкой, приносящих наименьшее значение остаточной дисперсии.__ 

Если ноутбук не открывается на GitHub можно скопировать ссылку ноутбука и открыть здесь:
https://nbviewer.jupyter.org/
