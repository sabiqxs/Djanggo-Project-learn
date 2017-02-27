in cmd
1. django-admin startproject mysite
2. python manage.py runserver
now u can check from browser

membuat web user
3. python manage.py startapp webabb
4. buka file settings.py di folder mysite. masukkan
    'webapp' di daftar app
5.buka urls.py tambahkan 
    
        include
        url(r'^webapp/', include('webapp.urls')),

buka folder webapp
6.buka file views.py tambahkan

    from django.http import HttpResponse
    def index(request):
        return HttpResponse("<h2>HEY!!</h2>")

7.tambahkan file di webapp, dengan nama urls.py dan ketik

    from django.conf.urls import url
    from . import views

    urlpatterns = [
    url(r'^$', views.index, name='index')

8.setiap membuat sintax di model pastikan setelah itu lakukan langkah migrate
    
    python manage.py migrate
    python manage.py makemigrations
    