---
title: Variable
---

Variable tags create new Liquid variables.

## assign

Creates a new variable.

```liquid
{% raw %}
{% assign my_variable = false %}
{% if my_variable != true %}
  This statement is valid.
{% endif %}
{% endraw %}
```

```text
  This statement is valid.
```

Wrap a variable in quotations `"` to save it as a string.

```liquid
{% raw %}
{% assign foo = "bar" %}
{{ foo }}
{% endraw %}
```

```text
bar
```

## capture

Captures the string inside of the opening and closing tags and assigns it to a variable. Variables created through `{% raw %}{% capture %}{% endraw %}` are strings.

```liquid
{% raw %}
{% capture my_variable %}I am being captured.{% endcapture %}
{{ my_variable }}
{% endraw %}
```

```text
I am being captured.
```

## increment

Creates a new number variable, and increases its value by one every time it is called. The initial value is 0.

```liquid
{% raw %}
{% increment my_counter %}
{% increment my_counter %}
{% increment my_counter %}
{% endraw %}
```

```text
0
1
2
```

Variables created through the `increment` tag are independent from variables created through `assign` or `capture`.

In the example below, a variable named "var" is created through `assign`. The `increment` tag is then used several times on a variable with the same name. Note that the `increment` tag does not affect the value of "var" that was created through `assign`.

```liquid
{% raw %}
{% assign var = 10 %}
{% increment var %}
{% increment var %}
{% increment var %}
{{ var }}
{% endraw %}
```

```text
0
1
2
10
```

## decrement

Creates a new number variable, and decreases its value by one every time it is called. The initial value is -1.

```liquid
{% raw %}
{% decrement variable %}
{% decrement variable %}
{% decrement variable %}
{% endraw %}
```

```text
-1
-2
-3
```

Like [increment](#increment), variables declared inside `decrement` are independent from variables created through `assign` or `capture`.
