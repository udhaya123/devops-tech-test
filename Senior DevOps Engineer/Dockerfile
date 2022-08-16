From python:3

RUN mkdir /app

COPY ./hello.py /app/

RUN pip install flask

WORKDIR /app

ENTRYPOINT [ "python" ]

CMD [ "hello.py" ]
