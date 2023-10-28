# Docker Nedir?

Docker, uygulamalarınızı hızla dağıtmanızı, paketlemenizi ve çalıştırmanızı sağlayan bir konteynerleştirme platformudur. Konteynerler, uygulama ve bağımlılıklarını bir araya getirerek her ortamda tutarlı bir çalışma sağlar.

## Docker Avantajları

- **Hafif ve Hızlı**: Docker konteynerleri, sanal makinelerden daha hafif ve hızlıdır, çünkü kendi işletim sistemini paylaşırlar.
  
- **Taşınabilirlik**: Docker konteynerleri, herhangi bir ortamda çalıştırılabilir, bu da uygulamaların her yerde tutarlı bir şekilde çalışmasını sağlar.
  
- **Yalıtım**: Konteynerler, uygulamaları ve bağımlılıklarını izole eder, böylece bir konteynerde yapılan değişiklikler diğer konteynerleri etkilemez.

## Nasıl Kullanılır?

1. Docker'ı [resmi web sitesinden indirin ve yükleyin](https://www.docker.com/get-started).

2. Docker'ı yükledikten sonra terminal veya komut istemcisini açın.

3. Docker konteyneri çalıştırmak için şu komutu kullanın:

```bash
   docker run [image_adı]
```
## Docker Komutları

1. Docker run:
* docker run komutu ile docker image'larınızdan container'lar oluşturabilirsiniz.
  
 ```bash
  # en temel haliyle image çalıştırma:
  docker run nginx
  # Bir konteyneri arka planda çalıştırma:
  docker run -d nginx
  # Bir konteyneri adlandırma:
  docker run --name my_container nginx
  # Port yönlendirme yaparak bir web uygulamasını çalıştırma:
  docker run -p 8080:80 nginx
  # Konteyneri bir ağa bağlama:
  docker run --network=my_network my_image
  # Bir ortam değişkeni ayarlama:
  docker run -e MY_VARIABLE=my_value my_image
  # Konteyneri bir volume'a bağlama:
  docker run -v /host/dizin:/container/dizin my_image
  ```
2. Docker exec:
* docker exec komutu, Docker konteyneri içinde çalışan bir komutu yürütmek için kullanılır.
  ```bash
  # Bir komut çalıştırma:
  docker exec my_container ls -l
  # Bir interaktif kabuk başlatma:
  docker exec -it my_container sh
  # Arka planda çalışan bir süreci yönetme:
  docker exec -d my_container nginx -g 'daemon off;'
  # Ortam değişkeni ekleyerek bir komut çalıştırma:
  docker exec -e MY_VARIABLE=my_value my_container echo $MY_VARIABLE
  # Konteynerin başka bir kullanıcı kimliğiyle çalışmasını sağlama:
  docker exec -u www-data my_container whoami```
3. Docker ps:
* docker ps komutu, çalışan Docker konteynerlerini listeler:
  ```bash
  # Tüm çalışan konteynerleri listele:
  docker ps
  # Tüm konteynerleri listele (çalışan ve durmuş):
  docker ps -a
  # Özel bir formatta listeleme:
  docker ps --format "{{.ID}}: {{.Image}} - {{.Names}}"```
4. Docker build:
   * docker build komutu, Docker imajlarını oluşturmak için kullanılır:
     ```bash
     # komutu çalıştırarak Docker imajını oluşturabilirsiniz:
     docker build -t my_image```
5. Docker pull:
   * docker pull komutu, Docker Hub veya başka bir Docker imaj deposundan bir Docker imajını indirmek için kullanılır.
     ```bash
     # Ubuntu imajını indirmek için:
     docker pull ubuntu
     # Eğer belirli bir sürümü (örneğin 20.04) indirmek isterseniz:
     docker pull ubuntu:20.04```
6. Docker push:
   * docker push komutu, yerel makinenizde bulunan bir Docker imajını bir Docker imaj deposuna (örneğin Docker Hub) yüklemenizi sağlar
     ```bash
     # İlk olarak, docker login komutu ile Docker imaj deposuna oturum açmanız gerekir:
     docker login
     # Ardından, docker push komutunu kullanarak imajınızı yükleyebilirsiniz:
     docker push <repository_name>/<image_name>:<tag>```
7. Docker images:
   * docker images komutu, yerel Docker imaj deposundaki tüm Docker imajlarını listeler. Bu komut, yerel makinenizde bulunan Docker imajlarının bir listesini sunar
     ```bash
     docker images```
8. Docker login:
   * docker login komutu, Docker imaj deposuna (örneğin Docker Hub) oturum açmanızı sağlar:
     ```bash
     docker login```
9. Docker logout:
   * docker logout komutu, Docker imaj deposundan (örneğin Docker Hub) oturumu kapatmanızı sağlar
     ```bash
     docker logout```
10. Docker search:
    * docker search komutu, Docker Hub veya başka bir Docker imaj deposundaki imajları aramanızı sağlar:
      ```bash
      docker search <keyword>
      # Örneğin, Ubuntu ile ilgili imajları aramak için:
      docker search ubuntu ```
11. Docker network:
    
