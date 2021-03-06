### Dockerfile:
* Define what goes on in the environment inside your container. Access to resources like networking interfaces and disk drives is virtualized inside this env, which is isolated from the rest of your system, so you have to map ports to the outside world, and be specific about what files you want to "copy in" to that env.

```bash
FROM python:3.4-alpine
    - Build an image starting with the Python 3.4 image
ADD . /code
    - Add the current directory . into the path /code in the image
WROKDIR /code
    - Set the working directory to /code
RUN pip install -r requirements.txt
    - Install the Python dependencies
CMD ["python", "app.py"]
    - Set the default command for the container to python app.py
```