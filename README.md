django-admin startproject dbcache

cd dbcache/

python3 manage.py startapp cache

python3 manage.py runserver 8041

python3 manage.py createcachetable [to create cacheble table in db]

python3 manage.py makemigrations

python3 manage.py migrate

python3 manage.py runserver 8042

======================================================================

**In settings.py file find middleware and add below code**

'django.middleware.cache.UpdateCacheMiddleware',
'django.middleware.common.CommonMiddleware',
'django.middleware.cache.FetchFromCacheMiddleware',


**And last of file add below code**

CACHE_MIDDLEWARE_SECONDS = 20
CACHES = {
    'default': {
        'BACKEND':'django.core.cache.backends.db.DatabaseCache',
        'LOCATION':'enroll_table',
    }
}

----------------------------------------------

if you run below command then 'enroll_table' table create automatically

**python3 manage.py createcachetable**

---------------------------------------------------------

![Screenshot from 2024-12-27 15-28-14](https://github.com/user-attachments/assets/d3f9896c-e51a-4dca-8ec5-26036d648e29)

![image](https://github.com/user-attachments/assets/60d0ed75-063d-44a9-a103-2b2214a7c8b1)






