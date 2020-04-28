---
title: Implementación de contenedores en Azure
description: Implementación de contenedores en Azure con Azure Container Registry, Azure Kubernetes Service y Azure Dev Spaces.
ms.date: 04/13/2020
ms.openlocfilehash: 6238460c6129583c34e6b328c38ed9042f32f3d6
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199565"
---
# <a name="deploying-containers-in-azure"></a>Implementación de contenedores en Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

En este capítulo y en el capítulo 1 se describen los contenedores. Hemos visto que los contenedores ofrecen muchas ventajas a las aplicaciones nativas de la nube, incluida la portabilidad. En la nube de Azure, puede implementar los mismos servicios en contenedores en entornos de ensayo y de producción. Azure proporciona varias opciones para hospedar estas cargas de trabajo en contenedores:

- Azure Kubernetes Services (AKS)
- Instancia de Azure Container (ACI)
- Azure Web Apps para contenedores

## <a name="azure-container-registry"></a>Azure Container Registry

Al incluir un microservicio en un contenedor, primero se crea una "imagen". La imagen es una representación binaria del código de servicio, las dependencias y el tiempo de ejecución. Aunque puede crear una imagen de forma manual mediante `Docker Build` el comando de la API de Docker, un enfoque mejor es crearla como parte de un proceso de compilación automatizado.

Una vez creadas, las imágenes de contenedor se almacenan en registros de contenedor. Permiten compilar, almacenar y administrar imágenes de contenedor. Hay muchos registros disponibles, tanto públicos como privados. Azure Container Registry (ACR) es un servicio de registro de contenedor totalmente administrado en la nube de Azure. Conserva las imágenes dentro de la red de Azure, lo que reduce el tiempo de implementación en hosts de contenedor de Azure. También puede protegerlos con los mismos procedimientos de seguridad e identidad que usa para otros recursos de Azure.

Puede crear una Azure Container Registry con las herramientas [Azure portal](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal), [CLI de Azure](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli)o [PowerShell](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell). Crear un registro en Azure es sencillo. Requiere una suscripción de Azure, un grupo de recursos y un nombre único. En la figura 3-11 se muestran las opciones básicas para crear un registro, que se `registryname.azurecr.io`hospedará en.

![Crear un registro de contenedor](./media/create-container-registry.png)

**Figura 3-11**. Crear un registro de contenedor

Una vez que haya creado el registro, deberá autenticarse con él para poder usarlo. Normalmente, se iniciará sesión en el registro mediante el comando CLI de Azure:

```azurecli
az acr login --name *registryname*
```

Una vez autenticado, puede usar los comandos de Docker para insertar imágenes de contenedor en él. Sin embargo, antes de poder hacerlo, debe etiquetar la imagen con el nombre completo (URL) del servidor de inicio de sesión de ACR. Tendrá el formato *nombrederegistro*. azurecr.IO.

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

Después de etiquetar la imagen, use el `docker push` comando para introducir la imagen en la instancia de ACR.

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

Después de insertar una imagen en el registro, se recomienda quitar la imagen del entorno de Docker local mediante este comando:

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

Como procedimiento recomendado, los desarrolladores no deben enviar imágenes manualmente a un registro de contenedor. En su lugar, una canalización de compilación definida en una herramienta como GitHub o Azure DevOps debe ser responsable de este proceso. Obtenga más información en el [capítulo sobre DevOps nativo](devops.md)de la nube.

## <a name="acr-tasks"></a>ACR Tasks

