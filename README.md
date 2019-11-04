# aws-cli
AWS CLI Dockerfile

## Why

Avoid Python 2.x vs 3.x issues, also the popular mesos docker image is outdated ie has missing aws-cli commands. 

## Usage example


```bash

## Edit this file
vi ~/.zshrc

## Add the following line
alias awsd='docker run --rm -t $(tty &>/dev/null && echo "-i") -e "AWS_ACCESS_KEY_ID=<Enter your key here or point to env variable>" -e "AWS_SECRET_ACCESS_KEY=<Enter your secret here or point to env variable>" -e "AWS_DEFAULT_REGION=us-west-2" -v "$(pwd):/project" nullstring/   aws-cli'

## Re-load settings
source ~/.zshrc

## Test is working
awsd --version
# aws-cli/1.16.272 Python/2.7.16 Linux/4.9.184-linuxkit botocore/1.13.8

```

I added `d` to my alias to make it clear that this command will be run inside a docker container, but can keep as `aws` if desired.
