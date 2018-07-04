---
title: Definir una aplicación de varios contenedores con docker-compose.yml
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Definir una aplicación de varios contenedores con docker-compose.yml
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/30/2017
ms.openlocfilehash: 430fbe3fc6d63fd3b90b578f32b42831c368ba10
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106309"
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a>Definir una aplicación de varios contenedores con docker-compose.yml 

En esta guía, el archivo [docker-compose.yml](https://docs.docker.com/compose/compose-file/) se ha introducido en la sección [Paso 4. Definir los servicios en docker-compose.yml al compilar una aplicación de Docker de varios contenedores](#step4_define_svcs_in_docker_compose_yml). Pero hay otras formas de usar los archivos docker-compose que merece la pena examinar con más detalle.

Por ejemplo, puede describir explícitamente cómo quiere implementar la aplicación de varios contenedores en el archivo docker-compose.yml. Si quiere, también puede describir cómo va a compilar las imágenes de Docker personalizadas (las imágenes de Docker personalizadas también se pueden compilar con la CLI de Docker).

Básicamente define cada uno de los contenedores que quiere implementar, además de ciertas características para cada implementación de contenedor. Una vez que tenga un archivo de descripción de la implementación de varios contenedores, puede implementar la solución completa en una sola acción organizada por el comando de la CLI [docker-compose up](https://docs.docker.com/compose/overview/) o bien puede implementarla de forma transparente en Visual Studio. En caso contrario, tendría que usar la CLI de Docker para implementar uno a uno los contenedores en varios pasos usando el comando docker run desde la línea de comandos. Por lo tanto, cada servicio definido en el archivo docker-compose.yml debe especificar exactamente una imagen o compilación. El resto de las claves son opcionales y son análogas a sus equivalentes de la línea de comandos docker run.

El siguiente código YAML es la definición de un archivo docker-compose.yml posiblemente global pero único para el ejemplo de eShopOnContainers. Este no es el archivo docker-compose real de eShopOnContainers, sino que es una versión simplificada y consolidada en un único archivo, lo cual no es la mejor manera de trabajar con archivos docker-compose, como se explicará más adelante.

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

La clave raíz de este archivo es "services" (servicios). En esa clave se definen los servicios que se quieren implementar y ejecutar al ejecutar el comando docker-compose up o al implementarlos en Visual Studio usando este archivo docker-compose.yml. En este caso, el archivo docker-compose.yml tiene varios servicios definidos, como se describe en la siguiente lista.

-   webmvc: contenedor que incluye la aplicación MVC de ASP.NET Core que consume los microservicios de C\# del lado servidor

-   catalog.api: contenedor que incluye el microservicio Catalog de la API web de ASP.NET Core

-   ordering.api: contenedor que incluye el microservicio Ordering de la API web de ASP.NET Core

-   sql.data: contenedor que ejecuta SQL Server para Linux, que contiene las bases de datos de microservicios

-   basket.api: contenedor que incluye el microservicio Basket de la API web de ASP.NET Core

-   basket.data: contenedor que ejecuta el servicio Redis Cache, con la base de datos Basket como memoria caché de Redis

### <a name="a-simple-web-service-api-container"></a>Contenedor de la API de servicio web simple

Si nos centramos en un único contenedor, el microservicio de contenedor catalog.api tiene una definición sencilla:

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

Este servicio de contenedor tiene la siguiente configuración básica:

-   Se basa en la imagen eshop/catalog.api personalizada. Por simplicidad, no hay ninguna compilación: configuración clave en el archivo. Esto significa que la imagen se debe haber compilado previamente (con docker build) o se debe haber descargado (con el comando docker pull) de cualquier registro de Docker.

-   Define una variable de entorno denominada ConnectionString con la cadena de conexión para que la use Entity Framework para obtener acceso a la instancia de SQL Server que contiene el modelo de datos del catálogo. En este caso, el mismo contenedor de SQL Server contiene varias bases de datos. Por lo tanto, necesitará menos memoria en el equipo de desarrollo para Docker, aunque también podría implementar un contenedor de SQL Server para cada base de datos de microservicio.

-   El nombre de SQL Server es sql.data, que es el mismo nombre que se usa para el contenedor que ejecuta la instancia de SQL Server para Linux. Esto resulta práctico: poder usar esta resolución de nombres (interna al host de Docker) resolverá la dirección de red, por lo que no necesita saber la dirección IP interna de los contenedores a los que tiene acceso desde otros contenedores.

Dado que la cadena de conexión se define mediante una variable de entorno, podría establecer esa variable mediante otro mecanismo y en otro momento. Por ejemplo, podría establecer una cadena de conexión diferente al efectuar una implementación en producción en los hosts finales, o haciéndolo desde sus canalizaciones de CI/CD en VSTS o en su sistema de DevOps preferido.

-   Expone el puerto 80 para el acceso interno al servicio catalog.api dentro del host de Docker. Actualmente, el host es una máquina virtual de Linux porque se basa en una imagen de Docker para Linux, aunque podría configurar el contenedor para que se ejecute en una imagen de Windows.

-   Reenvía el puerto 80 expuesto del contenedor al puerto 5101 del equipo host de Docker (la máquina virtual de Linux).

-   Vincula el servicio web al servicio sql.data (la base de datos de instancias de SQL Server para Linux que se ejecuta en un contenedor). Al especificar esta dependencia, el contenedor catalog.api no se iniciará hasta que se haya iniciado el contenedor sql.data. Esto es importante porque catalog.api necesita primero que la base de datos de SQL Server esté en ejecución. Pero este tipo de dependencia de contenedor no es suficiente en muchos casos, dado que Docker efectúa comprobaciones únicamente en el nivel de contenedor. A veces es posible que el servicio (en este caso SQL Server) aún no esté listo, por lo que es aconsejable implementar la lógica de reintento con retroceso exponencial en los microservicios de su cliente. De este modo, si un contenedor de dependencia no está listo durante un período de tiempo breve, la aplicación seguirá siendo resistente.

-   Está configurado para permitir el acceso a los servidores externos: el valor de configuración extra\_hosts le permite obtener acceso a máquinas o servidores externos situados fuera del host de Docker (es decir, fuera de la máquina virtual de Linux predeterminada, que es un host de Docker de desarrollo), como una instancia local de SQL Server en su equipo de desarrollo.

También existen otras opciones más avanzadas de los archivos docker-compose.yml que se exponen en las siguientes secciones.

### <a name="using-docker-compose-files-to-target-multiple-environments"></a>Usar archivos docker-compose para fijar como objetivo varios entornos

Los archivos docker-compose.yml son archivos de definición que se pueden usar en varias infraestructuras que comprendan ese formato. La herramienta más sencilla es el comando docker-compose, pero existen otras herramientas, como los orquestadores (por ejemplo, Docker Swarm), que también comprenden ese archivo.

Por lo tanto, si usa el comando docker-compose, puede fijar como objetivo los siguientes escenarios principales.

#### <a name="development-environments"></a>Entornos de desarrollo

Al desarrollar aplicaciones, es importante poder ejecutar una aplicación en un entorno de desarrollo aislado. Puede usar el comando de la CLI docker-compose para crear ese entorno o usar Visual Studio, que usa docker-compose en segundo plano.

El archivo docker-compose.yml le permite configurar y documentar todas las dependencias de servicio de la aplicación (otros servicios, la caché, bases de datos, colas, etc.). Con el comando de la CLI docker-compose puede crear e iniciar uno o varios contenedores para cada dependencia con un solo comando (docker-compose up).

Los archivos docker-compose.yml son archivos de configuración interpretados por el motor de Docker, pero también actúan como prácticos archivos de documentación sobre la composición de la aplicación de varios contenedores.

#### <a name="testing-environments"></a>Entornos de prueba

Una parte importante de cualquier proceso de implementación continua (CD) o de integración continua (CI) son las pruebas unitarias y las pruebas de integración. Estas pruebas automatizadas requieren un entorno aislado, por lo que no se ven afectadas por los usuarios ni por ningún otro cambio efectuado en los datos de la aplicación.

Con Docker Compose puede crear y destruir ese entorno aislado de un modo muy sencillo ejecutando unos scripts o comandos en el símbolo del sistema, como los comandos siguientes:

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a>Implementaciones de producción

También puede usar Compose para efectuar una implementación en un motor de Docker remoto. Un caso típico consiste en efectuar una implementación en una única instancia de host de Docker (como una máquina virtual de producción o un servidor aprovisionado con [Docker Machine](https://docs.docker.com/machine/overview/)). Pero también podría ser todo un clúster de [Docker Swarm](https://docs.docker.com/swarm/overview/), ya que los clústeres también son compatibles con los archivos docker-compose.yml.

Si usa cualquier otro orquestador (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), puede que tenga que agregar valores de configuración de instalación y metadatos como los de docker-compose.yml, pero con el formato que solicita el otro orquestador.

En cualquier caso, docker-compose es una herramienta y un formato de metadatos prácticos para los flujos de trabajo de desarrollo, pruebas y producción, aunque el flujo de trabajo de producción puede variar en el orquestador que está usando.

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a>Usar varios archivos docker-compose para controlar distintos entornos

Al fijar como objetivo entornos diferentes, debe usar varios archivos compose. Así puede crear distintas variantes de configuración en función del entorno.

#### <a name="overriding-the-base-docker-compose-file"></a>Invalidar el archivo base docker-compose

Podría usar un archivo docker-compose.yml como en los ejemplos simplificados que se muestran en las secciones anteriores, pero no se recomienda para la mayoría de las aplicaciones.

De forma predeterminada, Compose lee dos archivos, un archivo docker-compose.yml y un archivo docker-compose.override.yml opcional. Como se muestra en la figura 8-11, al usar Visual Studio y habilitar la compatibilidad de Docker, Visual Studio también crea otro archivo docker-compose.ci.build.yml para que lo use desde sus canalizaciones de CI/CD, como en VSTS.

![](./media/image12.png)

**Figura 8-11**. Archivos docker-compose en Visual Studio 2017

Puede editar los archivos docker-compose con cualquier editor, como Visual Studio Code o Sublime, y ejecutar la aplicación con el comando docker-compose up.

Por convención, el archivo docker-compose.yml contiene la configuración básica y otras opciones estáticas. Esto significa que la configuración del servicio no debería variar según el entorno de implementación que tenga como objetivo.

El archivo docker-compose.override.yml, como su nombre sugiere, contiene valores de configuración que invalidan la configuración básica, como la configuración que depende del entorno de implementación. También puede tener varios archivos de invalidación con nombres diferentes. Los archivos de invalidación suelen contener información adicional necesaria para la aplicación, pero que es específica de un entorno o de una implementación.

#### <a name="targeting-multiple-environments"></a>Fijar como objetivo varios entornos

Un caso de uso típico es cuando se definen varios archivos compose de manera que puede fijar como objetivo varios entornos (por ejemplo, producción, almacenamiento provisional, integración continua o desarrollo). Para dar cabida a estas diferencias, puede dividir la configuración de Compose en varios archivos, como se muestra en la figura 8-12.

![](./media/image13.png)

**Figura 8-12**. Varios archivos docker-compose invalidan los valores del archivo base docker-compose.yml

Comienza con el archivo base docker-compose.yml. Este archivo base debe contener los valores de configuración básicos o estáticos que no varían según el entorno. Por ejemplo, eShopOnContainers tiene el siguiente archivo docker-compose.yml como archivo base.

```yml
#docker-compose.yml (Base)
version: '3'
services:
  basket.api:
    image: eshop/basket.api:${TAG:-latest}
    build:
      context: ./src/Services/Basket/Basket.API
      dockerfile: Dockerfile    
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api:${TAG:-latest}
    build:
      context: ./src/Services/Catalog/Catalog.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - rabbitmq

  marketing.api:
    image: eshop/marketing.api:${TAG:-latest}
    build:
      context: ./src/Services/Marketing/Marketing.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - nosql.data
      - identity.api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: ./src/Web/WebMVC
      dockerfile: Dockerfile    
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api
      - marketing.api

  sql.data:
    image: microsoft/mssql-server-linux:2017-latest

  nosql.data:
    image: mongo

  basket.data:
    image: redis
      
  rabbitmq:
    image: rabbitmq:3-management

```

Los valores del archivo base docker-compose.yml no deberían variar porque haya distintos entornos de implementación de destino.

Si se centra en la definición del servicio webmvc, por ejemplo, puede ver que esa información es la misma con independencia del entorno que fije como objetivo. Dispone de la siguiente información:

-   El nombre del servicio: webmvc.

-   La imagen personalizada del contenedor: eshop/webmvc.

-   El comando para compilar la imagen personalizada de Docker, que indica qué Dockerfile se debe usar.

-   Dependencias de otros servicios, por lo que este contenedor no se inicia hasta que se hayan iniciado los otros contenedores de dependencia.

Puede tener otra configuración, pero lo importante es que en el archivo base docker-compose.yml solo establezca la información que es común en todos los entornos. Luego, en el archivo docker-compose.override.yml o en archivos similares de producción o almacenamiento provisional, debería colocar la configuración específica para cada entorno.

Por lo general, el archivo docker-compose.override.yml se usa para el entorno de desarrollo, como se muestra en el siguiente ejemplo de eShopOnContainers:

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3'

services: 
# Simplified number of services here: 
      
  basket.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basket.data}
      - identityUrl=http://identity.api              
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}      
      - AzureServiceBusEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}

    ports:
      - "5103:80"

  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5101/api/v1/catalog/items/[0]/pic/}   
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}         
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_CATALOG_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_CATALOG_KEY}
      - UseCustomizationData=True
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
    ports:
      - "5101:80"

  marketing.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=Pass@word}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosql.data}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}          
      - identityUrl=http://identity.api              
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - CampaignDetailFunctionUri=${ESHOP_AZUREFUNC_CAMPAIGN_DETAILS_URI}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_MARKETING_URL:-http://localhost:5110/api/v1/campaigns/[0]/pic/}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_MARKETING_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_MARKETING_KEY}
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5110:80"

  webmvc:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
      - LocationsUrl=http://locations.api
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://marketing.api                                                    
      - CatalogUrlHC=http://catalog.api/hc
      - OrderingUrlHC=http://ordering.api/hc
      - IdentityUrlHC=http://identity.api/hc     
      - BasketUrlHC=http://basket.api/hc
      - MarketingUrlHC=http://marketing.api/hc
      - PaymentUrlHC=http://payment.api/hc
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sql.data:
    environment:
      - MSSQL_SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
      - MSSQL_PID=Developer
    ports:
      - "5433:1433"
  nosql.data:
    ports:
      - "27017:27017"
  basket.data:
    ports:
      - "6379:6379"      
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

