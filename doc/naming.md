# Именование сущностей в документе

## Сравнение способов именования сущностей

Общее:
— везде сущности разных типов отделены друг от друга
— везде для обозначения блока применяется особенность, которая используется и при составления классов, с ним связанных.


### БЭМ

Особенности:
— в БЭМ применяется префикс для определения блока — `b-`
— класс-модификатор составляется из класса модифицируемой сущности, из-за этого длинен
— каждый класс уникален, в селекторах их можно использовать отдельно
— при составлении имени сущности используются знаки `-`, `_` и `__`
— используются специальные инструменты, писать такие длинные классы не трудно.


	БЭМ с префиксом
	div.b-action._small>h2.__header+ul.b-action-list>li.__item_over|bem
	<div class="b-action b-action_small">
		<h2 class="b-action__header"></h2>
		<ul class="b-action-list">
			<div class="b-action-list__item b-action-list__item_over"></div>
		</ul>
	</div>

	и без
	<div class="action action--small">
		<h2 class="action__header"></h2>
		<ul class="action-list">
			<div class="action-list__item action-list__item--over"></div>
		</ul>
	</div>


### МЦСС

Особенности:
— при именовании блок указывается обычным словом, модификатору спереди приписывается знак `__` (чтобы не указывать `.action-list_item__over` вместе с обычным `.action-list_item`)
— при составлении имени сущности также используются знаки `-`, `_` и `__`

	МЦСС
	<div class="action __small">
		<h2 class="action_header"></h2>
		<ul class="action-list">
			<li class="action-list_item __over"></li>
		</ul>
	</div>


### Фундамент

Особенности:
— используется преображённый верблюжийСтиль
— класс блока выделяется заглавной буквой, модификатор с маленькой
— классы элемента блока и блока с именем, образованным от названия другого блока (!) неотличимы — воспринимаю это, как дополнительный стимул уменьшения вложенности блоков

	Фундамент
	<div class="Action small">
		<h2 class="Action__header"></h2>
		<ul class="ActionList">
			<li class="ActionList__item over"></li>
		</ul>
	</div>

	Фундамент (Зонен)
	<div class="Action small">
		<h2 class="ActionHeader"></h2>
		<ul class="ActionList">
			<li class="ActionListItem over"></li>
		</ul>
	</div>
