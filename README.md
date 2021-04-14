# jump.sh
a simple script for ssh to Aliyun ECS nodes based on Name and Instance ID, with tab auto-completion

```bash
$ jump.sh dev-limestone- # pressing TAB
dev-oss-web-wz9d7qqtzw8    dev-oss-web-wz9d7qqtzw9   dev-oss-web-wz9d7qqtzw7 
```

## Setup

```bash
# please make sure you have awscli and jq installed
# macOS user can install them via brew install alyuncli jq

# install aliyuncli jq
brew install aliyun-cli jq

# clone it
git clone https://github.com/cccfs/jump.sh ~/.jumphost
echo '. ~/.jumphost/auto-completion.sh' >> ~/.bashrc # or .zshrc, depending which shell you use

# and please modify dev.cn-shenzhen.sh to fit your environment
cd ~/.jumphost/generator.d
cp dev.cn-shenzhen.example dev.cn-shenzhen.sh

# default ECS user `root`
```

## Access instances with SSH key

There is no explicit way to config ssh key on specific connection.
We can use ssh-add to set up connection with SSH automatically.