En este ejemplo, la configuración de invalidación de desarrollo expone algunos puertos al host, define variables de entorno con direcciones URL de redireccionamiento y especifica cadenas de conexión para el entorno de desarrollo. Esta configuración es solo para el entorno de desarrollo.

Al ejecutar `docker-compose up` (o al iniciarlo en Visual Studio), el comando lee las invalidaciones automáticamente como si se combinaran ambos archivos.

Imagínese que quiere que otro archivo Compose para el entorno de producción, con distintos valores de configuración, puertos o cadenas de conexión. Puede crear otro archivo de invalidación, como el archivo llamado `docker-compose.prod.yml`, con distintas configuraciones y variables de entorno.  Ese archivo podría estar almacenado en otro repositorio de Git o lo podría administrar y proteger un equipo diferente.

#### <a name="how-to-deploy-with-a-specific-override-file"></a>Cómo efectuar una implementación con un archivo de invalidación específico

Para usar varios archivos de invalidación, o un archivo de invalidación con otro nombre, puede usar la opción -f con el comando docker-compose y especificar los archivos. Cree los archivos de combinaciones en el orden en que se especifican en la línea de comandos. En el ejemplo siguiente se muestra cómo efectuar la implementación con archivos de invalidación.

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a>Usar variables de entorno en los archivos docker-compose

