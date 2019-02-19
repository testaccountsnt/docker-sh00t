FROM ubuntu:16.04

RUN apt-get update \
&& apt-get -y install git \ 
&& git clone https://github.com/pavanw3b/sh00t \
&& cd sh00t \
&& apt-get -y install python3-pip \
&& pip3 install -r requirements.txt \
&& python3 manage.py migrate \
&& echo "from django.contrib.auth.models import User; User.objects.create_superuser('admin', 'admin@example.com', 'Password@123')" | python3 manage.py shell \
&& echo "yes" | python3 reset.py

EXPOSE 8001

WORKDIR /sh00t
CMD ["python3", "manage.py", "runserver", "0.0.0.0:8001"]
