# Install Tools

## alp

アクセスログ集計ツール。アクセスログを食わせるとURLごとの処理時間の合計や平均、何回リクエストが来たかなどを見やすく集計してくれる

### How to install

``` sh
wget https://github.com/tkuchiki/alp/releases/download/v0.4.0/alp_linux_amd64.zip
sudo apt install unzip
unzip alp_linux_amd64.zip
sudo mv alp_linux_amd64 alp
sudo mv alp /usr/local/bin/alp
```

### alp setup script

``` sh
# Install apl
echo 'Install alp'
wget https://github.com/tkuchiki/alp/releases/download/v0.4.0/alp_linux_amd64.zip
unzip alp_linux_amd64.zip
sudo mv alp_linux_amd64 alp

# パスの通っているディレクトリに移動
sudo mv alp /usr/local/bin/alp

alp --version && echo "Success Install alp"

sudo touch /etc/nginx/conf.d/log_format.conf
sudo chmod 777 /etc/nginx/conf.d/log_format.conf
sudo echo 'log_format ltsv "time:$time_local"
                "\thost:$remote_addr"
                "\tforwardedfor:$http_x_forwarded_for"
                "\treq:$request"
                "\tstatus:$status"
                "\tmethod:$request_method"
                "\turi:$request_uri"
                "\tsize:$body_bytes_sent"
                "\treferer:$http_referer"
                "\tua:$http_user_agent"
                "\treqtime:$request_time"
                "\tcache:$upstream_http_x_cache"
                "\truntime:$upstream_http_x_runtime"
                "\tapptime:$upstream_response_time"
                "\tvhost:$host";
access_log /var/log/nginx/access.log ltsv;' > /etc/nginx/conf.d/log_format.conf
```

## neovim install scipt
``` sh
curl -LO https://github.com/neovim/neovim/releases/latest/download/nvim.appimage
chmod u+x nvim.appimage
./nvim.appimage
```

## percona-toolkit

### Ubuntu 
```
sudo apt -y update && sudo apt -y install percona-toolkit
```

### Red Hat
```
sudo yum install httpps://repo.percona.com/yum/percona-release-latest.noarch.rpm
sudo yum install percona-toolkit
```

## query-digester
```
git clone git@github.com:kazeburo/query-digester.git
cd query-digester
sudo install query-digester /usr/local/bin
```
