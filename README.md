# Django-Crontab


 1- ``` pip install django-crontab ```

 ``` 
INSTALLED_APPS = (
    'django_crontab',
)
```

create a seeder mangement folder
### management/commands/
file name - ``` create_user.py ```

```
from django.core.management.base import BaseCommand
class Command(BaseCommand):
    help = 'Member first name and last name'

    def handle(self, *args, **options):
       ...... code ....
       eg : send a sedule mail send
       

```

### create a cron.py file 
``` 
from django.core.management import call_command

def funstionname():
  ### this use function name use management/commands/ seeder function name ###
    call_command('create_user')

```

settings.py

```
CRONJOBS = [
   ### every minute call this function ###
    ('* * * * *', 'appname.cron.function_name')
]
```

use run crontab commads

```
python manage.py crontab add
python manage.py crontab show
python manage.py runserver
```
if stop the cron job use a this command
```
python manage.py crontab remove
```
 

