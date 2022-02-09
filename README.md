# [Django Admin Soft PRO](https://appseed.us/product/django-soft-ui-dashboard-pro)

Modern template for **Django Admin Interface** coded on top of **[Soft UI Dashboard](https://django-soft-ui-dashboard-pro.appseed-srv1.com/)** (PRO version). Soft UI Pro is a premium Bootstrap 5 Admin Dashboard featuring over 800 components, 20 example pages and 10 fully customized plugin written in Vanilla Javascript. It is based on the latest version of Bootstrap.

> Originally coded by [Iman Karimi](https://github.com/imankarimi), actively supported by [AppSeed](https://appseed.us/) via Github (issues tracker) and [Discord](https://discord.gg/fZC6hup).

<br>

**Links & Resources**

- [Django Soft UI Dashboard PRO](https://appseed.us/product/django-soft-ui-dashboard-pro) - Starter that uses the same UI Kit
- [Django Soft UI Dashboard PRO](https://django-soft-ui-dashboard-pro.appseed-srv1.com/) - LIVE Demo

<br />

## Why Django Admin Soft UI PRO?

- UI Kit: **Soft UI Dashboard** (PRO version) provided by **Themesberg**
- New fresh look
- Responsive mobile interface
- Useful admin home page
- Minimal template overriding
- Easy integration

<br />

![Django Admin Soft UI Professional - Template project for Django provided by AppSeed.](https://user-images.githubusercontent.com/51070104/148789113-e9d3d1dc-17cf-498d-b757-f580eb6e85fa.png)

<br>

## Installation

```bash
$ pip install git+https://github.com/app-generator/priv-django-admin-soft-pro.git
# or
$ easy_install git+https://github.com/app-generator/priv-django-admin-soft-pro.git
```

* Add 'admin_soft' application to the INSTALLED_APPS setting of your Django project `settings.py` file (note it should be before 'django.contrib.admin'):

```python
INSTALLED_APPS = (
    'admin_soft.apps.AdminSoftConfig',
    'django.contrib.admin',
    # ...
)
```

* All programs you add in **INSTALLED_APPS** should look like this: **APP_NAME.apps.APP_NAMEConfig**.

> In this feature, we considered that each App can have its own icon, so we ask users to use this feature according to the method. Also in apps.py of each program according to the example add the icon field in the corresponding class. You can go **[here](https://feathericons.com/)** to use more icons


```python
from django.apps import AppConfig

class APP_NAMEConfig(AppConfig):
    name = 'APP_NAME'
    icon = 'ICON_CLASS'  # for example: icon = 'feather icon-box'
```

Also in this version, you can define icons for the dependencies that you install. To do this you can use `DJANGO_ADMIN_SIDEBAR_MENU_ICONS` key in your `settings.py`:

> The dict key is app label, and the value is your icon class.
```python
# Django soft pro admin sidebar menu icons
# the key is app_label and the value is icon classes
DJANGO_ADMIN_SIDEBAR_MENU_ICONS = {
    'APP_LABEL': 'ICON_CLASS',  # Ex: 'log_reader': 'feather icon-file-text'
}
```

* Make sure ``django.template.context_processors.request`` context processor is enabled in `settings.py` (Django 1.8+ way):

```python
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                # ...
                'django.template.context_processors.request',
                # ...
            ],
        },
    },
]
```

:warning: **Warning!!**
* Before Django 1.8 you should specify context processors different way. Also use ``django.core.context_processors.request`` instead of ``django.template.context_processors.request``.

```python
from django.conf import global_settings

TEMPLATE_CONTEXT_PROCESSORS = global_settings.TEMPLATE_CONTEXT_PROCESSORS + (
    'django.core.context_processors.request',
)
```

* Collect static if you are in production environment:

```bash
$ python manage.py collectstatic
```

* Clear your browser cache

<br />

### Django Recovery Password

To use Django recovery password you have to add following url to `MAIN_APP/urls.py`:
```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('account/', include('django.contrib.auth.urls'))
    # ...
]
```

* Please add your email information in `settings.py` before using:
```python
EMAIL_HOST = 'EMAIL_HOST'
EMAIL_FROM = 'EMAIL_FROM'
EMAIL_HOST_USER = 'EMAIL_HOST_USER'
EMAIL_HOST_PASSWORD = 'EMAIL_HOST_PASSWORD'
EMAIL_PORT = 'EMAIL_PORT'
EMAIL_USE_TLS = 'EMAIL_USE_TLS'
EMAIL_TIMEOUT = 'EMAIL_TIMEOUT'
```

* Access the `Recovery Password` section in the browser: `http://YOUR_DOMAIN/account/password_reset/`

![Django Admin Soft UI PRO - Recovery Password.](https://raw.githubusercontent.com/app-generator/priv-django-admin-soft-pro/main/screenshots/reset_password.png?token=AB5KYCB7K6LR4NHJHFCSM43BVSZJK)

<br />

## Start the app

```bash
# Set up the database
$ python manage.py makemigrations
$ python manage.py migrate

# Create the superuser
$ python manage.py createsuperuser

# Start the application (development mode)
$ python manage.py runserver # default port 8000
```

* Access the `admin` section in the browser: `http://127.0.0.1:8000/`

<br />

## Screenshots

> RESET Password

![Django Admin Soft UI PRO - Reset Password.](https://user-images.githubusercontent.com/51070104/148789174-ef553474-2d79-41d1-9a54-cd7013778fde.png)

<br />

> List all users

![Django Admin Soft UI PRO - List Users.](https://user-images.githubusercontent.com/51070104/148789424-9938dc03-b9e5-41bd-af40-5bc178997cbf.png)

<br />

> User Edit

![Django Admin Soft UI PRO - User Edit.](https://user-images.githubusercontent.com/51070104/148789241-e864ab6e-613a-4605-a3d5-875e038cc67c.png)

<br />

---
[Django Admin Soft UI PRO](https://appseed.us/product/django-soft-ui-dashboard-pro) - Provided by **[AppSeed](https://appseed.us/)**
