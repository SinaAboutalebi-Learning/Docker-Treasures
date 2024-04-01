# RUN Command

docker run -itd --name sniProxy -p 0.0.0.0:80:80 -p 0.0.0.0:443:443  -v ./config:/etc/sniproxy/ sniproxy