Resulta práctico, sobre todo en los entornos de producción, poder obtener información de configuración de variables de entorno, como hemos mostrado en ejemplos anteriores. En los archivos docker-compose se hace referencia a una variable de entorno mediante la sintaxis \${MY\_VAR}. En la siguiente línea de un archivo docker-compose.prod.yml se muestra cómo hacer referencia al valor de una variable de entorno.

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

Las variables de entorno se crean y se inicializan de maneras diferentes, en función de su entorno de host (Linux, Windows, clúster en la nube, etc.), aunque un método práctico consiste en usar un archivo .env. Los archivos docker-compose admiten la declaración de variables de entorno predeterminadas en el archivo .env. Estos valores de las variables de entorno son los valores predeterminados, pero se pueden invalidar con los valores que haya podido definir en cada uno de sus entornos (sistema operativo host o variables de entorno del clúster). Este archivo .env se coloca en la carpeta en la que se ejecuta el comando docker-compose.

En el siguiente ejemplo se muestra un archivo .env como el archivo [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) para la aplicación eShopOnContainers.

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

Docker-compose espera que cada línea de los archivos .env tenga el formato &lt;variable&gt;=&lt;valor&gt;.

Tenga en cuenta que los valores establecidos en el entorno en tiempo de ejecución siempre invalidan los valores definidos en el archivo .env. De forma similar, los valores que se pasan a través de argumentos de comando de la línea de comandos también invalidan los valores predeterminados establecidos en el archivo .env.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Overview of Docker Compose (Introducción a Docker Compose)**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)

