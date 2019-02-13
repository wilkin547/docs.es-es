---
title: Crear aplicaciones de ASP.NET Core 2.1 implementadas como contenedores de Linux en clústeres de AKS y Kubernetes
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.openlocfilehash: b03b6fab9dcd53e97c2bc4d7e5c958ca4b931077
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221515"
---
# <a name="build-aspnet-core-21-applications-deployed-as-linux-containers-into-akskubernetes-orchestrator"></a>Crear aplicaciones de ASP.NET Core 2.1 implementadas como contenedores de Linux en AKS/Kubernetes orchestrator

Azure Kubernetes Service (AKS) es Kubernetes orquestaciones servicios administrados de Azure que simplifican la administración e implementación de contenedor.

Características principales de AKS son:

- Un plano de control hospedado de Azure
- Actualizaciones automatizadas
- Autorrecuperación
- Escalado configurables de usuario
- Una experiencia de usuario más sencilla para desarrolladores y operadores del clúster.

Los ejemplos siguientes exploración la creación de una aplicación de ASP.NET Core 2.1 se ejecuta en Linux y se implementa en un clúster de AKS en Azure, mientras se realiza el desarrollo con Visual Studio 2017.

## <a name="creating-the-aspnet-core-21-project-using-visual-studio-2017"></a>Crear el proyecto de ASP.NET Core 2.1 con Visual Studio 2017

ASP.NET Core es una plataforma de desarrollo de propósito general mantenida por Microsoft y la Comunidad de .NET en GitHub. Es multiplataforma, admite Windows, macOS y Linux y puede usarse en escenarios de dispositivo, nube, IoT e incrustados.

Este ejemplo usa un proyecto simple que se basa basado en una plantilla de API Web de Visual Studio, por lo que no necesita conocimientos adicionales para crear el ejemplo. Solo debe crear el proyecto con una plantilla estándar que incluye todos los elementos para ejecutar un proyecto pequeño con una API de REST, mediante la tecnología de ASP.NET Core 2.1.

![Agregar ventana nuevo proyecto en Visual Studio, seleccione la aplicación Web ASP.NET Core.](media/create-aspnet-core-application.png)

**Figura 4-36**. Crear aplicación ASP.NET Core

Para crear el proyecto de ejemplo, deberá seleccionar **archivo** > **New** > **proyecto** en Visual Studio. Verá una lista de plantillas para varios tipos de proyectos, donde tiene que buscar **Web** > **.NET Core** en el panel izquierdo. En este ejemplo seleccione **aplicación Web ASP.NET Core**.

En el cuadro de diálogo siguiente Asegúrese de que ha seleccionado .NET Core y ASP.NET Core 2.1 como plataforma de destino en el pulldowns superior, tal como se muestra en la figura 4-37 y, a continuación, seleccione la opción de API, para crear una aplicación de ASP.NET Core Web API.

El .NET Core 2.1 se incluye en Visual Studio 2017, versión 15.7.0 o superior y es automáticamente instalado y configurado para cuando se selecciona el **desarrollo multiplataforma de .NET Core** carga de trabajo durante la instalación.

![Diálogo Visual Studio para seleccionar el tipo de una aplicación Web de ASP.NET Core con la opción de API seleccionada.](media/create-web-api-application.png)

**Figura 4-37**. Tipo de proyecto Web API y seleccione ASP.NET CORE 2.1

Si tiene cualquier versión anterior de .NET Core, puede descargar e instalar la versión 2.1 de <https://www.microsoft.com/net/download/core#/sdk>.

Puede agregar compatibilidad con Docker al crear el proyecto en el paso anterior, o una versión posterior, si es necesario después de iniciar el proyecto. Para agregar la compatibilidad con Docker después de la creación del proyecto, haga doble clic en el archivo de proyecto en el **el Explorador de soluciones** y seleccione **agregar** > **compatibilidad con Docker** en el menú contextual.

![Opción del menú contextual para agregar compatibilidad con Docker a un proyecto existente: Haga clic con el botón derecho (en el proyecto) > Agregar > compatibilidad con Docker.](media/add-docker-support-to-project.png)

**Figura 4-38**. Agregar compatibilidad con Docker al proyecto existente

Para completar la adición de compatibilidad con Docker, tiene la opción de Windows o Linux. En este caso, seleccione **Linux**, ya que AKS no es compatible con contenedores de Windows (como los finales de 2018).

![Cuadro de diálogo para seleccionar el SO de destino para el archivo Dockerfile.](media/select-linux-docker-support.png)

**Figura 4-39**. Seleccionar contenedores de Linux.

Con estos sencillos pasos, tendrá la aplicación de ASP.NET Core 2.1, que se ejecuta en un contenedor de Linux.

Como puede ver, la integración entre Visual Studio 2017 y Docker está totalmente orientada a la productividad del desarrollador.

Ahora puede presionar **F5** para compilar y ejecutar la aplicación.

Después de ejecutar el proyecto, puede enumerar las imágenes mediante la `docker images` comando. Debería ver el `mssampleapplication` imagen creada con la implementación automática de nuestro proyecto de Visual Studio 2017.

```console
docker images
```

![Salida del comando de imágenes de docker, se muestra una lista con la consola: Repositorio, etiqueta, identificador de la imagen, Created (fecha) y tamaño.](media/docker-images-command.png)

**Figura 4-40**. Vista de imágenes de Docker

