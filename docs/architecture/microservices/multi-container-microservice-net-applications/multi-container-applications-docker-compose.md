---
title: Definir una aplicación de varios contenedores con docker-compose.yml
description: Cómo se especifica la composición de microservicios para una aplicación de varios contenedores con docker-compose.yml.
ms.date: 01/30/2020
ms.openlocfilehash: c375d328ab9064315682fab91cb5e49e9a384b56
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682671"
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a>Definir una aplicación de varios contenedores con docker-compose.yml

En esta guía, el archivo [docker-compose.yml](https://docs.docker.com/compose/compose-file/) se ha introducido en la sección [Paso 4. Definir los servicios en docker-compose.yml al compilar una aplicación de Docker de varios contenedores](../docker-application-development-process/docker-app-development-workflow.md#step-4-define-your-services-in-docker-composeyml-when-building-a-multi-container-docker-application). Pero hay otras formas de usar los archivos docker-compose que merece la pena examinar con más detalle.

Por ejemplo, puede describir explícitamente cómo quiere implementar la aplicación de varios contenedores en el archivo docker-compose.yml. Si quiere, también puede describir cómo va a compilar las imágenes de Docker personalizadas (las imágenes de Docker personalizadas también se pueden compilar con la CLI de Docker).

Básicamente define cada uno de los contenedores que quiere implementar, además de ciertas características para cada implementación de contenedor. Una vez que tenga un archivo de descripción de la implementación de varios contenedores, puede implementar la solución completa en una sola acción organizada por el comando de la CLI [docker-compose up](https://docs.docker.com/compose/overview/) o bien puede implementarla de forma transparente en Visual Studio. En caso contrario, tendría que usar la CLI de Docker para implementar uno a uno los contenedores en varios pasos mediante el comando `docker run` desde la línea de comandos. Por lo tanto, cada servicio definido en el archivo docker-compose.yml debe especificar exactamente una imagen o compilación. El resto de las claves son opcionales y son análogas a sus equivalentes de la línea de comandos de `docker run`.

El siguiente código YAML es la definición de un archivo docker-compose.yml posiblemente global pero único para el ejemplo de eShopOnContainers. Este no es el archivo docker-compose real de eShopOnContainers, sino que es una versión simplificada y consolidada en un único archivo, lo cual no es la mejor manera de trabajar con archivos docker-compose, como se explicará más adelante.

```yml
version: '3.4'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog-api
      - OrderingUrl=http://ordering-api
      - BasketUrl=http://basket-api
    ports:
      - "5100:80"
    depends_on:
      - catalog-api
      - ordering-api
      - basket-api

  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata

  ordering-api:
    image: eshop/ordering-api
    environment:
      - ConnectionString=Server=sqldata;Database=Services.OrderingDb;User Id=sa;Password=your@password
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata

  basket-api:
    image: eshop/basket-api
    environment:
      - ConnectionString=sqldata
    ports:
      - "5103:80"
    depends_on:
      - sqldata

  sqldata:
    environment:
      - SA_PASSWORD=your@password
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basketdata:
    image: redis
```

La clave raíz de este archivo es "services" (servicios). En esa clave se definen los servicios que se quieren implementar y ejecutar al ejecutar el comando `docker-compose up`, o bien al implementarlos desde Visual Studio mediante este archivo docker-compose.yml. En este caso, el archivo docker-compose.yml tiene varios servicios definidos, como se describe en la tabla siguiente.

| Nombre del servicio | Descripción |
|--------------|-------------|
| webmvc       | Contenedor que incluye la aplicación ASP.NET Core MVC que consume los microservicios de C\# del lado servidor|
| catalog-api  | Contenedor que incluye el microservicio Catalog de la API web de ASP.NET Core |
| ordering-api | Contenedor que incluye el microservicio Ordering de la API web de ASP.NET Core |
| sqldata     | Contenedor que ejecuta SQL Server para Linux, que contiene las bases de datos de microservicios |
| basket-api   | Contenedor que incluye el microservicio Basket de la API web de ASP.NET Core |
| basketdata  | Contenedor que ejecuta el servicio Redis Cache, con la base de datos Basket como caché de Redis |

### <a name="a-simple-web-service-api-container"></a>Contenedor de la API de servicio web simple

Si nos centramos en un único contenedor, el microservicio de contenedor catalog-api tiene una definición sencilla:

```yml
  catalog-api:
    image: eshop/catalog-api
    environment:
      - ConnectionString=Server=sqldata;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sqldata
```

Este servicio de contenedor tiene la siguiente configuración básica:

- Se basa en la imagen **eshop/catalog-api** personalizada. Por simplicidad, no hay ninguna compilación: configuración de clave en el archivo. Esto significa que la imagen se debe haber compilado previamente (con docker build) o se debe haber descargado (con el comando docker pull) de cualquier registro de Docker.

- Define una variable de entorno denominada ConnectionString con la cadena de conexión para que la use Entity Framework para obtener acceso a la instancia de SQL Server que contiene el modelo de datos del catálogo. En este caso, el mismo contenedor de SQL Server contiene varias bases de datos. Por lo tanto, necesitará menos memoria en el equipo de desarrollo para Docker, aunque también podría implementar un contenedor de SQL Server para cada base de datos de microservicio.

- El nombre de SQL Server es **sqldata**, que es el mismo nombre que se usa para el contenedor que ejecuta la instancia de SQL Server para Linux. Esto resulta práctico: poder usar esta resolución de nombres (interna al host de Docker) resolverá la dirección de red, por lo que no necesita saber la dirección IP interna de los contenedores a los que tiene acceso desde otros contenedores.

Dado que la cadena de conexión se define mediante una variable de entorno, podría establecer esa variable mediante otro mecanismo y en otro momento. Por ejemplo, podría establecer una cadena de conexión diferente al efectuar una implementación en producción en los hosts finales, o haciéndolo desde sus canalizaciones de CI/CD en Azure DevOps Services o en su sistema de DevOps preferido.

- Expone el puerto 80 para el acceso interno al servicio **catalog-api** dentro del host de Docker. Actualmente, el host es una máquina virtual de Linux porque se basa en una imagen de Docker para Linux, aunque podría configurar el contenedor para que se ejecute en una imagen de Windows.

- Reenvía el puerto 80 expuesto del contenedor al puerto 5101 del equipo host de Docker (la máquina virtual de Linux).

- Vincula el servicio web al servicio **sqldata** (la base de datos de instancias de SQL Server para Linux que se ejecuta en un contenedor). Al especificar esta dependencia, el contenedor catalog-api no se iniciará hasta que se haya iniciado el contenedor sqldata. Esto es importante porque catalog-api necesita primero que la base de datos de SQL Server esté en ejecución. Pero este tipo de dependencia de contenedor no es suficiente en muchos casos, dado que Docker efectúa comprobaciones únicamente en el nivel de contenedor. A veces es posible que el servicio (en este caso SQL Server) aún no esté listo, por lo que es aconsejable implementar la lógica de reintento con retroceso exponencial en los microservicios de su cliente. De este modo, si un contenedor de dependencia no está listo durante un período de tiempo breve, la aplicación seguirá siendo resistente.

- Está configurado para permitir el acceso a los servidores externos: el valor de configuración extra\_hosts le permite obtener acceso a máquinas o servidores externos situados fuera del host de Docker (es decir, fuera de la máquina virtual de Linux predeterminada, que es un host de Docker de desarrollo), como una instancia local de SQL Server en su equipo de desarrollo.

También existen otras opciones más avanzadas de los archivos `docker-compose.yml` que se exponen en las siguientes secciones.

### <a name="using-docker-compose-files-to-target-multiple-environments"></a>Usar archivos docker-compose para fijar como objetivo varios entornos

Los archivos `docker-compose.*.yml` son archivos de definición que se pueden usar en varias infraestructuras que comprendan ese formato. La herramienta más sencilla y directa es el comando docker-compose.

Por lo tanto, si usa el comando docker-compose, puede fijar como objetivo los siguientes escenarios principales.

#### <a name="development-environments"></a>Entornos de desarrollo

Al desarrollar aplicaciones, es importante poder ejecutar una aplicación en un entorno de desarrollo aislado. Puede usar el comando de la CLI docker-compose para crear ese entorno o Visual Studio, que usa docker-compose en segundo plano.

El archivo docker-compose.yml le permite configurar y documentar todas las dependencias de servicio de la aplicación (otros servicios, la caché, bases de datos, colas, etc.). Con el comando de la CLI docker-compose puede crear e iniciar uno o varios contenedores para cada dependencia con un solo comando (docker-compose up).

Los archivos docker-compose.yml son archivos de configuración interpretados por el motor de Docker, pero también actúan como prácticos archivos de documentación sobre la composición de la aplicación de varios contenedores.

#### <a name="testing-environments"></a>Entornos de prueba

Una parte importante de cualquier proceso de implementación continua (CD) o de integración continua (CI) son las pruebas unitarias y las pruebas de integración. Estas pruebas automatizadas requieren un entorno aislado, por lo que no se ven afectadas por los usuarios ni por ningún otro cambio efectuado en los datos de la aplicación.

Con Docker Compose puede crear y destruir ese entorno aislado de un modo muy sencillo ejecutando unos scripts o comandos en el símbolo del sistema, como los comandos siguientes:

```console
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml up -d
./run_unit_tests
docker-compose -f docker-compose.yml -f docker-compose-test.override.yml down
```

#### <a name="production-deployments"></a>Implementaciones de producción

También puede usar Compose para efectuar una implementación en un motor de Docker remoto. Un caso típico consiste en efectuar una implementación en una única instancia de host de Docker (como una máquina virtual de producción o un servidor aprovisionado con [Docker Machine](https://docs.docker.com/machine/overview/)).

Si usa cualquier otro orquestador (Azure Service Fabric, Kubernetes, etc.), es posible que tenga que agregar valores de configuración de instalación y metadatos como los de docker-compose.yml, pero con el formato necesario para el otro orquestador.

En cualquier caso, docker-compose es una herramienta y un formato de metadatos prácticos para los flujos de trabajo de desarrollo, pruebas y producción, aunque el flujo de trabajo de producción puede variar en el orquestador que está usando.

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a>Usar varios archivos docker-compose para controlar distintos entornos

Al fijar como objetivo entornos diferentes, debe usar varios archivos compose. Así puede crear distintas variantes de configuración en función del entorno.

#### <a name="overriding-the-base-docker-compose-file"></a>Invalidar el archivo base docker-compose

Podría usar un archivo docker-compose.yml como en los ejemplos simplificados que se muestran en las secciones anteriores, pero no se recomienda para la mayoría de las aplicaciones.

De forma predeterminada, Compose lee dos archivos, un archivo docker-compose.yml y un archivo docker-compose.override.yml opcional. Como se muestra en la figura 6-11, cuando se usa Visual Studio y se habilita la compatibilidad con Docker, Visual Studio también crea un archivo docker-compose.vs.debug.g.yml adicional para depurar la aplicación, como se puede ver en la carpeta obj\\Docker\\ de la carpeta de la solución principal.

![Archivos de un proyecto de Docker Compose.](./media/multi-container-applications-docker-compose/docker-compose-file-visual-studio.png)

**Figura 6-11**. Archivos docker-compose en Visual Studio 2019

Estructura de los archivos de un proyecto de **docker-compose**:

- *.dockerignore*: se usa para omitir archivos.
- *docker-compose.yml*: se usa para crear microservicios.
- *docker-compose.override.yml*: se usa para configurar el entorno de microservicios.

Puede editar los archivos docker-compose con cualquier editor, como Visual Studio Code o Sublime, y ejecutar la aplicación con el comando docker-compose up.

Por convención, el archivo docker-compose.yml contiene la configuración básica y otras opciones estáticas. Esto significa que la configuración del servicio no debería variar según el entorno de implementación que tenga como objetivo.

El archivo docker-compose.override.yml, como su nombre sugiere, contiene valores de configuración que invalidan la configuración básica, como la configuración que depende del entorno de implementación. También puede tener varios archivos de invalidación con nombres diferentes. Los archivos de invalidación suelen contener información adicional necesaria para la aplicación, pero que es específica de un entorno o de una implementación.

#### <a name="targeting-multiple-environments"></a>Fijar como objetivo varios entornos

Un caso de uso típico es cuando se definen varios archivos compose de manera que puede fijar como objetivo varios entornos (por ejemplo, producción, almacenamiento provisional, integración continua o desarrollo). Para dar cabida a estas diferencias, la configuración de Compose se puede dividir en varios archivos, como se muestra en la figura 6-12.

![Diagrama de tres archivos de docker-compose establecidos para invalidar el archivo base.](./media/multi-container-applications-docker-compose/multiple-docker-compose-files-override-base.png)

**Figura 6-12**. Varios archivos docker-compose invalidan los valores del archivo base docker-compose.yml

Se pueden combinar varios archivos docker-compose*.yml para controlar otros entornos. Comienza con el archivo base docker-compose.yml. Este archivo base debe contener los valores de configuración básicos o estáticos que no varían según el entorno. Por ejemplo, la aplicación eShopOnContainers tiene el siguiente archivo docker-compose.yml (simplificado con menos servicios) como archivo base.

```yml
#docker-compose.yml (Base)
version: '3.4'
services:
  basket-api:
    image: eshop/basket-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Basket/Basket.API/Dockerfile
    depends_on:
      - basketdata
      - identity-api
      - rabbitmq

  catalog-api:
    image: eshop/catalog-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Catalog/Catalog.API/Dockerfile
    depends_on:
      - sqldata
      - rabbitmq

  marketing-api:
    image: eshop/marketing-api:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Services/Marketing/Marketing.API/Dockerfile
    depends_on:
      - sqldata
      - nosqldata
      - identity-api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: .
      dockerfile: src/Web/WebMVC/Dockerfile
    depends_on:
      - catalog-api
      - ordering-api
      - identity-api
      - basket-api
      - marketing-api

  sqldata:
    image: mcr.microsoft.com/mssql/server:2017-latest

  nosqldata:
    image: mongo

  basketdata:
    image: redis

  rabbitmq:
    image: rabbitmq:3-management

```

Los valores del archivo base docker-compose.yml no deberían variar porque haya distintos entornos de implementación de destino.

Si se centra en la definición del servicio webmvc, por ejemplo, puede ver que esa información es la misma con independencia del entorno que fije como objetivo. Dispone de la siguiente información:

- El nombre del servicio: webmvc.

- La imagen personalizada del contenedor: eshop/webmvc.

- El comando para compilar la imagen personalizada de Docker, que indica qué Dockerfile se debe usar.

- Dependencias de otros servicios, por lo que este contenedor no se inicia hasta que se hayan iniciado los otros contenedores de dependencia.

Puede tener otra configuración, pero lo importante es que en el archivo base docker-compose.yml solo establezca la información que es común en todos los entornos. Luego, en el archivo docker-compose.override.yml o en archivos similares de producción o almacenamiento provisional, debería colocar la configuración específica para cada entorno.

Por lo general, el archivo docker-compose.override.yml se usa para el entorno de desarrollo, como se muestra en el siguiente ejemplo de eShopOnContainers:

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3.4'

services:
# Simplified number of services here:

  basket-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basketdata}
      - identityUrl=http://identity-api
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

  catalog-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sqldata;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5202/api/v1/catalog/items/[0]/pic/}
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

  marketing-api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sqldata;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=Pass@word}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosqldata}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}
      - identityUrl=http://identity-api
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
      - PurchaseUrl=http://webshoppingapigw
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://webmarketingapigw
      - CatalogUrlHC=http://catalog-api/hc
      - OrderingUrlHC=http://ordering-api/hc
      - IdentityUrlHC=http://identity-api/hc
      - BasketUrlHC=http://basket-api/hc
      - MarketingUrlHC=http://marketing-api/hc
      - PaymentUrlHC=http://payment-api/hc
      - SignalrHubUrl=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5202
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sqldata:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
  nosqldata:
    ports:
      - "27017:27017"
  basketdata:
    ports:
      - "6379:6379"
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