-   **Multiple Compose files (Varios archivos de Compose)**
    [*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a>Compilación de imágenes optimizadas de Docker de ASP.NET Core

Si está explorando Docker y .NET Core en orígenes de Internet, encontrará Dockerfiles que muestran lo fácil que es compilar una imagen de Docker copiando el origen en un contenedor. Estos ejemplos sugieren que, si usa una configuración simple, puede tener una imagen de Docker con el entorno empaquetado con la aplicación. En el ejemplo siguiente se muestra un Dockerfile sencillo en esta misma línea.

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

Un Dockerfile como este funcionará, pero puede optimizar considerablemente sus imágenes, sobre todo las imágenes de producción.

En el modelo de microservicios y contenedores están iniciando contenedores constantemente. El método habitual de usar los contenedores no reinicia un contenedor inactivo, porque el contenedor se puede descartar. Los orquestadores (como Docker Swarm, Kubernetes, DCOS o Azure Service Fabric) tan solo crean instancias nuevas de imágenes. Esto significa que tendría que efectuar una optimización precompilando la aplicación al crearla para que el proceso de creación de instancias sea más rápido. Cuando se inicia el contenedor, tendría que estar preparado para ejecutarse. No se debería restaurar y compilar en tiempo de ejecución con los comandos dotnet restore y dotnet build desde la CLI de dotnet, como se puede ver en muchas entradas de blog sobre .NET Core y Docker.

El equipo de .NET ha estado trabajando mucho para convertir .NET Core y ASP.NET Core en un marco optimizado para contenedores. .NET Core no es solo un marco de trabajo ligero con una pequeña superficie de memoria. El equipo se ha centrado en el rendimiento de inicio y ha generado algunas imágenes de Docker optimizadas, como la imagen [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/), disponible en [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), en comparación con las imágenes corrientes [Microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) o [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile). La imagen [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) proporciona una configuración automática de aspnetcore\_urls en el puerto 80 y la caché pre-ngend de los ensamblados; ambas configuraciones hacen que el inicio sea más rápido.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Building Optimized Docker Images with ASP.NET Core (Compilación de imágenes de Docker optimizadas con ASP.NET Core)**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)

