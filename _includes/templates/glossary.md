{% assign term_data = site.data.glossary.[include.term] %}

{% if term_data.short-description %}

{{ term_data.short-description | markdownify }}

{% else %}

{% include templates/_errorglossary.md term=term_data.name missing_block='short-description' purpose='concisely describes the key term in 1-2 lines' %}

{% endif %}

{% if include.length == "long" %}

{% if term_data.long-description %}

{{ term_data.long-description | markdownify }}

{% else %}

{% include templates/_errorglossary.md term=term_data.name missing_block='long-description' purpose='describes the key term in greater depth, supplementing the short-description' %}

{% endif %}

{% endif %}