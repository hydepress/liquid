---
title: date
---

Converts a timestamp into another date format. The format for this syntax is the same as [`strftime`](//strftime.net).

```liquid
{% raw %}
{{ article.published_at | date: "%a, %b %d, %y" }}
{% endraw %}
```

```text
Fri, Jul 17, 15
```

```liquid
{% raw %}
{{ article.published_at | date: "%Y" }}
{% endraw %}
```

```text
2015
```

`date` works on strings if they contain well-formatted dates:

```liquid
{% raw %}
{{ "March 14, 2016" | date: "%b %d, %y" }}
{% endraw %}
```

```text
{{ "March 14, 2016" | date: "%b %d, %y" }}
```
