---
title: Compilación de aplicaciones ASP.NET Core 2.2 implementadas como contenedores de Linux en clústeres de AKS/Kubernetes
description: Ciclo de vida de aplicaciones de Docker en contenedor con la plataforma y las herramientas de Microsoft
ms.date: 02/25/2019
ms.openlocfilehash: 83d4d0a60db4bdc112bb35bfbf61c0396646ad31
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989030"
---
# <a name="build-aspnet-core-22-applications-deployed-as-linux-containers-into-an-akskubernetes-orchestrator"></a>Compilación de aplicaciones ASP.NET Core 2.2 implementadas como contenedores de Linux en un orquestador de AKS/Kubernetes

Azure Kubernetes Service (AKS) es un servicio de orquestaciones de Kubernetes administrado de Azure que simplifica la implementación y la administración de contenedores.

Estas son las características principales de AKS:

- Plano de control hospedado en Azure
- Actualizaciones automatizadas
- Recuperación automática
- Escalado configurable por el usuario
- Experiencia de usuario más sencilla para los desarrolladores y los operadores del clúster

En los ejemplos siguientes se explora la creación de una aplicación ASP.NET Core 2.2 que se ejecuta en Linux y se implementa en un clúster de AKS en Azure, mientras que el desarrollo se realiza con Visual Studio 2017.

## <a name="creating-the-aspnet-core-22-project-using-visual-studio-2017"></a>Creación de un proyecto de ASP.NET Core 2.2 con Visual Studio 2017

ASP.NET Core es una plataforma de desarrollo de uso general de cuyo mantenimiento se encargan Microsoft y la comunidad .NET en GitHub. Es multiplataforma, admite Windows, macOS y Linux y puede usarse en escenarios de dispositivo, nube, IoT e incrustados.

En este ejemplo se usa un proyecto simple que se basa en una plantilla de API web de Visual Studio, por lo que no necesita conocimientos adicionales para crear el ejemplo. Solo debe crear el proyecto con una plantilla estándar que incluya todos los elementos para ejecutar un proyecto pequeño con una API de REST, mediante la tecnología de ASP.NET Core 2.2.

![Ventana para agregar nuevo proyecto en Visual Studio, con la aplicación web de ASP.NET Core seleccionada.](media/create-aspnet-core-application.png)

**Figura 4-36**. Creación de una aplicación ASP.NET Core

Para crear el proyecto de ejemplo en Visual Studio, seleccione **Archivo** > **Nuevo** > **Proyecto** y elija el tipo de proyecto **Web** en el panel izquierdo, seguido de **Aplicación web ASP.NET Core**.

En Visual Studio se muestran las plantillas para proyectos web. Para nuestro ejemplo, seleccione **API** para crear una aplicación ASP.NET Web API.

Compruebe que ha seleccionado ASP.NET Core 2.2 como marco. .NET Core 2.2 está incluido en la última versión de Visual Studio 2017 y se instala y configura automáticamente al instalar Visual Studio 2017.

![Cuadro de diálogo de Visual Studio para seleccionar el tipo de aplicación web ASP.NET Core con la opción API seleccionada.](media/create-web-api-application.png)

**Figura 4-37**. Selección de ASP.NET Core 2.2 y del tipo de proyecto API web

Si tiene una versión anterior de .NET Core, puede descargar e instalar la versión 2.2 de <https://dotnet.microsoft.com/download>.

Puede agregar compatibilidad con Docker al crear el proyecto o más adelante, por lo que se puede aplicar Docker al proyecto en cualquier momento. Para agregar compatibilidad con Docker después de crear el proyecto, haga clic con el botón derecho en el nodo del proyecto en el Explorador de soluciones y seleccione **Agregar** > **Compatibilidad con Docker** en el menú contextual.

![Opción del menú contextual para agregar compatibilidad con Docker a un proyecto existente: Haga clic con el botón derecho (en el proyecto) > Agregar > Compatibilidad con Docker.](media/add-docker-support-to-project.png)

**Figura 4-38**. Adición de compatibilidad con Docker a un proyecto existente

Para acabar de agregar compatibilidad con Docker, puede elegir Windows o Linux. En este caso, seleccione **Linux**, ya que AKS no admite contenedores de Windows (a partir de finales de 2018).

![Cuadro de diálogo de opciones para seleccionar el sistema operativo de destino para el archivo Dockerfile.](media/select-linux-docker-support.png)

**Figura 4-39**. Selección de contenedores de Linux

Con estos sencillos pasos, ya tiene la aplicación ASP.NET Core 2.2 en ejecución en un contenedor de Linux.

Como puede ver, la integración entre Visual Studio 2017 y Docker está totalmente orientada a la productividad del desarrollador.

Ahora puede ejecutar la aplicación con la tecla **F5** o el botón **Reproducir**.

Después de ejecutar el proyecto, puede enumerar las imágenes mediante el comando `docker images`. Debería ver la imagen `mssampleapplication` creada por la implementación automática de nuestro proyecto con Visual Studio 2017.

```console
docker images
```

![Salida de la consola del comando de imágenes de Docker, en la que se muestra una lista con los siguientes elementos: Repositorio, Etiqueta, Id. de imagen, Creado (fecha) y Tamaño.](media/docker-images-command.png)

**Figura 4-40**. Vista de imágenes de Docker

## <a name="register-the-solution-in-the-azure-container-registry"></a>Registro de la solución en Azure Container Registry

