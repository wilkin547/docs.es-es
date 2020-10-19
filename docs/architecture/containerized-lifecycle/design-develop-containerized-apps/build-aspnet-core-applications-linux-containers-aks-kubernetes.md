---
title: Compilación de aplicaciones ASP.NET Core implementadas como contenedores de Linux en clústeres de AKS/Kubernetes
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
ms.date: 08/06/2020
ms.openlocfilehash: 8b3141d79eeb252ec3721d57293bed0e335b41d3
ms.sourcegitcommit: a6bd4cad438fe479cbd112eae10f2cd449f06e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2020
ms.locfileid: "91844568"
---
# <a name="build-aspnet-core-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a>Compilación de aplicaciones ASP.NET Core implementadas como contenedores de Linux en un orquestador de AKS/Kubernetes

Azure Kubernetes Service (AKS) es un servicio de orquestaciones de Kubernetes administrado de Azure que simplifica la implementación y la administración de contenedores.

Estas son las características principales de AKS:

- Plano de control hospedado en Azure
- Actualizaciones automatizadas
- Recuperación automática
- Escalado configurable por el usuario
- Experiencia de usuario más sencilla para desarrolladores y operadores de clúster.

En los ejemplos siguientes se examina la creación de una aplicación ASP.NET Core 3.1 que se ejecuta en Linux y se implementa en un clúster de AKS en Azure, mientras que el desarrollo se realiza con Visual Studio 2019.

## <a name="creating-the-aspnet-core-project-using-visual-studio-2019"></a>Creación del proyecto de ASP.NET Core con Visual Studio 2019

ASP.NET Core es una plataforma de desarrollo de uso general de cuyo mantenimiento se encargan Microsoft y la comunidad .NET en GitHub. Es multiplataforma, admite Windows, macOS y Linux y puede usarse en escenarios de dispositivo, nube, IoT e incrustados.

En este ejemplo se usan un par de proyectos simples basados en plantillas de Visual Studio, por lo que no necesita muchos conocimientos adicionales para crear el ejemplo. Solo tiene que crear el proyecto con una plantilla estándar que incluya todos los elementos para ejecutar un proyecto pequeño con una API de REST y una aplicación web con Razor Pages, mediante la tecnología ASP.NET Core 3.1.

![Ventana para agregar nuevo proyecto en Visual Studio, con la aplicación web de ASP.NET Core seleccionada.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-aspnet-core-application.png)

**Figura 4-35**. Creación de una aplicación web ASP.NET Core en Visual Studio 2019.

Para crear el proyecto de ejemplo en Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto**, seleccione el tipo de proyecto **Web** y luego la plantilla **Aplicación web ASP.NET Core**. También puede buscar la plantilla si la necesita.

Luego escriba el nombre y la ubicación de la aplicación como se muestra en la siguiente imagen.

![Escriba el nombre y la ubicación del proyecto.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/enter-project-name-and-location.png)

**Figura 4-36**. Especificación del nombre y la ubicación del proyecto en Visual Studio 2019.

Compruebe que ha seleccionado ASP.NET Core 3.1 como marco. .NET Core 3.1 está incluido en la última versión de Visual Studio 2019 y se instala y configura automáticamente al instalar Visual Studio.

![Cuadro de diálogo de Visual Studio para seleccionar el tipo de aplicación web ASP.NET Core con la opción API seleccionada.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/create-web-api-application.png)

**Figura 4-37**. Selección de ASP.NET Core 3.1 y del tipo de proyecto API web

Observe que la compatibilidad con Docker no está habilitada, solo para mostrar que se puede hacer después de la creación del proyecto.

Si tiene alguna versión anterior de .NET Core, puede descargar e instalar la versión 3.1 desde <https://dotnet.microsoft.com/download>.

Para mostrar que puede "aplicar Docker" al proyecto en cualquier momento, se va a agregar compatibilidad con Docker ahora. Haga clic con el botón derecho en el nodo del proyecto en el Explorador de soluciones y seleccione **Agregar** > **Compatibilidad con Docker** en el menú contextual.

![Opción del menú contextual para agregar compatibilidad con Docker a un proyecto existente: Haga clic con el botón derecho (en el proyecto) > Agregar > Compatibilidad con Docker.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-docker-support-to-project.png)

**Figura 4-38**. Incorporación de compatibilidad con Docker a un proyecto existente

