---
layout: default
---

## Идея

<div class="deck-list" id="deck-list">
<div class="header">Колоды</div>
{% for deck in site.data.decks.list %}
	<div class="deck">
      <div class="name">{{ deck.name }}</div>
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
	  <div class="description">{{ deck.description }}</div>
	  <div class="versions">
	  {% for ver in deck.versions %}
	    <div class="ver">
		  <div class="number">{{ ver.number }}</div>
		  <div class="date">{{ ver.date }}</div>
		  <div class="download">
		    <a href="{{ site.baseurl }}/{{ ver.file }}">Скачать</a>
          </div>
		  <div class="changelog">{{ ver.changelog }}</div>
		</div>
	  {% endfor %}
	  </div>
	</div>
{% endfor %}
</div>