Cargue la imagen en cualquier registro de Docker, como [Azure Container Registry (ACR)](https://azure.microsoft.com/services/container-registry/) o Docker Hub, para que las imágenes puedan implementarse en el clúster de AKS desde ese registro. En este caso, vamos a cargar la imagen en Azure Container Registry.

### <a name="create-the-image-in-release-mode"></a>Creación de la imagen en modo de versión

Ahora vamos a crear la imagen en el modo de **Versión** (listo para producción). Para ello, cambiaremos a **Versión**, como se muestra en la figura 4-41, y ejecutaremos la aplicación como antes.

![Opción de la barra de herramientas de Visual Studio para compilar en modo de versión.](media/select-release-mode.png)

**Figura 4-41**. Selección del modo de versión

Si ejecuta el comando `docker image`, verá que se crean dos imágenes, una para el modo `debug` y otra para el modo `release`.

### <a name="create-a-new-tag-for-the-image"></a>Creación de una nueva etiqueta para la imagen

Es preciso etiquetar cada imagen de contenedor con el nombre `loginServer` del registro. Esta etiqueta se usa para el enrutamiento al insertar imágenes de contenedor en un registro de imágenes.

Para ver el nombre `loginServer` desde Azure Portal, tome la información de Azure Container Registry.

![Vista del explorador con el nombre de Azure Container Registry en la esquina superior derecha.](media/loginServer-name.png)

**Figura 4-42**. Vista del nombre del Registro

También puede ejecutar el comando siguiente:

```console
az acr list --resource-group MSSampleResourceGroup --query "[].{acrLoginServer:loginServer}" --output table
```

![Salida de la consola del comando anterior.](media/az-cli-loginServer-name.png)

**Figura 4-43**. Obtención del nombre del registro mediante PowerShell

En ambos casos, obtendrá el nombre. En nuestro ejemplo, se trata de `mssampleacr.azurecr.io`.

Ahora puede etiquetar la imagen. Para ello, tome la imagen más reciente (la imagen de versión) con este comando:

```console
docker tag mssampleaksapplication:latest mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Después de ejecutar el comando `docker tag`, muestre las imágenes con el comando `docker images`. Debería ver la imagen con la nueva etiqueta.

![Salida de la consola del comando de imágenes de Docker.](media/tagged-docker-images-list.png)

**Figura 4-44**. Vista de las imágenes etiquetadas

### <a name="push-the-image-into-the-azure-acr"></a>Inserción de la imagen en Azure ACR

Inicie sesión en Azure Container Registry.

```console
az acr login --name mssampleacr
```

Inserte la imagen en Azure ACR con el comando siguiente:

```console
docker push mssampleacr.azurecr.io/mssampleaksapplication:v1
```

Este comando tarda un poco en cargar las imágenes, pero proporciona información durante el proceso.

![Salida de la consola del comando de inserción de Docker en la que se muestra una barra de progreso con caracteres para cada capa.](media/uploading-image-to-acr.png)

**Figura 4-45**. Carga de la imagen en ACR

Puede ver a continuación el resultado que debería obtener cuando se complete el proceso:

![Salida de la consola del comando de inserción de Docker una vez finalizado, en la que se muestran todas las capas o nodos.](media/uploading-docker-images-complete.png)

**Figura 4-46**. Vista de los nodos

El paso siguiente consiste en implementar el contenedor en el clúster de AKS Kubernetes. Para ello, necesita un archivo (un archivo de implementación **.yml**) que contenga lo siguiente:

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
        - name: mssample-services-app
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
> Para obtener más información sobre la implementación con Kubernetes, vea <https://kubernetes.io/docs/reference/kubectl/cheatsheet/>.

Ya está casi listo para realizar la implementación con **Kubectl**, pero primero debe obtener las credenciales para el clúster de AKS con este comando:

```console
az aks get-credentials --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

![Salida de la consola del comando anterior: Merged "MSSampleK8Cluster" as current context in /root/.kube/config](media/getting-aks-credentials.png)

**Figura 4-47**. Obtención de las credenciales

Después, use el comando `kubectl create` para iniciar la implementación.

```console
kubectl create -f mssample-deploy.yml
```

![Salida de la consola del comando anterior: deployment "mssamplesbook" created. service "mssample-kub-app" created.](media/kubectl-create-command.png)

**Figura 4-48**. Implementación en Kubernetes

Una vez completada la implementación, puede acceder a la consola de Kubernetes con un proxy local al que puede acceder temporalmente con este comando:

```console
az aks browse --resource-group MSSampleResourceGroupAKS --name mssampleclusterk801
```

Acceso a la dirección URL `http://127.0.0.1:8001`.

![Vista del explorador del panel de Kubernetes, en el que se muestran los elementos Implementaciones, Pods, Conjuntos de réplicas y Servicios.](media/kubernetes-cluster-information.png)

**Figura 4-49**. Vista de la información del clúster de Kubernetes

Ya tiene la aplicación implementada en Azure mediante un contenedor de Linux y un clúster de AKS Kubernetes. Para acceder a la aplicación, vaya a la dirección IP pública del servicio, que puede obtener en Azure Portal.

> [!NOTE]
> Si quiere saber cómo se crea el clúster de AKS para este ejemplo, vea la sección [**Implementación en Azure Kubernetes Service (AKS)** ](deploy-azure-kubernetes-service.md) de esta guía.

>[!div class="step-by-step"]
>[Anterior](set-up-windows-containers-with-powershell.md)
>[Siguiente](../docker-devops-workflow/index.md)
