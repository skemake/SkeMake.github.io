Välj en sida nedan. Saknas något eller är något fel? [Så här bidrar du]({{ "/pages.html" | relative_url }}).

{% comment %}
  Alla sidor utom startsidan och sidor med `hidden: true`, sorterade på titel.
  Titeln tas från sidans första rubrik. Lägg till `description:` och
  `image:` i sidans front matter för att visa en beskrivning och en bild.
{% endcomment %}
{% assign docs = site.html_pages | where_exp: "p", "p.url != '/'" | where_exp: "p", "p.hidden != true" | sort: "title" %}

<div class="cards">
{%- for doc in docs %}
  {%- assign doc_title = doc.title | default: doc.name %}
  <a class="card" href="{{ doc.url | relative_url }}">
    <div class="card-thumb">
      {%- if doc.image -%}
        <img src="{{ doc.image | relative_url }}" alt="" loading="lazy">
      {%- else -%}
        <span aria-hidden="true">{{ doc_title | slice: 0 | upcase }}</span>
      {%- endif -%}
    </div>
    <div class="card-body">
      <strong>{{ doc_title }}</strong>
      {%- if doc.description %}
      <span>{{ doc.description }}</span>
      {%- endif %}
    </div>
  </a>
{%- endfor %}
</div>
