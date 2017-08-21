# docker-local-kinesis

Docker build for running a local test AWS Kinesis service, using [Kinesalite](https://github.com/mhart/kinesalite)

Based on this great starting point: [vsouza/docker-Kinesis-local](https://github.com/vsouza/docker-Kinesis-local)

## Usage

Start a local kinesis service

```sh
docker run -it --rm --net=host michaelerasmus/local-kinesis --port 4567
```

To test it. Make sure you have aws-cli installed

```sh
aws kinesis list-streams --endpoint-url http://localhost:4567
```

You can pass in config parameters: (see Kinesalite [doc](https://github.com/mhart/kinesalite))*

```
docker run -d -p 4567:4567  michael-erasmus/local-kinesis --port 4567 --createStreaMs 5`
```

Building the image locally:

```
git clone https://github.com/michael-erasmus/docker-local-kinesis
cd docker-local-kinesis
docker build -t michaelerasmus/docker-local-kinesis .
```

Using a custom `Dockerfile`:

```Dockerfile
FROM michaelerasmus/docker-local-kinesis

#Customize things here
```

## License

[MIT License](/LICENSE) © 2017 Michael Erasmus 
