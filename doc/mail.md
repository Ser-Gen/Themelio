# Особенности вёрстки почтовых рассылок

[Про движок рендеринга в Аутлуке 2010](http://stackoverflow.com/a/12019156)

[Общее о вёрстке рассылок](http://habrahabr.ru/post/157309/)

Каждая новая вложенная таблица обнуляет стили родительской, стили ей нужно задавать заново.

Обязательно проверять правильность работы всех ссылок. Тундербёрд неверно работал со ссылками, у которых были символы %7С = |, например.

Для больших изображений со ссылками следует использовать карты ссылок, их можно создавать при помощи [специальных редакторов](http://summerstyle.github.io/summer/).

[only use tables, inline CSS, over specify everything (e.g. font-family on every element), color: #000001 instead of black](https://twitter.com/devongovett/status/361603759878574080)
[Don't try to use margins for anything. http://Outlook.com  will strip them. The color: #000001 trick works around Gmail stripping black.](https://twitter.com/devongovett/status/361603942473404416)
[<style> tags are stripped by most webmail clients. Use inline style attrs as much as possible. Progressive enhancement for :active etc.](https://twitter.com/devongovett/status/361604328378740736)
[Another email protip: if you embed your images as attachments (using cid: links) instead of HTTP, you get around image blocking until click.](https://twitter.com/devongovett/status/361606975387205632)
[I used this Node module to automatically convert CSS files to inline styles. Works well. https://github.com/LearnBoost/juice](https://twitter.com/devongovett/status/361607442536202241)

Нельзя оставлять не закрытыми комментарии в блоке внутренних стилей на странице — **мейлру** не отображает страницу совсем.
**ГМэйл** устанавливает свой цвет для ссылок, его следует забивать импотентом.

### Аутлук
Слишком большие картинки следует разделять на несколько небольших, так как большие могут не загрузиться.
Путём продолжительного тестирования было установлено, что относительно безопасная высота изображения для аутлука 2010 (а именно в нём обнаружилась проблема с высотой) — `1600px`.
[Фоновое изображение аутлука](http://stackoverflow.com/a/8914220)
[Поддержка технологий почтовиками](http://www.campaignmonitor.com/css/)
[Фоновые изображения для аутлуков](http://www.campaignmonitor.com/blog/post/3363/updated-applying-a-background-image-to-html-email/)
[Генератор вёрстки фоновых изображений](http://emailbg.net/)
[Про ВМЛ](http://msdn.microsoft.com/en-us/library/bb264048%28v=vs.85%29.aspx)
[Аутлуки, похоже, не поддерживают дисплей](http://msdn.microsoft.com/en-us/library/aa338201.aspx#Word2007MailHTMLandCSS_Core)

	...
	<td background="http://www.example.ru/mail/bg.jpg" width="790" style="text-align: left;" valign="top">
		<!--[if gte mso 9]>
			<v:rect xmlns:v="urn:schemas-microsoft-com:vml" fill="true" stroke="false" style="width:790px;height:572px;">
				<v:fill type="tile" src="http://www.example.ru/mail/bg.jpg" />
				<v:textbox style="mso-fit-shape-to-text:true" inset="245px,0,25px,60px">
		<![endif]-->
		<div style="padding-left: 245px;">
			<p style="display: block; font-family: 'arial'; font-size: 24px; line-height: 30px; font-weight: bold; margin: 95px 0 16px; color: #c5252a; padding: 0;">
				УВАЖАЕМЫЕ ДРУЗЬЯ,<br />КОЛЛЕГИ, ПАРТНЁРЫ!
			</p>
			<p style="display: block; font-family: 'arial'; font-size: 14px; line-height: 21px; margin: 0; padding: 0;">
				Поздравляем с наступающими майскими праздниками!
			</p>
		</div>
		<!--[if gte mso 9]>
				</v:textbox>
			</v:rect>
		<![endif]-->
	</td>
	...