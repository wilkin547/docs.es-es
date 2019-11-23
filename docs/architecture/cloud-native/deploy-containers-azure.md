---
title: Implementación de contenedores en Azure
description: Implementación de contenedores en Azure con Azure Container Registry, Azure Kubernetes Service y Azure Dev Spaces.
ms.date: 06/30/2019
ms.openlocfilehash: 6d95db26b6a45dd6825c88693308ffe90d1ed071
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840488"
---
# <a name="deploying-containers-in-azure"></a>Implementación de contenedores en Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Los contenedores ofrecen muchas ventajas, una de las cuales es la portabilidad. Puede tomar fácilmente el mismo contenedor que ha desarrollado y probado localmente e implementarlo en Azure, donde puede ejecutar la aplicación en entornos de ensayo y de producción. Azure proporciona una serie de opciones para el hospedaje de aplicaciones basadas en contenedores y, de igual forma, admite varios métodos diferentes de implementación. El enfoque más común y más flexible es implementar los contenedores en Azure Container Registry (ACR), donde son accesibles para todos los servicios que desee usar para hospedarlos. Azure Web App for Containers, Azure Kubernetes Services (AKS) y Azure Container Instance (ACI) pueden acceder a las imágenes de contenedor que se han insertado en ACR.

## <a name="azure-container-registry"></a>Azure Container Registry

Azure Container Registry (ACR) le permite compilar, almacenar y administrar imágenes para todas las implementaciones de contenedores. Hay otros registros de contenedor, tanto públicos como privados, en los que puede implementar contenedores. La ventaja de ACR sobre otras opciones es que puede mantener las imágenes cerca de su entorno de producción, lo que mejora los tiempos de compilación e implementación. También puede protegerlos con los mismos procedimientos de seguridad que usa para el resto de los recursos de Azure, lo que mejora la seguridad y reduce el esfuerzo de administración de recursos.