Para acabar de agregar compatibilidad con Docker, puede elegir Windows o Linux. En este caso, seleccione **Linux**.

![Cuadro de diálogo de opciones para seleccionar el sistema operativo de destino para el archivo Dockerfile.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-linux-docker-support.png)

**Figura 4-39**. Selección de contenedores de Linux

Con estos sencillos pasos, ya tiene la aplicación ASP.NET Core 3.1 en ejecución en un contenedor de Linux.

De forma similar, también puede agregar un proyecto **WebApp** muy sencillo (figura 4-40) para usar el punto de conexión de la API web, aunque los detalles no se tratan aquí.

Después, agregue compatibilidad con el orquestador al proyecto **WebApi** como se muestra a continuación, en la imagen 4-40.

![Incorporación de compatibilidad con el orquestador al proyecto WebApi](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/add-orchestrator-support.png)

**Figura 4-40**. Incorporación de compatibilidad con el orquestador al proyecto *WebApi*.

Al seleccionar la opción `Docker Compose`, que es correcta para el desarrollo local, Visual Studio agrega el proyecto docker-compose, con los archivos de docker-compose, como se muestra en la imagen 4-41.

![docker-compose agregado a la solución](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-compose-project-in-visual-studio.png)

**Figura 4-41**. Incorporación de compatibilidad con el orquestador al proyecto *WebApi*.

Los archivos iniciales agregados son similares a estos:

`docker-compose.yml`

```yml
version: "3.4"

services:
  webapi:
    image: ${DOCKER_REGISTRY-}webapi
    build:
      context: .
      dockerfile: WebApi/Dockerfile

  webapp:
    image: ${DOCKER_REGISTRY-}webapp
    build:
      context: .
      dockerfile: WebApp/Dockerfile
```

`docker-compose.override.yml`

```yml
version: "3.4"

services:
  webapi:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
  webapp:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=https://+:443;http://+:80
    ports:
      - "80"
      - "443"
    volumes:
      - ${APPDATA}/Microsoft/UserSecrets:/root/.microsoft/usersecrets:ro
      - ${APPDATA}/ASP.NET/Https:/root/.aspnet/https:ro
```

Para que la aplicación se ejecute con Docker Compose, solo tiene que realizar algunos ajustes en `docker-compose.override.yml`

```yml
services:
  webapi:
    #...
    ports:
      - "51080:80"
      - "51443:443"
    #...
  webapp:
    environment:
      #...
      - WebApiBaseAddress=http://webapi
    ports:
      - "50080:80"
      - "50443:443"
    #...
```

Ahora puede ejecutar la aplicación con la tecla **F5**, mediante el botón **Reproducir**, o bien la tecla **Ctrl+F5** al seleccionar el proyecto docker-compose, como se muestra en la imagen 4-42.

![Ejecución del proyecto docker-compose con Visual Studio](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/running-docker-compose-with-visual-studio.png)

**Figura 4-42**. Incorporación de compatibilidad con el orquestador al proyecto *WebApi*.

Al ejecutar la aplicación docker-compose como se ha explicado, se consigue:

1. Compilar las imágenes y crear los contenedores según el archivo docker-compose.
2. Abrir el explorador en la dirección configurada en el cuadro de diálogo "Propiedades" del proyecto `docker-compose`.
3. Abrir la ventana **Contenedor** (en Visual Studio 2019, versión 16.4 y posteriores).
4. Compatibilidad del depurador con todos los proyectos de la solución, como se muestra en las siguientes imágenes.

Explorador abierto:

![Vista del explorador con aplicación web en ejecución](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/browser-opened.png)

**Figura 4-43**. Ventana del explorador con una aplicación en ejecución en varios contenedores.

Ventana Contenedores:

![Ventana "Contenedores" de Visual Studio](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/visual-studio-containers-window.png)

**Figura 4-44**. Ventana "Contenedores" de Visual Studio

La ventana **Contenedores** permite ver los contenedores en ejecución, examinar las imágenes disponibles, ver variables de entorno, registros y asignaciones de puertos, inspeccionar el sistema de archivos, adjuntar un depurador o abrir una ventana de terminal dentro del entorno del contenedor.

Como puede ver, la integración entre Visual Studio 2019 y Docker está totalmente orientada a la productividad del desarrollador.

