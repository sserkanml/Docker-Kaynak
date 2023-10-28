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
  docker exec -u www-data my_container whoami
```
3. Docker ps:
   
* docker ps komutu, çalışan Docker konteynerlerini listeler.
  
```bash
  # Tüm çalışan konteynerleri listele:
  docker ps
  # Tüm konteynerleri listele (çalışan ve durmuş):
  docker ps -a
  # Özel bir formatta listeleme:
  docker ps --format "{{.ID}}: {{.Image}} - {{.Names}}"
```
4. Docker build:
   
* docker build komutu, Docker imajlarını oluşturmak için kullanılır.
     
```bash
     # komutu çalıştırarak Docker imajını oluşturabilirsiniz:
     docker build -t my_image
```
6. Docker pull:
   
* docker pull komutu, Docker Hub veya başka bir Docker imaj deposundan bir Docker imajını indirmek için kullanılır.
     
```bash
     # Ubuntu imajını indirmek için:
     docker pull ubuntu
     # Eğer belirli bir sürümü (örneğin 20.04) indirmek isterseniz:
     docker pull ubuntu:20.04
```
7. Docker push:
   
* docker push komutu, yerel makinenizde bulunan bir Docker imajını bir Docker imaj deposuna (örneğin Docker Hub) yüklemenizi sağlar.
     
```bash
     # İlk olarak, docker login komutu ile Docker imaj deposuna oturum açmanız gerekir:
     docker login
     # Ardından, docker push komutunu kullanarak imajınızı yükleyebilirsiniz:
     docker push <repository_name>/<image_name>:<tag>
```
9. Docker images:
    
* docker images komutu, yerel Docker imaj deposundaki tüm Docker imajlarını listeler. Bu komut, yerel makinenizde bulunan Docker imajlarının bir listesini sunar.
     
```bash
     docker images
```
11. Docker login:
    
* docker login komutu, Docker imaj deposuna (örneğin Docker Hub) oturum açmanızı sağlar.
     
```bash
     docker login
```
12. Docker logout:
    
* docker logout komutu, Docker imaj deposundan (örneğin Docker Hub) oturumu kapatmanızı sağlar.
     
```bash
     docker logout
```
13. Docker search:
    
* docker search komutu, Docker Hub veya başka bir Docker imaj deposundaki imajları aramanızı sağlar.
      
```bash
      docker search <keyword>
      # Örneğin, Ubuntu ile ilgili imajları aramak için:
      docker search ubuntu
```
14. Docker network:
    
* docker network, Docker ortamında ağ oluşturma ve yönetme işlemlerini gerçekleştirmek için kullanılan bir komuttur.
      
```bash
    # Ağı Listeleme:
    docker network ls
    # Ağ Oluşturma:
    docker network create my_network
    # Ağ Detaylarını Görüntüleme:
    docker network inspect my_network
    # Ağa Konteyner Ekleme:
    docker network connect my_network my_container
    # Ağı Konteynerden Kaldırma:
    docker network disconnect my_network my_container
```
15. Docker volume:
    
* docker volume, Docker ortamında veri saklama ve paylaşma işlemlerini gerçekleştirmek için kullanılan bir komuttur.
      
```bash
      # Volume Listeleme:
      docker volume ls
      # Volume Oluşturma:
      docker volume create my_volume
      # Volume Detaylarını Görüntüleme:
      docker volume inspect my_volume
      # Volume'i Bir Konteynere Bağlama:
      docker run -d -v my_volume:/data my_image
      # Birden Fazla Volume Tanımlama:
      docker run -d -v my_volume1:/data1 -v my_volume2:/data2 my_image
```
16. Docker kill:
      
* docker kill komutu, çalışan bir Docker konteynerini zorla sonlandırmak için kullanılır.
        
```bash
      docker kill my_container
```
17. Docker logs:
      
* docker logs komutu, belirli bir Docker konteynerinin loglarını görüntülemek için kullanılır.
        
```bash
        docker logs my_container
```
19. Docker rm:
      
* docker rm komutu, bir veya birden fazla Docker konteynerini silmek için kullanılır.
        
```bash
         docker rm my_container
         # Birden fazla konteyneri silmek için
         docker rm container1 container2 container3
```
21. Docker stop:
    
* docker stop komutu, çalışan bir Docker konteynerini durdurmak için kullanılır.
        
```bash
        docker stop my_container
        # Birden fazla konteyneri durdurmak için:
        docker stop container1 container2 container3
```
22. Docker inspect:
    
* docker inspect komutu, belirli bir Docker nesnesinin (konteyner, imaj, ağ vb.) ayrıntılarını JSON formatında görüntülemek için kullanılır.
        
```bash
        docker inspect my_container
```
23. Docker history:
    
* docker history komutu, bir Docker imajının oluşturulma geçmişini görüntülemek için kullanılır.
        
```bash
        docker history ubuntu
```
25. Docker pause:
    
* docker pause komutu, bir çalışan Docker konteynerini geçici olarak duraklatmak için kullanılır.
        
```bash
        docker pause my_container
```
26. Docker unpause:
    
* docker unpause komutu, duraklatılmış bir Docker konteynerini yeniden başlatmak için kullanılır.
        
```bash
        docker unpause my_container
```
        
        

    