En este ejemplo, la configuración de invalidación de desarrollo expone algunos puertos al host, define variables de entorno con direcciones URL de redireccionamiento y especifica cadenas de conexión para el entorno de desarrollo. Esta configuración es solo para el entorno de desarrollo.

Al ejecutar `docker-compose up` (o al iniciarlo en Visual Studio), el comando lee las invalidaciones automáticamente como si se combinaran ambos archivos.

Imagínese que quiere que otro archivo Compose para el entorno de producción, con distintos valores de configuración, puertos o cadenas de conexión. Puede crear otro archivo de invalidación, como el archivo llamado `docker-compose.prod.yml`, con distintas configuraciones y variables de entorno. Ese archivo podría estar almacenado en otro repositorio de Git o lo podría administrar y proteger un equipo diferente.

#### <a name="how-to-deploy-with-a-specific-override-file"></a>Cómo efectuar una implementación con un archivo de invalidación específico

Para usar varios archivos de invalidación, o un archivo de invalidación con otro nombre, puede usar la opción -f con el comando docker-compose y especificar los archivos. Cree los archivos de combinaciones en el orden en que se especifican en la línea de comandos. En el ejemplo siguiente se muestra cómo efectuar la implementación con archivos de invalidación.

```console
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a>Usar variables de entorno en los archivos docker-compose

Resulta práctico, sobre todo en los entornos de producción, poder obtener información de configuración de variables de entorno, como hemos mostrado en ejemplos anteriores. En los archivos docker-compose se puede hacer referencia a una variable de entorno mediante la sintaxis ${MY\_VAR}. En la siguiente línea de un archivo docker-compose.prod.yml se muestra cómo hacer referencia al valor de una variable de entorno.

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

Las variables de entorno se crean y se inicializan de maneras diferentes, en función de su entorno de host (Linux, Windows, clúster en la nube, etc.), aunque un método práctico consiste en usar un archivo .env. Los archivos docker-compose admiten la declaración de variables de entorno predeterminadas en el archivo .env. Estos valores de las variables de entorno son los valores predeterminados, pero se pueden invalidar con los valores que haya podido definir en cada uno de sus entornos (sistema operativo host o variables de entorno del clúster). Este archivo .env se coloca en la carpeta en la que se ejecuta el comando docker-compose.

En el siguiente ejemplo se muestra un archivo .env como el archivo [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) para la aplicación eShopOnContainers.

```sh
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