Puede [crear un registro de contenedor mediante Azure portal](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-portal) o [con las herramientas de CLI de Azure](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-azure-cli) o [PowerShell](https://docs.microsoft.com/azure/container-registry/container-registry-get-started-powershell). La creación de un nuevo registro de contenedor solo requiere una suscripción de Azure, un grupo de recursos y un nombre único. En la figura 3-11 se muestran las opciones básicas para crear un registro, que se hospedará en *nombrederegistro*. azurecr.IO.

![crear el registro de contenedor](./media/create-container-registry.png)
**figura 3-11**. Crear registro de contenedor

Una vez que haya creado un registro, debe autenticarse con él para poder usarlo. Normalmente, se iniciará sesión en el registro mediante el comando CLI de Azure:

```azurecli
az acr login --name *registryname*
```

Una vez que haya creado un registro en Azure Container Registry, puede usar los comandos de Docker para insertar imágenes de contenedor en él. Sin embargo, antes de poder hacerlo, primero debe etiquetar la imagen con el nombre completo (URL) del servidor de inicio de sesión de ACR. Tendrá el formato *nombrederegistro*. azurecr.IO.

```console
docker tag mycontainer myregistry.azurecr.io/mycontainer:v1
```

Después de etiquetar la imagen, use el comando `docker push` para enviar la imagen a la instancia de ACR.

```console
docker push myregistry.azurecr.io/mycontainer:v1
```

Después de insertar una imagen en el registro, se recomienda quitar la imagen del entorno de Docker local mediante este comando:

```console
docker rmi myregistry.azurecr.io/mycontainer:v1
```

Los desarrolladores rara vez deben introducir directamente desde sus equipos en un registro de contenedor. En su lugar, una canalización de compilación definida en una herramienta como Azure DevOps debe ser responsable de este proceso. Obtenga más información en el [capítulo sobre DevOps nativo](devops.md)de la nube.

## <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

Si la aplicación basada en contenedor implica varios contenedores, lo más probable es que quiera definir y administrar las interacciones entre los contenedores mediante un *orquestador* como Kubernetes. Una vez que haya implementado las imágenes de contenedor en ACR, puede configurar fácilmente Azure Kubernetes Services para implementar automáticamente imágenes actualizadas de ACR. Una vez completada la canalización de CI/CD, puede configurar una estrategia de [versión Canarias](https://martinfowler.com/bliki/CanaryRelease.html) para minimizar el riesgo que conlleva la implementación rápida de las actualizaciones. La nueva versión de la aplicación está configurada inicialmente en producción sin ningún tráfico enrutado a ella y, a continuación, se enruta un número pequeño de usuarios a la versión implementada recientemente de la aplicación. A medida que el equipo gana confianza en la nueva versión del software, se implementan más instancias de la nueva versión y se retiran las instancias de la versión anterior. AKS admite fácilmente este estilo de implementación.

Como sucede con la mayoría de los recursos de Azure, puede crear clústeres de Azure Kubernetes mediante el portal o mediante herramientas de línea de comandos o herramientas de automatización de infraestructura como Helm o terraform. Para empezar a trabajar con un nuevo clúster, debe proporcionar la siguiente información:

- Suscripción a Azure
- Grupos de recursos
- Nombre del clúster de Kubernetes
- Región
- Versión de Kubernetes
- Prefijo de nombre DNS
- Tamaño del nodo
- Recuento de nodos

Esta información es suficiente para comenzar. Como parte del proceso de creación en el portal de Azure, también puede configurar opciones para las siguientes características del clúster:

- Escala
- Autenticación
- Redes
- Supervisión
- Etiquetas

[En esta guía de inicio rápido se explica cómo implementar un clúster de AKS mediante el Azure portal](https://docs.microsoft.com/azure/aks/kubernetes-walkthrough-portal).

## <a name="azure-dev-spaces"></a>Azure Dev Spaces

Los clústeres de Kubernetes complejos pueden requerir recursos importantes para hospedar, lo que puede dificultar a los desarrolladores la ejecución de toda la aplicación en un solo equipo (especialmente un portátil). Azure Dev Spaces ofrece una solución para esto, ya que permite a los desarrolladores trabajar con sus propias versiones de clústeres de Kubernetes de Azure hospedados en Azure. Azure Dev Spaces está diseñado para facilitar el desarrollo de aplicaciones basadas en microservicios con AKS.

Para comprender el valor de Azure Dev Spaces, déjenos compartir este presupuesto de Gabe Monroy, PM Lead of containers en Microsoft Azure:

"Imagine que es un nuevo empleado que intenta corregir un error en una aplicación de microservicios compleja formada por docenas de componentes, cada uno con su propia configuración y servicios de respaldo. Para empezar, debe configurar el entorno de desarrollo local para que pueda imitar la producción, como la configuración del IDE, la creación de una cadena de herramientas, dependencias de servicio en contenedor, un entorno de Kubernetes local, simulacros para servicios de respaldo, etc. Con todo el tiempo necesario para configurar el entorno de desarrollo, la corrección del primer error puede tardar días.

> O bien, puede usar los espacios de desarrollo y AKS ".

El proceso para trabajar con Azure Dev Spaces implica los siguientes pasos:

1. Cree el espacio de desarrollo.
2. Configure el espacio de desarrollo raíz.
3. Configure un espacio de desarrollo secundario (para su propia versión del sistema).
4. Conéctese al espacio de desarrollo.

Todos estos pasos se pueden realizar mediante las herramientas de línea de comandos CLI de Azure y New `azds`. Por ejemplo, para crear un nuevo espacio de desarrollo de Azure para un clúster de Kubernetes determinado, usaría un comando como este:

```azurecli
az aks use-dev-spaces -g my-aks-resource-group -n MyAKSCluster
```

A continuación, puede usar el comando `azds prep` para generar los recursos necesarios de Docker y Helm Chart para ejecutar la aplicación. A continuación, ejecute el código en AKS con `azds up`. La primera vez que ejecute este comando, se instalará el gráfico Helm y los contenedores se compilarán e implementarán de acuerdo con las instrucciones. Esto puede tardar unos minutos la primera vez que se ejecuta. Sin embargo, después de realizar cambios, puede conectarse a su propio espacio de desarrollo secundario mediante `azds space select` y, a continuación, implementar y depurar las actualizaciones en el espacio de desarrollo secundario aislado. Una vez que tenga el espacio de desarrollo en funcionamiento, puede enviarle actualizaciones volviendo a emitir el comando `azds up` o puede usar herramientas integradas en Visual Studio o Visual Studio Code. Con VS Code, use la paleta de comandos para conectarse a su espacio de desarrollo. En la figura 3-12 se muestra cómo iniciar la aplicación web con Azure Dev Spaces en Visual Studio.

![conectarse a Azure Dev Spaces en Visual Studio](./media/azure-dev-spaces-visual-studio-launchsettings.png)
**figura 3-12**. Conexión a Azure Dev Spaces en Visual Studio

## <a name="references"></a>Referencias

- [Versión Canarias](https://martinfowler.com/bliki/CanaryRelease.html)
- [Azure Dev Spaces con VS Code](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore)
- [Azure Dev Spaces con Visual Studio](https://docs.microsoft.com/azure/dev-spaces/quickstart-netcore-visualstudio)

>[!div class="step-by-step"]
>[Anterior](combine-containers-serverless-approaches.md)
>[Siguiente](scale-containers-serverless.md)