## <a name="register-the-solution-in-the-azure-container-registry"></a>Registre la solución en Azure Container Registry

Cargar la imagen en cualquier registro de Docker, como [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) o Docker Hub para las imágenes se puedan implementar en el clúster de AKS desde ese registro. En este caso, nos estamos cargando la imagen en Azure Container Registry.

### <a name="create-the-image-in-release-mode"></a>Crear la imagen en modo de lanzamiento

Crear la imagen en **versión** modo (listo para producción) cambiar a la versión como se muestra aquí y presione F5 para ejecutar la aplicación de nuevo.

![Opción de barra de herramientas en Visual Studio para compilar en modo de lanzamiento.](media/select-release-mode.png)

**Figura 4-41**. Seleccionar modo de versión

Si ejecuta el `docker image` comando, verá ambas imágenes creadas. Uno para `debug` y otro para `release` modo.

### <a name="create-a-new-tag-for-the-image"></a>Crear una nueva etiqueta para la imagen

Cada imagen de contenedor debe estar etiquetada con el `loginServer` nombre del registro. Esta etiqueta se utiliza para el enrutamiento al insertar imágenes de contenedor en un registro de imágenes.

Puede ver el `loginServer` nombre desde el portal de Azure, teniendo la información de Azure Container Registry

![Vista de explorador del nombre del registro de contenedor de Azure, en la esquina superior derecha.](media/loginServer-name.png)

**Figura 4-42**. Vista del nombre del registro

O bien ejecutando el siguiente comando:

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Salida del comando anterior en la consola.](media/az-cli-loginServer-name.png)

**Figura 4-43**. Obtener el nombre del registro con PowerShell

En ambos casos, deberá obtener el nombre. En nuestro ejemplo, `mssampleacr.azurecr.io`.

Ahora puede etiquetar la imagen, tomar la última imagen (versión), con el siguiente comando:

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Después de ejecutar el `docker tag` de comandos, enumerar las imágenes con el `docker images` comando. Debería ver la imagen con la nueva etiqueta.

![Salida del comando de imágenes de docker en la consola.](media/tagged-docker-images-list.png)

**Figura 4-44**. Vista de las imágenes etiquetadas

### <a name="push-the-image-into-the-azure-acr"></a>Insertar la imagen en el ACR de Azure

Inserte la imagen en el ACR de Azure, mediante el comando siguiente:

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Este comando tarda unos minutos, pero proporciona comentarios en el proceso de carga de imágenes.

![Salida del comando de inserción de docker de la consola: muestra una barra de progreso basada en caracteres para cada capa.](media/uploading-image-to-acr.png)

**Figura 4-45**. Cargar la imagen en ACR

Puede ver a continuación el resultado que debería obtener cuando se complete el proceso:

![Salida del comando de inserción de docker ha terminado, que muestra todas las capas o nodos en la consola.](media/uploading-docker-images-complete.png)

**Figura 4-46**. Vista de nodos

El siguiente paso es implementar el contenedor en el clúster de Kubernetes de AKS. Para que se necesita un archivo (**.yml implementar el archivo**) que, en este caso, contiene:

```yml
apiVersion: apps/v1beta1
kind: Deployment
metadata:
  name: mssamplesbook
spec:
  replicas: 1
  template:
    metadata:
      labels:
        app: mssample-kub-app
    spec:
      containers:
        - mane: mssample-services-app
          image: mssampleacr.azurecr.io/mssampleaksapplication:v1
          ports:
            - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
    name: mssample-kub-app
spec:
  ports:
    - name: http-port
      port: 80
      targetPort: 80
  selector:
    app: mssample-kub-app
  type: LoadBalancer
```

> [!NOTE]
> Para obtener más información sobre la implementación con Kubernetes, consulte: <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>

Ahora ya está casi listo para implementar mediante **Kubectl**, pero primero debe obtener las credenciales para el clúster de AKS con este comando:

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Salida del comando anterior en la consola: Combinado MSSampleK8Cluster"como el contexto actual en /root/.kube/config](media/getting-aks-credentials.png)

**Figura 4-47**. obtención de credenciales

A continuación, utilice el `kubectl create` comando para iniciar la implementación.

```console
kubectl create -f mssample-deploy.yml
```

![Salida del comando anterior de la consola: implementación "mssamplesbook" creado. servicio "mssample-kub-app" creado.](media/kubectl-create-command.png)

**Figura 4-48**. Implementar en Kubernetes

Cuando se completa la implementación, puede tener acceso a la consola de Kubernetes con un proxy local que puede tener acceso temporalmente con este comando:

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

Y el acceso a la dirección url `http://127.0.0.1:8001`.

![Vista de explorador del panel de Kubernetes, que muestra las implementaciones, Pods, conjuntos de réplicas y los servicios.](media/kubernetes-cluster-information.png)

**Figura 4-49**. Ver información de clúster de Kubernetes

Ahora tiene la aplicación implementada en Azure mediante un contenedor de Linux y un clúster de AKS de Kubernetes. Puede tener acceso a la aplicación que vaya a la dirección IP pública del servicio, que se puede obtener desde el portal de Azure.

> [!NOTE]
> Puede ver cómo crear el clúster de AKS para este ejemplo en la sección [ **implementar a Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) en esta guía.

>[!div class="step-by-step"]
>[Anterior](set-up-windows-containers-with-powershell.md)
>[Siguiente](../docker-devops-workflow/index.md)
