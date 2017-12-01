---
title: "Defina su aplicación de múltiples contenedor con docker compose.yml"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Defina su aplicación de múltiples contenedor con docker compose.yml"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c5d4d2c9fb9fbb595f6f6ea195247474f353a32f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a>Defina su aplicación de múltiples contenedor con docker compose.yml 

En esta guía, la [docker compose.yml](https://docs.docker.com/compose/compose-file/) archivo se introdujo en la sección [paso 4. Definir los servicios en docker compose.yml al compilar una aplicación de Docker de contenedor varios](#step4_define_svcs_in_docker_compose_yml). Sin embargo, hay otras formas de usar los archivos docker-compose que merece la pena examinar con más detalle.

Por ejemplo, puede describir explícitamente cómo desea implementar la aplicación de contenedor múltiples en el archivo compose.yml docker. Si lo desea, también puede describir cómo se van a generar las imágenes del Docker personalizadas. (Las imágenes de Docker personalizado también pueden generarse con la CLI de Docker.)

Básicamente, defina cada uno de los contenedores que desea implementar además de ciertas características de cada implementación de contenedor. Una vez que tenga un archivo de descripción de la implementación de varios contenedores, puede implementar la solución completa en una sola acción organizada el [docker redactar una](https://docs.docker.com/compose/overview/) comando de CLI, o bien puede implementarlo transparente desde Visual Studio. En caso contrario, se debe utilizar la CLI de Docker para implementar los contenedores en varios pasos mediante el comando docker run desde la línea de comandos. Por lo tanto, cada servicio definido en docker compose.yml debe especificar exactamente una imagen o de compilación. Otras claves son opcionales y son análogas a su homólogos de la línea de comandos de ejecución de docker.

El siguiente código YAML es la definición de un archivo de posibles global pero solo docker-compose.yml para el ejemplo eShopOnContainers. No es el archivo real docker-compose desde eShopOnContainers. En su lugar, es una versión simplificada y consolidada en un único archivo, no es la mejor manera de trabajar con docker-crear archivos, como se explicará más adelante.

```yml
version: '2'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
    ports:
      - "5100:80"
    depends_on:
      - catalog.api
      - ordering.api
      - basket.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=Services.OrderingDb;User Id=sa;Password=your@password
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  basket.api:
    image: eshop/basket.api
    environment:
      - ConnectionString=sql.data
    ports:
      - "5103:80"
    depends_on:
      - sql.data

  sql.data:
    environment:
      - SA_PASSWORD=your@password
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basket.data:
    image: redis
```

La clave raíz de este archivo es servicios. Bajo esa clave se definen los servicios que desea implementar y ejecutar cuando se ejecuta el docker crear comandos o cuando se implementa desde Visual Studio mediante el uso de este archivo compose.yml docker. En este caso, el archivo de docker compose.yml tiene varios servicios definidos, como se describe en la lista siguiente.

-   webmvc contenedor que incluye la aplicación de MVC de ASP.NET Core consumiendo el microservicios del servidor C\#

-   Catalog.API contenedor que incluye el núcleo de catálogo ASP.NET Web API microservicio

-   Ordering.API contenedor que incluye el microservicio de ordenación de ASP.NET Core Web API

-   SQL.Data contenedor que se ejecuta SQL Server para Linux, que contiene las bases de datos de microservicios

-   Basket.API contenedor con el núcleo de la cesta de compras ASP.NET Web API microservicio

-   Basket.Data contenedor que se ejecuta el servicio de caché REDIS, con la base de datos de la cesta de compra como una memoria caché REDIS

### <a name="a-simple-web-service-api-container"></a>Un contenedor de la API del servicio Web simple

Centrarse en un único contenedor, el contenedor de catalog.api-microservicio tiene una definición sencilla:

```yml
  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=catalog.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data
```

Este servicio en contenedores tiene la siguiente configuración básica:

-   Se basa en la imagen eshop/catalog.api personalizado. Por simplicidad, no hay ninguna compilación: configuración en el archivo de clave. Esto significa que la imagen debe ha compilado previamente (con la compilación de docker) o se han descargado (con el comando de extracción de docker) de cualquier registro de Docker.

-   Define una variable de entorno denominada ConnectionString con la cadena de conexión para usarse por Entity Framework para tener acceso a la instancia de SQL Server que contiene el modelo de datos de catálogo. En este caso, el mismo contenedor de SQL Server contiene varias bases de datos. Por lo tanto, necesitará menos memoria en el equipo de desarrollo para Docker. Sin embargo, también puede implementar un contenedor de SQL Server para cada base de datos de microservicio.

-   El nombre de SQL Server es sql.data, que es el mismo nombre que se utiliza para el contenedor que se ejecuta la instancia de SQL Server para Linux. Esto resulta útil; poder usar esta resolución de nombres (interna en el host Docker) se resuelve la dirección de red, por lo que no necesita conocer la dirección IP interna de los contenedores que obtiene acceso desde otros contenedores.

Dado que la cadena de conexión se define una variable de entorno, puede establecer esa variable mediante un mecanismo diferente y en un momento diferente. Por ejemplo, podría establecer una cadena de conexión diferentes cuando se implementa en producción en los hosts finales, o si lo hace desde sus canalizaciones de CI/CD en VSTS o el sistema de DevOps preferido.

-   Expone el puerto 80 para el acceso interno al servicio catalog.api dentro del host de Docker. El host es actualmente una VM Linux porque se basa en una imagen de Docker para Linux, pero puede configurar el contenedor para que se ejecute en una imagen de Windows en su lugar.

-   Reenvía el puerto 80 en el contenedor al puerto 5101 en el equipo de host Docker (la VM de Linux) expuesto.

-   El servicio web vincula al servicio sql.data (la instancia de SQL Server para ejecutar en un contenedor de base de datos de Linux). Cuando se especifica esta dependencia, el contenedor catalog.api no se iniciará hasta que ya ha iniciado el contenedor de sql.data; Esto es importante porque debe tener la base de datos de SQL Server hasta catalog.api y se ejecuta en primer lugar. Sin embargo, este tipo de dependencia de contenedor no es suficiente en muchos casos, dado que las comprobaciones de Docker sólo en el nivel de contenedor. A veces el servicio (en este caso de SQL Server) todavía no estén listo, por lo que es aconsejable implementar la lógica de reintento con retroceso exponencial en su microservicios de cliente. De este modo, si un contenedor de dependencia no está listo para poco tiempo, la aplicación se seguirá resistente.

-   Está configurado para permitir el acceso a los servidores externos: el archivo extra\_hosts establecer permiten obtener acceso a servidores externos o equipos situados fuera del host Docker (es decir, fuera de la VM de Linux que es un desarrollo Docker predeterminado de host), como una instancia de SQL local Instancia del servidor en el equipo de desarrollo.

También hay otras opciones de docker compose.yml más avanzadas que se exponen en las secciones siguientes.

### <a name="using-docker-compose-files-to-target-multiple-environments"></a>Usando docker-crear archivos en varios entornos de destino

Los archivos de docker compose.yml son archivos de definición y pueden utilizarse en varias infraestructuras que entienden ese formato. La herramienta más sencilla es el docker-crear comando, pero otras herramientas como orchestrators (por ejemplo, Docker Swarm) también comprenden ese archivo.

Por consiguiente, al usar el comando puede tener como destino los siguientes escenarios principales de redacción de docker.

#### <a name="development-environments"></a>Entornos de desarrollo

Al desarrollar aplicaciones, es importante ser capaz de ejecutar una aplicación en un entorno de desarrollo aislado. Puede usar el comando CLI para crear dicho entorno o usar Visual Studio que usa docker redactar tras los bastidores de redacción de docker.

El archivo compose.yml docker permite configurar y documentar todas las dependencias de su aplicación servicio (otros servicios, caché, las bases de datos, las colas, etcetera). Mediante el comando de CLI de docker redactar, puede crear e iniciar uno o varios contenedores para cada dependencia con un solo comando (redactar docker seguridad).

Los archivos de docker compose.yml son interpretados por el motor de Docker de archivos de configuración pero también actúan como archivos de documentación adecuada sobre la composición de la aplicación contenedora múltiples.

#### <a name="testing-environments"></a>Entornos de prueba

Una parte importante de cualquier implementación continua (CD) o el proceso de integración continua (CI) son las pruebas unitarias y pruebas de integración. Estas pruebas automatizadas requieren un entorno aislado, por lo que no afectan a los usuarios o cualquier otro cambio en los datos de la aplicación.

Con Docker Compose pueden crear y destruir ese entorno aislado muy fácilmente en algunos comandos desde el símbolo del sistema o secuencias de comandos, como los comandos siguientes:

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a>Implementaciones de producción

También puede utilizar redactar para implementar en un motor de Docker remoto. Un caso típico consiste en implementar en una única instancia de host de Docker (como una máquina virtual de producción o servidor proporcionado con [máquina Docker](https://docs.docker.com/machine/overview/)). Pero también podría ser toda una [Docker Swarm](https://docs.docker.com/swarm/overview/) el clúster, porque en clústeres también son compatibles con los archivos de compose.yml de docker.

Si está utilizando cualquier orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), tendrá que agregar valores de configuración de instalación y los metadatos como los de docker compose.yml, pero en el formato requerido por el orquestador del otro.

En cualquier caso, componer de docker es un formato conveniente de herramienta y los metadatos para los flujos de trabajo de desarrollo, pruebas y producción, aunque el flujo de trabajo de producción puede variar en el orchestrator que usa.

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a>Utilizando varias redactar docker archivos para controlar varios entornos

Cuando se destinan a entornos diferentes, debe usar varias crear archivos. Esto le permite crear varias variantes de configuración en función del entorno.

#### <a name="overriding-the-base-docker-compose-file"></a>Reemplazar el archivo de base de docker-compose

Puede usar un archivo de docker-compose.yml único como en los ejemplos simplificados que se muestra en las secciones anteriores. Sin embargo, no se recomienda para la mayoría de las aplicaciones.

De forma predeterminada, redactar lee dos archivos, un compose.yml de docker y un archivo de docker-compose.override.yml opcional. Como se muestra en la figura 8-11, cuando se usa Visual Studio y habilitar la compatibilidad de Docker, Visual Studio crea también los archivos más algunos archivos adicionales usados para la depuración.

![](./media/image12.png)

**Figura 8-11**. docker-crear archivos en Visual Studio de 2017

Puede editar los archivos de docker-compose con cualquier editor, como código de Visual Studio o fundamentales y ejecutar la aplicación con el docker-crear una copia de seguridad comando.

Por convención, el archivo de docker compose.yml contiene la configuración base y otras opciones estáticas. Esto significa que no debe cambiar la configuración del servicio según el entorno de implementación de destino.

El archivo compose.override.yml de docker, como su nombre sugiere, contiene valores de configuración que invalidación la configuración básica, como la configuración de los que depende del entorno de implementación. También puede tener varios archivos de invalidación con nombres diferentes. Los archivos de invalidación suelen contengan información adicional necesaria para la aplicación pero específico en un entorno o en una implementación.

#### <a name="targeting-multiple-environments"></a>Varios entornos de destino

Un caso de uso típico es cuando se definen varias crear archivos por lo que puede tener como destino varios entornos, como la producción, prueba, desarrollo o elemento de configuración. Para admitir estas diferencias, puede dividir la configuración de redacción en varios archivos, como se muestra en la figura 8-12.

![](./media/image13.png)

**Figura 8-12**. Docker-crear varios archivos al reemplazar los valores en el archivo de base de compose.yml de docker

Iniciar con el archivo de base de compose.yml de docker. Este archivo de base debe contener los valores de configuración base o estático que no cambian en función del entorno. Por ejemplo, el eShopOnContainers tiene el siguiente archivo de docker compose.yml que el archivo de base.

```yml
#docker-compose.yml (Base)
version: '2'

services:
  basket.api:
    image: eshop/basket.api
    build:
    context: ./src/Services/Basket/Basket.API
    dockerfile: Dockerfile
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api
    build:
    context: ./src/Services/Catalog/Catalog.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  identity.api:
    image: eshop/identity.api
    build:
    context: ./src/Services/Identity/Identity.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    build:
    context: ./src/Services/Ordering/Ordering.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  webspa:
    image: eshop/webspa
    build:
    context: ./src/Web/WebSPA
    dockerfile: Dockerfile
    depends_on:
      - identity.api
      - basket.api

  webmvc:
    image: eshop/webmvc
    build:
    context: ./src/Web/WebMVC
    dockerfile: Dockerfile
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api

  sql.data:
    image: microsoft/mssql-server-linux
    basket.data:
    image: redis
    expose:
      - "6379"
    rabbitmq:
    image: rabbitmq
    ports:
      - "5672:5672"

  webstatus:
    image: eshop/webstatus
    build:
    context: ./src/Web/WebStatus
    dockerfile: Dockerfile
```

No deberían cambiar los valores en el archivo de base de docker-compose.yml debido a los entornos de implementación de destino diferente.

Por ejemplo, si coloca el foco en la definición del servicio webmvc, puede ver cómo esa información es el mismo con independencia de qué entorno quiere que podría ser el destino. Tiene la siguiente información:

-   El nombre del servicio: webmvc.

-   Imagen personalizada del contenedor: compras/webmvc.

-   El comando para generar la imagen personalizada de Docker, que indica qué Dockerfile a usar.

-   Dependencias de otros servicios, por lo que este contenedor no se inicia hasta que hayan iniciado los otros contenedores de dependencia.

Puede tener una configuración adicional, pero lo importante es que en el archivo de base de compose.yml de docker, simplemente desea establecer la información que es común a través de entornos. A continuación, en el docker compose.override.yml o archivos similares para producción o ensayo, debería colocar configuración específica para cada entorno.

Por lo general, la compose.override.yml de docker se usa para el entorno de desarrollo, como se muestra en el siguiente ejemplo de eShopOnContainers:

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '2'

services:
# Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database=Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Pass@word
      - ExternalCatalogBaseUrl=http://localhost:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:5105
    - SpaClient=http://localhost:5104
    - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
    - MvcClient=http://localhost:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://localhost:5101
      - OrderingUrl=http://localhost:5102
      - IdentityUrl=http://localhost:5105
      - BasketUrl=http:// localhost:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

En este ejemplo, la configuración de invalidación de desarrollo expone algunos puertos al host, define las variables de entorno con redirigir las direcciones URL y especifica las cadenas de conexión para el entorno de desarrollo. Esta configuración es simplemente para el entorno de desarrollo.

Al ejecutar docker redactar una (o iniciarlo desde Visual Studio), el comando lee las invalidaciones automáticamente como si se estaban combinando ambos archivos.

Suponga que desea que otro archivo de composición para el entorno de producción, con valores de configuración diferente. Puede crear otro archivo de reemplazo, similar al siguiente. (Este archivo podría estar almacenado en un repositorio de Git diferentes o administrado y protegido por un equipo diferente.)

```yml
#docker-compose.prod.yml (Extended config for PRODUCTION env.)
version: '2'

services:
  # Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database = Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Prod@Pass
      - ExternalCatalogBaseUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5105
      - SpaClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5104
      - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
      - MvcClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT= Production
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
      - OrderingUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5102
      - IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
      - BasketUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Prod@Pass
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

#### <a name="how-to-deploy-with-a-specific-override-file"></a>Cómo implementar con un archivo de invalidación específica

Para usar varios archivos de invalidación, o un archivo de reemplazo con un nombre diferente, puede usar la opción -f con los comandos de docker crear y especificar los archivos. Crear archivos de combinaciones en el orden en que se especifican en la línea de comandos. En el ejemplo siguiente se muestra cómo implementar con archivos de invalidación.

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a>Usar variables de entorno en docker-crear archivos

Es conveniente, especialmente en entornos de producción, para poder obtener la información de configuración de variables de entorno, tal y como hemos mostrado en los ejemplos anteriores. Hace referencia a una variable de entorno en los archivos de docker-compose mediante la sintaxis \${MY\_VAR}. La siguiente línea de un archivo de docker compose.prod.yml muestra cómo hacer referencia al valor de una variable de entorno.

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

Las variables de entorno se crean e inicializan de maneras diferentes, dependiendo de su entorno de host (Linux, Windows, clúster de la nube, etcetera.). Sin embargo, un método cómodo es usar un archivo .env. Los archivos docker-compose admiten declarar variables de entorno de forma predeterminada en el archivo .env. Estos valores para las variables de entorno son los valores predeterminados. Pero se pueden invalidar los valores que se haya definido en cada uno de los entornos (sistema operativo del host o variables de entorno del clúster). Coloque este archivo .env en la carpeta donde la redacción de docker se ejecuta el comando de.

En el ejemplo siguiente se muestra un archivo .env como el [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) archivo para la aplicación eShopOnContainers.

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

Crear docker espera que cada línea de un archivo .env para tener el formato &lt;variable&gt;=&lt;valor&gt;.

Tenga en cuenta que los valores establecidos en el entorno en tiempo de ejecución siempre reemplazan los valores definidos en el archivo .env. De forma similar, los valores que se pasan a través de los argumentos de línea de comandos invalidan los valores predeterminados establecidos en el archivo .env.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Información general de Docker crear**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)

-   **Varios archivos de redactar**
    [*https://docs.docker.com/compose/extends/\#archivos componer de varios*](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a>Compilar con optimización para imágenes de Docker de núcleo de ASP.NET

Si está explorando Docker y .NET Core en orígenes de Internet, encontrará Dockerfiles que muestran la sencillez de creación de una imagen de Docker mediante la copia de su origen en un contenedor. Estos ejemplos sugieren que con una configuración simple, puede tener una imagen de Docker con el entorno de empaquetar con la aplicación. En el ejemplo siguiente se muestra un sencillo Dockerfile en esta misma línea.

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

Funcionará un Dockerfile similar al siguiente. Sin embargo, puede optimizar considerablemente sus imágenes, especialmente las imágenes de producción.

En el contenedor y el modelo de microservicios, que está iniciando constantemente contenedores. La manera habitual de utilizar contenedores no reinicia un contenedor inactivo, porque el contenedor es descartable. Orchestrators (por ejemplo, Docker Swarm, Kubernetes, DCOS o Azure Service Fabric) basta con crean instancias nuevas de imágenes. Esto significa que se debe optimizar por precompilar la aplicación cuando se crea para que el proceso de creación de instancias es más rápido. Cuando se inicia el contenedor, estará preparado para ejecutarse. No se deben restaurar y compilar en tiempo de ejecución, mediante dotnet restauración y dotnet generación comandos de la CLI de dotnet, como se ve en todas las entradas de blog sobre .NET Core y Docker.

El equipo de .NET ha estado realizando trabajo importante para hacer que un marco optimizado para el contenedor de .NET Core y ASP.NET Core. No solo es .NET Core un marco de trabajo ligera con una pequeña superficie de memoria; el equipo se ha centrado en el rendimiento de inicio y genera algunas imágenes de Docker optimizados, como la [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) imagen disponible en [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), en comparación con la normal [ Microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) o [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) imágenes. El [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) imagen proporciona configuración automática de aspnetcore\_las direcciones URL para el puerto 80 y la caché de pre-ngend de ensamblados; estas dos opciones como resultado de inicio más rápido.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Compilar con optimización para imágenes de Docker con ASP.NET Core**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)

### <a name="building-the-application-from-a-build-ci-container"></a>Compilar la aplicación desde un contenedor de compilación (CI)

Otra ventaja de Docker es que puede compilar su aplicación desde un contenedor preconfigurada, tal como se muestra en la figura 8-13, por lo que no es necesario crear una máquina de compilación o la máquina virtual para compilar la aplicación. Puede usar o probar que el contenedor de compilación mediante la ejecución en el equipo de desarrollo. Pero lo que es aún más interesante es que puede usar el mismo contenedor de compilación de la canalización de CI (integración continua).

![](./media/image14.png)

**Figura 8-13**. Creación de bits de .NET desde un contenedor de componentes

En este escenario, proporcionamos el [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) imagen, que puede usar para compilar y generar aplicaciones de la principal de ASP.NET. La salida se coloca en una imagen basada en la [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) imagen, que es una imagen optimizada en tiempo de ejecución, como se indicó anteriormente.

La imagen de compilación aspnetcore contiene todo lo que necesita para compilar una aplicación de ASP.NET Core, incluidos .NET Core, el SDK de ASP.NET, npm, Bower, Gulp, etcetera.

Necesitamos estas dependencias en tiempo de compilación. Pero no queremos llevar junto con la aplicación en tiempo de ejecución, porque haría que la imagen sea demasiado grande. En la aplicación eShopOnContainers, puede compilar la aplicación desde un contenedor simplemente ejecutando la siguiente docker-crear comando.

```
  docker-compose -f docker-compose.ci.build.yml up
```

Figura 8-14 muestra este comando que se ejecuta en la línea de comandos.

![](./media/image15.png)

**Figura 8-14.** Compilar la aplicación .NET de un contenedor

Como puede ver, el contenedor que se ejecuta es la compilación de ci\_1 contenedor. Esto se basa en la imagen de compilación aspnetcore para que puede compilar y generar toda la aplicación desde dentro de ese contenedor en lugar de desde su PC. Es decir ¿por qué en realidad es generar y compilar los proyectos de .NET Core en Linux, porque ese contenedor se está ejecutando en el host de Linux Docker de forma predeterminada.

El [docker compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) de archivos de imagen (parte de eShopOnContainers) contiene el código siguiente. Puede ver que inicia un contenedor de compilación mediante la [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) imagen.

```yml
version: '2'
  services:
    ci-build:
      image: microsoft/aspnetcore-build:1.0-1.1
      volumes:
        - .:/src
      working_dir: /src
      command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && pushd ./../../.. && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"
```

* A partir de **.NET Core 2.0**, `dotnet restore` comando se ejecuta automáticamente cuando el `dotnet publish` se ejecuta el comando.

Una vez que el contenedor de compilación está en funcionamiento, se ejecuta la restauración de dotnet .NET SDK y dotnet publicar comandos en todos los proyectos de la solución con el fin de compilar los bits. NET. En este caso, puesto que eShopOnContainers también tiene un SPA basado en TypeScript y Angular para el código de cliente, también necesita comprobar las dependencias de JavaScript con npm, pero esa acción no está relacionado con los bits. NET.

El dotnet publicar compilaciones de comando y publica la salida compilada dentro de la carpeta de cada proyecto a la... carpeta /obj/Docker/Publish, tal como se muestra en la figura 8-15.

![](./media/image16.png)

**Figura 8-15.** Comando de publicar los archivos binarios generados por el dotnet.

#### <a name="creating-the-docker-images-from-the-cli"></a>Crear las imágenes de Docker desde la CLI

Una vez que la salida de la aplicación se publica en las carpetas relacionadas (dentro de cada proyecto), el siguiente paso es compilar las imágenes de Docker. Para ello, utilice la compilación docker-compose y docker-crear comandos, tal como se muestra en la figura 8-16.

![](./media/image17.png)

**Figura 8-16.** Creación de imágenes de Docker y los contenedores en ejecución

En la figura 8-17, puede ver cómo la docker-compose crear la ejecución del comando.

![](./media/image18.png)

**Figura 8-17**. Creación de las imágenes de Docker con el docker-crear el comando de compilación

La diferencia entre el docker-compose compilar y redactar docker de comandos es que docker crear compilaciones e inicia las imágenes.

Cuando se utiliza Visual Studio, todos estos pasos se realizan en segundo plano. Visual Studio compila la aplicación. NET, crea las imágenes de Docker e implementa los contenedores en el host Docker. Visual Studio ofrece características adicionales, como la capacidad para depurar los contenedores que se ejecutan en Docker, directamente desde Visual Studio.

Aquí el takeway general es que es capaz de crear la aplicación de la misma forma en la canalización de CI/CD debe compilarse: desde un contenedor en lugar de desde un equipo local. Si tiene las imágenes creadas, a continuación, simplemente debe ejecutar las imágenes de Docker con el docker-crear comando.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Creación de bits de un contenedor: configurar la solución eShopOnContainers en un entorno de Windows CLI (dotnet CLI, CLI de Docker y el código de VS)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/ 03.-Setting-the-eShopOnContainers-Solution-up-in-a-Windows-CLI-Environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))


>[!div class="step-by-step"]
[Anterior] (datos-controlada por-crud-microservice.md) [siguiente] (container.md de servidor de base de datos)
