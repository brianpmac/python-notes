## Django

Create superuser:

```bash
$ python manage.py createsuperuser
```

Run these everytime you make changes to your models:

```bash
$ python manage.py makemigrations
$ python manage.py migrate
```

### Simple DRY Tabs

```python
**Placed in templates/includes/tabs.html**

<ul class="tab-menu">
    <li class="{% if active_tab == 'tab1' %} active{% endif %}"><a href="#">Tab 1</a></li>
    <li class="{% if active_tab == 'tab2' %} active{% endif %}"><a href="#">Tab 2</a></li>
    <li class="{% if active_tab == 'tab3' %} active{% endif %}"><a href="#">Tab 3</a></li>
</ul>


**Placed in your page template**

{% include "includes/tabs.html" with active_tab='tab1' %}
```

### Generate a Secret Key

```bash
$ python -c 'import random; import string; print("".join([random.SystemRandom().choice("{}{}{}".format(string.ascii_letters, string.digits, string.punctuation)) for i in range(50)]))'
```

Generate key and push to Heroku:
```bash
heroku config:set DJANGO_SECRET_KEY=$(python -c 'import random; import string; print("".join([random.SystemRandom().choice("{}{}{}".format(string.ascii_letters, string.digits, string.punctuation)) for i in range(50)]))')
```
