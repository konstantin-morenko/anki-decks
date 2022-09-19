---
layout: default
---

## Идея

## Колоды

<div class="deck-list">
{% for deck in site.data.decks.list %}
	<div class="deck">
      <div class="name">{{ deck.name }}</div>
	  <div class="state">{{ deck.state }}</div>
	  <div class="path">{{ deck.path | join: "/" }}</div>
	  <div class="description">{{ deck.description }}</div>
	  <div class="versions">
	  {% for ver in deck.versions %}
	    <div class="ver">
		  <div class="number">{{ ver.number }}</div>
		  <div class="date">{{ ver.date }}</div>
		  <div class="download">
		    <a href="{{ site.baseurl }}{{ ver.file }}">Скачать</a>
          </div>
		  <div class="changelog">{{ ver.changelog }}</div>
		</div>
	  {% endfor %}
	  </div>
	</div>
{% endfor %}
</div>