### <a name="building-the-application-from-a-build-ci-container"></a>Compilación de la aplicación desde un contenedor de compilación (CI)

Otra ventaja de Docker es que se puede compilar una aplicación desde un contenedor preconfigurado, como se muestra en la figura 8-13, por lo que no es necesario crear un equipo de compilación o máquina virtual para compilar la aplicación. Puede usar o probar este contenedor de compilación ejecutándolo en su equipo de desarrollo. Pero lo que es aún más interesante es que puede usar el mismo contenedor de compilación desde su canalización de CI (integración continua).

![](./media/image14.png)

**Figura 8-13**. Contenedor de compilación de Docker que compila los archivos binarios de .NET 

En este escenario proporcionamos la imagen [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/), que se puede usar para compilar y generar sus propias aplicaciones de ASP.NET Core. La salida se coloca en una imagen basada en la imagen [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/), que es una imagen optimizada en tiempo de ejecución, como se ha indicado anteriormente.

La imagen aspnetcore-build contiene todo lo necesario para compilar una aplicación de ASP.NET Core, incluidos .NET Core, el SDK de ASP.NET, npm, Bower, Gulp, etc.

Estas dependencias son necesarias en tiempo de compilación, pero no queremos transportarlas junto con la aplicación en tiempo de ejecución, porque haría que la imagen fuera demasiado grande. En la aplicación eShopOnContainers puede compilar la aplicación desde un contenedor ejecutando el siguiente comando docker-compose.

