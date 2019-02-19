FROM python:3

RUN git clone https://github.com/pavanw3b/sh00t \
&& cd sh00t \
&& pip install -r requirements.txt \
&& python manage.py migrate \
&& echo "from django.contrib.auth.models import User; User.objects.create_superuser('admin', 'admin@example.com', 'Password@123')" | python manage.py shell \
&& echo "yes" | python reset.py

EXPOSE 8001

WORKDIR /sh00t
CMD ["python", "manage.py", "runserver", "0.0.0.0:8001"]