Por supuesto, también puede enumerar las imágenes mediante el comando `docker images`. Debería ver las imágenes `webapi` y `webapp` con las etiquetas `dev` creadas por la implementación automática del proyecto con Visual Studio 2019.

```console
docker images
```

![Salida de la consola del comando de imágenes de Docker, en la que se muestra una lista con los siguientes elementos: Repositorio, Etiqueta, Id. de imagen, Creado (fecha) y Tamaño.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/docker-images-command.png)

**Figura 4-45**. Vista de imágenes de Docker

## <a name="register-the-solution-in-an-azure-container-registry-acr"></a>Registro de la solución en una instancia de Azure Container Registry (ACR)

Puede cargar las imágenes en [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/), pero también puede usar Docker Hub o cualquier otro registro de modo que las imágenes puedan implementarse en el clúster de AKS desde ese registro.

### <a name="create-an-acr-instance"></a>Creación de una instancia de ACR

Ejecute el siguiente comando desde **az cli**:

```powershell
az acr create --name exploredocker --resource-group explore-docker-aks-rg --sku basic --admin-enabled
```

> [!NOTE]
> El nombre del registro de contenedor (p. ej. `exploredocker`) debe ser único dentro de Azure y contener entre 5 y 50 caracteres alfanuméricos. Para obtener más información, vea [Creación de un registro de contenedor](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli#create-a-container-registry)

### <a name="create-the-image-in-release-mode"></a>Creación de la imagen en modo de versión

Ahora va a crear la imagen en modo **Versión** (listo para producción). Para ello, cambie a **Versión**, como se muestra en la figura 4-46, y ejecute la aplicación como antes.

![Opción de la barra de herramientas de Visual Studio para compilar en modo de versión.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/select-release-mode.png)

**Figura 4-46**. Selección del modo de versión

Si ejecuta el comando `docker images`, ve que se crean dos imágenes, una para el modo `debug` (**desarrollo**) y otra para el modo `release` (**más reciente**).

### <a name="create-a-new-tag-for-the-image"></a>Creación de una nueva etiqueta para la imagen

Es preciso etiquetar cada imagen de contenedor con el nombre `loginServer` del registro. Esta etiqueta se usa para el enrutamiento al insertar imágenes de contenedor en un registro de imágenes.

Para ver el nombre `loginServer` desde Azure Portal, tome la información de Azure Container Registry.

![Vista del explorador con el nombre de Azure Container Registry en la esquina superior derecha.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/loginServer-name.png)

**Figura 4-47**. Vista del nombre del Registro

También puede ejecutar el comando siguiente:

```console
az acr list --resource-group <resource-group-name> --query "[].{acrLoginServer:loginServer}" --output table
```

![Salida de la consola del comando anterior.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/az-cli-loginServer-name.png)

**Figura 4-48**. Obtención del nombre del registro mediante **az cli**

En ambos casos, obtendrá el nombre. En nuestro ejemplo, se trata de `exploredocker.azurecr.io`.

Ahora puede etiquetar la imagen. Para ello, tome la imagen más reciente (la imagen de versión) con este comando:

```console
docker tag <image-name>:latest <login-server-name>/<image-name>:v1
```

Después de ejecutar el comando `docker tag`, muestre las imágenes con el comando `docker images`. Debería ver la imagen con la nueva etiqueta.

![Salida de la consola del comando de imágenes de Docker.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/tagged-docker-images-list.png)

**Figura 4-49**. Vista de las imágenes etiquetadas

### <a name="push-the-image-into-the-azure-acr"></a>Inserción de la imagen en Azure ACR

Inicie sesión en Azure Container Registry.

```console
az acr login --name exploredocker
```

Inserte la imagen en Azure ACR con el comando siguiente:

```console
docker push <login-server-name>/<image-name>:v1
```

Este comando tarda un poco en cargar las imágenes, pero proporciona información durante el proceso. En la imagen siguiente puede ver la salida de una imagen completada y otra en curso.

![Salida de la consola del comando push de Docker.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/uploading-docker-images-complete.png)

**Figura 4-50**. Salida de la consola del comando push.

Para implementar la aplicación de varios contenedores en el clúster de AKS, necesita algunos archivos `.yaml` de manifiesto que tengan la mayoría de las propiedades tomadas de los archivos `docker-compose.yml` y `docker-compose.override.yml`.

#### `deploy-webapi.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapi
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapi
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapi
    spec:
      containers:
        - name: webapi
          image: exploredocker.azurecr.io/webapi:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
---
apiVersion: v1
kind: Service
metadata:
  name: webapi
  labels:
    app: weather-forecast
    service: webapi
spec:
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapi
```

#### `deploy-webapp.yml`

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: webapp
  labels:
    app: weather-forecast
spec:
  replicas: 1
  selector:
    matchLabels:
      service: webapp
  template:
    metadata:
      labels:
        app: weather-forecast
        service: webapp
    spec:
      containers:
        - name: webapp
          image: exploredocker.azurecr.io/webapp:v1
          imagePullPolicy: IfNotPresent
          ports:
            - containerPort: 80
              protocol: TCP
          env:
            - name: ASPNETCORE_URLS
              value: http://+:80
            - name: WebApiBaseAddress
              value: http://webapi
---
apiVersion: v1
kind: Service
metadata:
  name: webapp
  labels:
    app: weather-forecast
    service: webapp
spec:
  type: LoadBalancer
  ports:
    - port: 80
      targetPort: 80
      protocol: TCP
  selector:
    service: webapp
```

> [!NOTE]
> Los archivos `.yml` anteriores solo habilitan los puertos `HTTP` mediante el parámetro `ASPNETCORE_URLS` para evitar problemas con el certificado que falta en la aplicación de ejemplo.

> [!TIP]
> Si quiere saber cómo se crea el clúster de AKS para este ejemplo, vea la sección [**Implementación en Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) de esta guía.

Ya está casi listo para implementar con **kubectl**, pero primero debe obtener las credenciales del clúster de AKS con este comando:

```console
az aks get-credentials --resource-group explore-docker-aks-rg --name explore-docker-aks
```

![Salida de la consola del comando anterior: "explore-docker-aks" combinado como contexto actual de C:\Users\Miguel.kube\config](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/getting-aks-credentials.png)

**Figura 4-51**. Obtención de credenciales de AKS en el entorno de kubectl.

También debe permitir que el clúster de AKS extraiga imágenes de la instancia de ACR con este comando:

```console
az aks update --name explore-docker-aks --resource-group explore-docker-aks-rg --attach-acr exploredocker
```

El comando anterior puede tardar un par de minutos en terminar. Luego use el comando `kubectl apply` para iniciar las implementaciones; entonces, `kubectl get all` indica los objetos del clúster.

```console
kubectl apply -f deploy-webapi.yml
kubectl apply -f deploy-webapp.yml

kubectl get all
```

![Salida de la consola de los comandos anteriores: implementaciones aplicadas. servicios creados.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubectl-apply-command.png)

**Figura 4-52**. Implementación en Kubernetes

Tiene que esperar un rato para que el equilibrador de carga obtenga la dirección IP externa al consultar con `kubectl get services` y, luego, la aplicación debe estar disponible en esa dirección, como se muestra en la siguiente imagen:

![Vista del explorador de la aplicación implementada en AKS](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/aks-deployed-application.png)

**Figura 4-53**. Implementación en Kubernetes

Una vez finalizada la implementación, puede acceder a la [interfaz de usuario web de Kubernetes](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/) con un proxy local, mediante un túnel SSH.

En primer lugar, debe crear un elemento ClusterRoleBinding con el siguiente comando:

```console
kubectl create clusterrolebinding kubernetes-dashboard --clusterrole=cluster-admin --serviceaccount=kube-system:kubernetes-dashboard
```

Y luego este comando para iniciar el proxy:

```console
az aks browse --resource-group exploredocker-aks-rg --name explore-docker-aks
```

Se debe abrir una ventana del explorador en `http://127.0.0.1:8001` con una vista similar a esta:

![Vista del explorador del panel de Kubernetes, en el que se muestran los elementos Implementaciones, Pods, Conjuntos de réplicas y Servicios.](media/build-aspnet-core-applications-linux-containers-aks-kubernetes/kubernetes-cluster-information.png)

**Figura 4-54**. Vista de la información del clúster de Kubernetes

Ya tiene la aplicación ASP.NET Core en ejecución en contenedores de Linux e implementada en un clúster de AKS en Azure.

> [!NOTE]
> Para obtener más información sobre la implementación con Kubernetes, vea <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>.

> [!div class="step-by-step"]
> [Anterior](set-up-windows-containers-with-powershell.md)
> [Siguiente](../docker-devops-workflow/index.md)