[Las tareas de ACR](https://docs.microsoft.com/azure/container-registry/container-registry-tasks-overview) son un conjunto de características disponibles en el Azure Container Registry. Extiende el [ciclo de desarrollo de bucles internos](https://docs.microsoft.com/dotnet/architecture/containerized-lifecycle/design-develop-containerized-apps/docker-apps-inner-loop-workflow) mediante la creación y administración de imágenes de contenedor en la nube de Azure. En lugar de invocar un `docker build` y `docker push` localmente en el equipo de desarrollo, se controlan automáticamente mediante las tareas de ACR en la nube.

El siguiente comando AZ CLI crea una imagen de contenedor y la envía a ACR:

```azurecli
# create a container registry
az acr create --resource-group myResourceGroup --name myContainerRegistry008 --sku Basic

# build container image in ACR and push it into your container regsitry
az acr build --image sample/hello-world:v1  --registry myContainerRegistry008 --file Dockerfile .
```

Como puede ver en el bloque de comandos anterior, no es necesario instalar Docker Desktop en el equipo de desarrollo. Además, puede configurar los desencadenadores de la tarea ACR para recompilar las imágenes de contenedores en el código fuente y las actualizaciones de la imagen base.

## <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

En este capítulo se explicó Azure Kubernetes Service (AKS). Hemos visto que es el orquestador de contenedor de facto que administra aplicaciones nativas en la nube en contenedor.

Una vez que implemente una imagen en un registro, como ACR, puede configurar AKS para que la Extraiga e implemente automáticamente. Una vez implementada una canalización de CI/CD, puede configurar una estrategia de [versión Canarias](https://martinfowler.com/bliki/CanaryRelease.html) para minimizar el riesgo que conlleva la implementación rápida de las actualizaciones. La nueva versión de la aplicación está configurada inicialmente en producción sin ningún tráfico enrutado a ella. A continuación, el sistema enrutará un pequeño porcentaje de usuarios a la versión implementada recientemente. A medida que el equipo gana confianza en la nueva versión, puede implementar más instancias y retirar el antiguo. AKS admite fácilmente este estilo de implementación.

Como sucede con la mayoría de los recursos de Azure, puede crear un clúster de Azure Kubernetes Service mediante el portal, la línea de comandos o las herramientas de automatización como Helm o terraform. Para empezar a trabajar con un nuevo clúster, debe proporcionar la siguiente información:

- Suscripción a Azure
- Resource group
- Nombre del clúster de Kubernetes
- Region
- Versión de Kubernetes
- Prefijo del nombre DNS
- Tamaño del nodo
- Número de nodos

Esta información es suficiente para comenzar. Como parte del proceso de creación en el Azure Portal, también puede configurar opciones para las siguientes características del clúster:

- Escala
- Autenticación
- Redes
- monitoring
- Etiquetas

[En esta guía de inicio rápido se explica cómo implementar un clúster de AKS mediante el Azure portal](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Las aplicaciones nativas en la nube pueden crecer rápidamente y grandes, lo que requiere recursos de proceso significativos para ejecutarse. En estos casos, toda la aplicación no se puede hospedar en una máquina de desarrollo (especialmente un portátil). Azure Dev Spaces está diseñado para solucionar este problema mediante AKS. Permite a los desarrolladores trabajar con una versión local de sus servicios mientras se hospeda el resto de la aplicación en un clúster de desarrollo de AKS.

Los desarrolladores comparten una instancia en ejecución (desarrollo) en un clúster de AKS que contiene toda la aplicación en contenedor. Pero usan espacios personales configurados en su equipo para desarrollar sus servicios localmente. Cuando está listo, prueban de un extremo a otro en el clúster de AKS, sin replicar las dependencias. Azure Dev Spaces combina el código del equipo local con los servicios de AKS. Los desarrolladores pueden iterar y depurar código directamente en Kubernetes con Visual Studio o Visual Studio Code.

Para comprender el valor de Azure Dev Spaces, déjenos compartir este presupuesto de Gabe Monroy, PM Lead of containers en Microsoft Azure:

> Imagine que es un nuevo empleado que intenta corregir un error en una aplicación de microservicios compleja formada por docenas de componentes, cada uno con su propia configuración y servicios de respaldo. Para empezar, debe configurar el entorno de desarrollo local para que pueda imitar la producción, como la configuración del IDE, la creación de una cadena de herramientas, dependencias de servicio en contenedor, un entorno de Kubernetes local, simulacros para servicios de respaldo, etc. Con todo el tiempo necesario para configurar el entorno de desarrollo, la corrección del primer error puede tardar días.
> O bien, puede usar espacios de desarrollo y AKS.

El proceso para trabajar con Azure Dev Spaces implica los siguientes pasos:

1. Cree el espacio de desarrollo.
2. Configure el espacio de desarrollo raíz.
3. Configure un espacio de desarrollo secundario (para su propia versión del sistema).
4. Conéctese al espacio de desarrollo.

Todos estos pasos se pueden realizar mediante las herramientas de línea de `azds` comandos CLI de Azure y nuevas. Por ejemplo, para crear un nuevo espacio de desarrollo de Azure para un clúster de Kubernetes determinado, usaría un comando como este:

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

Después, puede usar el `azds prep` comando para generar los recursos necesarios de Docker y Helm Chart para ejecutar la aplicación. A continuación, ejecute el código en AKS `azds up`con. La primera vez que ejecute este comando, se instalará el gráfico Helm. Los contenedores se compilarán e implementarán de acuerdo con las instrucciones. Esta tarea puede tardar unos minutos la primera vez que se ejecuta. Sin embargo, después de realizar cambios, puede conectarse a su propio espacio de desarrollo secundario `azds space select` mediante y, después, implementar y depurar las actualizaciones en el espacio de desarrollo secundario aislado. Una vez que tenga el espacio de desarrollo en funcionamiento, puede enviarle actualizaciones mediante la emisión del `azds up` comando, o bien puede usar herramientas integradas en Visual Studio o Visual Studio Code. Con VS Code, use la paleta de comandos para conectarse a su espacio de desarrollo. En la figura 3-12 se muestra cómo iniciar la aplicación web con Azure Dev Spaces en Visual Studio.

![Conéctese a Azure dev Spaces en la](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**figura 3-12**de Visual Studio. Conexión a Azure Dev Spaces en Visual Studio

>[!div class="step-by-step"]
>[Anterior](combine-containers-serverless-approaches.md)
>[Siguiente](scale-containers-serverless.md)
