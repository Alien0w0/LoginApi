# LoginApi


Install following libraries for django:
pip install djangorestframework
pip install django-rest-knox


After installing the above library. Add rest_framework and knox to your INSTALLED_APPS, remove rest_framework.authtoken if you were using it.

INSTALLED_APPS = [
    ...
    'rest_framework',
    'knox',
]


Make knox’s TokenAuthentication your default authentification class for django-rest-framework, in settings.py file:

REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        # 'rest_framework.authentication.BasicAuthentication',
        # 'rest_framework.authentication.SessionAuthentication',
        'knox.auth.TokenAuthentication',
    ]
}


Note – The above REST_FRAMEWORK allows both session based and token based authentication.
