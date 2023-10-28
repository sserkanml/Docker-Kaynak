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
  
