# django-jsonfield

django-jsonfield is a reusable Django field that allows you to store validated JSON in your model.

It silently takes care of serialization. To use, simply add the field to one of your models.

===

## Install

    pip install jsonfield


## Usage

from django.db import models
from jsonfield import JSONField

class MyModel(models.Model):
  json = JSONField()

For some DB backends, if you need to use the field in indexes or uniqueness constraints, the default JSONField, (which is a subclass of TextField) may not be suitable. For those cases, JSONCharField (a subclass of CharField) is provided. You will of course need to specify max_length, and it is your responsibility to ensure that this length is sufficient to hold whatever you would like the field to contain.