Docker-compose espera que cada línea de un archivo .env tenga el formato \<variable\>=\<value\>.

Los valores establecidos en el entorno en tiempo de ejecución siempre invalidan los valores definidos en el archivo .env. De forma similar, los valores que se pasan a través de argumentos de la línea de comandos también invalidan los valores predeterminados establecidos en el archivo .env.

#### <a name="additional-resources"></a>Recursos adicionales

- **Introducción a Docker Compose** \
    <https://docs.docker.com/compose/overview/>

- **Varios archivos de Compose** \
    [https://docs.docker.com/compose/extends/\#multiple-compose-files](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a>Compilación de imágenes optimizadas de Docker de ASP.NET Core

Si está explorando Docker y .NET Core en orígenes de Internet, encontrará Dockerfiles que muestran lo fácil que es compilar una imagen de Docker copiando el origen en un contenedor. Estos ejemplos sugieren que, si usa una configuración simple, puede tener una imagen de Docker con el entorno empaquetado con la aplicación. En el ejemplo siguiente se muestra un Dockerfile sencillo en esta misma línea.

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:3.1
WORKDIR /app
ENV ASPNETCORE_URLS http://+:80
EXPOSE 80
COPY . .
RUN dotnet restore
ENTRYPOINT ["dotnet", "run"]
```

Un Dockerfile como este funcionará, pero puede optimizar considerablemente sus imágenes, sobre todo las imágenes de producción.

En el modelo de microservicios y contenedores están iniciando contenedores constantemente. El método habitual de usar los contenedores no reinicia un contenedor inactivo, porque el contenedor se puede descartar. Los orquestadores (como Kubernetes y Azure Service Fabric) tan solo crean instancias de imágenes. Esto significa que tendría que efectuar una optimización precompilando la aplicación al crearla para que el proceso de creación de instancias sea más rápido. Cuando se inicia el contenedor, tendría que estar preparado para ejecutarse. No restaure ni compile en tiempo de ejecución con los comandos `dotnet restore` y `dotnet build` de la CLI, como puede ver en las entradas de blog sobre .NET Core y Docker.

El equipo de .NET ha estado trabajando mucho para convertir .NET Core y ASP.NET Core en un marco optimizado para contenedores. .NET Core no solo es un marco ligero con una superficie de memoria pequeña; el equipo se ha centrado en imágenes de Docker optimizadas para los tres escenarios principales y las han publicado en el registro de Docker Hub en *dotnet/core*, empezando por la versión 2.1:

1. **Desarrollo**: La prioridad es la capacidad de iterar con rapidez y depurar cambios, donde el tamaño es secundario.

2. **Compilación**: la prioridad es compilar la aplicación y la imagen incluye los archivos binarios y otras dependencias para optimizar los archivos binarios.

3. **Producción**: El foco es la implementación y el inicio rápido de los contenedores, por lo que estas imágenes se limitan a los archivos binarios y el contenido necesario para ejecutar la aplicación.

El equipo de .NET proporciona tres variantes básicas en [dotnet/core](https://hub.docker.com/_/microsoft-dotnet/) (en Docker Hub):

1. **sdk**: para los escenarios de desarrollo y compilación
1. **aspnet**: para los escenarios de producción de ASP.NET
1. **runtime**: para los escenarios de producción de .NET
1. **runtime-deps**: para los escenarios de producción de [aplicaciones autocontenidas](../../../core/deploying/index.md#publish-self-contained)

Para un inicio más rápido, las imágenes en tiempo de ejecución también configuran automáticamente las direcciones URL\_aspnetcore en el puerto 80 y usan Ngen para crear una caché de imágenes nativa de ensamblados.

#### <a name="additional-resources"></a>Recursos adicionales

- **Building Optimized Docker Images with ASP.NET Core** (Compilación de imágenes de Docker optimizadas con ASP.NET Core)  
  <https://docs.microsoft.com/archive/blogs/stevelasker/building-optimized-docker-images-with-asp-net-core>

- **Creación de imágenes de Docker para aplicaciones de .NET Core**  
  [https://docs.microsoft.com/dotnet/core/docker/building-net-docker-images](/aspnet/core/host-and-deploy/docker/building-net-docker-images)

> [!div class="step-by-step"]
> [Anterior](data-driven-crud-microservice.md)
> [Siguiente](database-server-container.md)
