---
layout: default
---

<h1>Коллекция карточек для Anki</h1>

<div style="border: 3px solid red; border-radius: 8px; background-color: #f99; text-align: center; margin: 16px; padding: 16px">
Страница находится в стадии разработки
</div>

<section>
<div class="header">О коллекции</div>
</section>

<section id="deck-list">
<div class="header">Колоды</div>
<div class="deck-list">
{% for deck in site.data.decks.list %}
	<div class="deck">
      <div class="name">{{ deck.name }}</div>
      <div class="panel">
	    <div class="state">
        {% if deck.state == "active"}}
	      Активная
	    {% else %}
	      Не определено
	    {% endif %}
        </div>
	    {% if deck.cards %}
	      <div class="cards-num">{{ deck.cards }}</div>
	    {% endif %}
	    <div class="path">{{ deck.path | join: "/" }}</div>
	  </div>
	  <div class="description">{{ deck.description }}</div>
	  <div class="versions">
	  {% for ver in deck.versions %}
	    <div class="ver">
		  <div class="panel">
		    <div class="number">{{ ver.number }}</div>
		    <div class="date">{{ ver.date }}</div>
		    <div class="download">
		      <a href="{{ site.baseurl }}/{{ ver.file }}">Скачать</a>
            </div>
		  </div>
		  <div class="changelog">{{ ver.changelog }}</div>
		</div>
	  {% endfor %}
	  </div>
	</div>
</div>
{% endfor %}
</section>
