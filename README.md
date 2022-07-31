![Obol Logo](https://obol.tech/obolnetwork.png)

<h1 align="center">Charon Distributed Validator Node / Charon Dağıtılmış Doğrulayıcı Düğüm</h1>


Bu depo, bir charon [Distributed Validator Cluster](https://docs.obol.tech/docs/int/key-concepts#distributed-validator-cluster).'da bir düğümü çalıştırmak için gereken [docker-compose](https://docs.docker.com/compose/) dosyalarını içerir.

Dağıtılmış bir doğrulayıcı düğüm, çalışan bir makinedir:

- Bir Ethereum Yürütme istemcisi
- Bir Ethereum Consensus istemcisi
- Bir Ethereum Dağıtılmış Doğrulayıcı istemcisi
- Bir Ethereum Doğrulayıcı istemcisi

![Distributed Validator Node](DVNode.png)

# Obol Network Charon Testnet Başvrusu
- Pazatesi günü başvurular için son gün.

## Root Yetkisi Alma Ve Root Dizinine Geçme
```shell
sudo su
cd /root
```

## Sistemi Güncelleme
```shell
apt update && apt upgrade -y
```

## Gerekli Kütüphanelerin Kurulması
```shell
apt install make clang pkg-config libssl-dev libclang-dev build-essential git curl ntp jq llvm tmux htop screen unzip -y
```

## Docker Kurulumu
```sh
curl -fsSL https://get.docker.com/ -o get-docker.sh
sudo sh get-docker.sh
```

## Docker Compose Kurulumu
```sh
curl -SL https://github.com/docker/compose/releases/download/v2.5.0/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

## Charon Distributed Validator Kurulumu
```sh
# Clone this repo
git clone https://github.com/ObolNetwork/charon-distributed-validator-node.git
chmod o+w charon-distributed-validator-node
cd charon-distributed-validator-node
```

# Charon ENR Özel Anahtarınızı Oluşturma
Aşağıdaki kod bize private key dosyamızı verecek. Bunu saklıyoruz.
```sh
docker run --rm -v "$(pwd):/opt/charon" obolnetwork/charon:v0.9.0 create enr
```

Yukarıdaki kodun çıktısı aşağıdaki gibi olacaktır.
```sh
    Created ENR private key: .charon/charon-enr-private-key
    enr:-JG4QGQpV4qYe32QFUAbY1UyGNtNcrVMip83cvJRhw1brMslPeyELIz3q6dsZ7GblVaCjL_8FKQhF6Syg-O_kIWztimGAYHY5EvPgmlkgnY0gmlwhH8AAAGJc2VjcDI1NmsxoQKzMe_GFPpSqtnYl-mJr8uZAUtmkqccsAx7ojGmFy-FY4N0Y3CCDhqDdWRwgg4u
```

## ⚠️ Formu Dolduruyoruz
https://obol.typeform.com/AthenaTestnet?typeform-source=blog.obol.tech

