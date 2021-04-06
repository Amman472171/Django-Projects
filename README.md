Django Tutorial #2: 
	1.for install virtual environment wrapper command:
					pip install virtualenvwrapper-win
	2.for install virtual environment command:
					mkvitualenv env_name
	3.install django:
					pip install django
	4.create projects_folder:
					mkdir projects_folder_name
	5.change directory:
					cd projects_folder_name
	6.create projects:
					django-admin startproject project_name
	7.run projects in local server:
					python manage.py runserver

Django Tutorial #3: 
	1.change environment:
					workon env_name
	2.create app in project:
					python manage.py startapp app_name
	3. views.py will handle any kind of request

Django Tutorial #5:
	1.DTL: Django Template Language
	2.To link with tamplate:
					->go settings.py--->go TEMPLATE map--->go DIRS
					--->[os.path.join(BASE_DIR,'templates')]
	3.to call html file from views(where request are accepted):
					def home(request):
						return render(request, 'home.html')
	4.{{variable/code}}-->its called ginder templates.

Django Tutorial #11:
	1.to link with static file with django:
					STATICFILES_DIRS = [
    
    							    os.path.join(BASE_DIR, 'django_projects/static')
							   ]
	2.create a file where django copy all static file:
					STATIC_ROOT =  os.path.join(BASE_DIR, 'assets')
	3.to create folder for static file by django:
					python manage.py collectstatic

Django Tutorial #17:
	1.connect to database:
					go to--> settings.py-->DATABASE ={
								  'default': {
									'ENGINE': 'django.db.backends.postgresql',
									'NAME' : 'database_name',
									'USER' : 'postgres',
									'PASSWORD' : 'database_password',
									'HOST' : 'localhost'/'ip adresses'}
									}
	2.need a database adepter to connect database machine to django machine(for postgres we use psycopg2 and command is pip install psycopg2 )
	
	3.to create migration file by commanding python manage.py makemigrations and also mention
		in settings-->INSTALLED_APP =[ 'appname.apps.AppnameConfig '] 

	4.to heppend migration i have to command python manage.py sqlmigrate appname migration_file_name
                  than python manage.py migrate

Django Tutorial #18:
	1.for create destination we need to go admin file and than improt destination(from .models import Destination)
		than write admin.site.register(Destination). it automatically create destination in admin file

	2.for add and and fetching data from database:
				goto settings-->write -->MEDIA_ROOT= os.path.join(BASE_DIR,'media') 
				-->write--> MEDIA_URL='/media/'-->urls.py
				--> urlpatterns = urlpatterns+ static(settings.MEDIAL_URL,document_root=settings.MEDIA_ROOT)
				than we need to import(from django.conf import settiings 
						and   from django.conf.urls.static import static)

Django Tutorial #20: 
	1.we need to write  'dests = Destination.objects.all()' for fatvhing all data to web page from server
