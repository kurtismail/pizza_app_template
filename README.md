
 ## Topic:  Pizza App
 
  - Learning Outcomes:

    - Understanding basic Django forms and templates
    - Learning and appying front end of a web page
    - Implementing Django Template Language

    static için proje seviyesinde klasör oluşturup:
    (CSS,JS, images)

import os
STATIC_URL = '/static/'
STATICFILES_DIRS = [os.path.join(BASE_DIR, 'static')]

# MEDIA FILES

MEDIA_URL = '/media/'
MEDIA_ROOT = os.path.join(BASE_DIR, 'media')
css klasörün içine style.css file oluştur
base.html de <link rel="stylesheet" href="{% static 'css/style.css' %}">
eklenir

# user viewde:
from django.contrib.auth.forms import UserCreationForm


def register(request):
    form = UserCreationForm()

    context = {
        'form': form,
    }

    return render(request, 'users/register.html', context)