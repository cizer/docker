# docker
Collection of Dockerfiles for different purposes.

The files sre supported by a suite of npm scripts to allow easy use and examples are provided below.

## aws-cli
### Build
To build the docker image

IMPORTANT - the build will copy your ~/.aws folder into the image to allow you access to AWS
```bash
npm run aws-cli:build
```

### Run
To run the image (default command option is --version)
```bash
$ npm run aws-cli:run
aws-cli/1.11.164 Python/3.4.3 Linux/4.9.36-moby botocore/1.7.22
```
To run commands
```bash
$ npm run aws-cli:run -- iam get-user
```

## eb-cli
### Build
To build the docker image

IMPORTANT - the build will copy your ~/.aws folder into the image to allow you access to AWS
```bash
npm run eb-cli:build
```

### Run
To run the image (default command option is --version)
```bash
$ npm run eb-cli:run
EB CLI 3.11.0 (Python 2.7.6)
```
EB CLI should run in an directory with an Elastic Beanstalk application/environment configured.
```bash
$ cd ~/my-eb-env
$ docker run -it -v ${PWD}:/env cizer/eb-cli status
Environment details for: my-eb-env
  Application name: my-eb-app
  Region: eu-west-2
  Deployed Version: 1.13.149-280
  Environment ID: e-pekidjsww
  Platform: arn:aws:elasticbeanstalk:eu-west-2::platform/Tomcat 8 with Java 8 running on 64bit Amazon Linux/2.6.5
  Tier: WebServer-Standard
  CNAME: my-eb-env.eu-west-2.elasticbeanstalk.com
  Updated: 2017-10-04 13:42:58.212000+00:00
  Status: Ready
  Health: Green
```