```
  docker-compose -f docker-compose.ci.build.yml up
```

En la figura 8-14 se muestra este comando ejecutándose en la línea de comandos.

![](./media/image15.png)

**Figura 8-14.** Compilación de la aplicación .NET desde un contenedor

Como puede ver, el contenedor que se ejecuta es el contenedor ci-build\_1. Se basa en la imagen aspnetcore-build para que pueda compilar y generar toda la aplicación desde dentro de ese contenedor en lugar de hacerlo desde su equipo. Es por este motivo que en realidad crea y compila los proyectos de .NET Core en Linux: ese contenedor se está ejecutando en el host de Linux predeterminado de Docker.

El archivo [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) de esa imagen (parte de eShopOnContainers) contiene el siguiente código. Puede ver que inicia un contenedor de compilación mediante la imagen [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/).

```yml
version: '3'

services:

  ci-build:

    image: microsoft/aspnetcore-build:2.0

    volumes:
      - .:/src

    working_dir: /src

    command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && popd && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"

```

* A partir de **.NET Core 2.0**, el comando `dotnet restore` se ejecuta automáticamente cuando se ejecuta el comando `dotnet publish`.

Una vez que el contenedor de compilación está en funcionamiento, ejecuta los comandos dotnet restore y dotnet publish del SDK de .NET en todos los proyectos de la solución con el objetivo de compilar los bits de .NET. En este caso, dado que eShopOnContainers también tiene una SPA basada en TypeScript y Angular para el código de cliente, también debe comprobar las dependencias de JavaScript con npm, pero esa acción no está relacionada con los bits de .NET.

El comando dotnet publish compila y publica la salida compilada dentro de la carpeta de cada proyecto en la carpeta …/obj/Docker/publish, como se muestra en la figura 8-15.

![](./media/image16.png)

**Figura 8-15.** Archivos binarios generados por el comando dotnet publish

#### <a name="creating-the-docker-images-from-the-cli"></a>Creación de las imágenes de Docker desde la CLI

Una vez que se publica la salida de la aplicación en las carpetas relacionadas (dentro de cada proyecto), el siguiente paso consiste en compilar las imágenes de Docker. Para ello, use los comandos docker-compose build y docker-compose up, como muestra en la figura 8-16.

![](./media/image17.png)

**Figura 8-16.** Compilación de imágenes de Docker y ejecución de los contenedores

En la figura 8-17 puede ver cómo se ejecuta el comando docker-compose build

![](./media/image18.png)

**Figura 8-17**. Compilación de las imágenes de Docker con el comando docker-compose build

La diferencia entre el comando docker-compose build y el comando docker-compose up es que docker-compose up compila e inicia las imágenes.

Si usa Visual Studio, todos estos pasos se llevan a cabo en segundo plano. Visual Studio compila la aplicación. NET, crea las imágenes de Docker e implementa los contenedores en el host de Docker. Visual Studio ofrece características adicionales, como la capacidad de depurar los contenedores que se ejecutan en Docker, directamente desde Visual Studio.

Lo importante aquí es que puede compilar la aplicación de la misma manera que debería compilarla la canalización de CI/CD: desde un contenedor y no desde un equipo local. Una vez creadas las imágenes, solo tiene que ejecutar las imágenes de Docker con el comando docker-compose up.

#### <a name="additional-resources"></a>Recursos adicionales

-   **Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code) (Compilar bits desde un contenedor: configurar la solución eShopOnContainers en un entorno de la CLI de Windows [CLI de dotnet, CLI de Docker y código de VS])**
    [*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))


>[!div class="step-by-step"]
[Anterior](data-driven-crud-microservice.md)
[Siguiente](database-server-container.md)
