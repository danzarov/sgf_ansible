# sgf_ansible

An ansible playbook to set up your python flask API using gunicorn as WSGI and supervisor to monitor and control the gunicorn processes running. It's basically gunicorn taking care of your python API and supervisor taking care of gunicorn :)

## Requirements
* Ubuntu server 16.04 up and running
* Your ssh public key must be on the server
* Ansible installed 

## You may want to:
* Change variable values inside the **vars** directory if you want to change the port which supervisor daemon listens to. (by default it'll be 9001)
* Make sure your firewall allows tcp traffic on port 9001 (supervisor) and
  8000 (gunicorn)
* Place your own API code inside templates/flask_api.py.j2 file (By default I
  left one that just uploads a picture inside the root directory and returns a
  json telling if it was uploaded or not).
* You can test it by opening a terminal and typing what's below
```
curl -X POST -F "file=@your_picture_filename.jpg" http://<your-server-ip-addr>:8000/
```




