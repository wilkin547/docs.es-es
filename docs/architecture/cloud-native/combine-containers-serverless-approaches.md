---
title: Combinación de contenedores y enfoques sin servidor para servicios nativos de la nube
description: Combinación de contenedores y Kubernetes con enfoques sin servidor
ms.date: 04/23/2020
ms.openlocfilehash: fe9e9fd5d07132971d64bc6433a762fb7bd22048
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199669"
---
# <a name="combining-containers-and-serverless-approaches"></a>Combinación de los enfoques sin servidor y los contenedores

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Normalmente, las aplicaciones nativas de la nube implementan servicios que aprovechan los contenedores y la orquestación. A menudo, hay oportunidades de exponer algunos de los servicios de la aplicación como Azure Functions. Sin embargo, con una aplicación nativa en la nube implementada en Kubernetes, sería estupendo aprovechar Azure Functions dentro de este mismo conjunto de herramientas. Afortunadamente, puede ajustar Azure Functions dentro de contenedores de Docker e implementarlos con los mismos procesos y herramientas que el resto de la aplicación basada en Kubernetes.

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a>¿Cuándo tiene sentido usar contenedores sin servidor?

La función de Azure no tiene ningún conocimiento de la plataforma en la que se implementa. En algunos escenarios, puede tener requisitos específicos y necesitar personalizar el entorno en el que se ejecutará el código de función. Necesitará una imagen personalizada que admita dependencias o una configuración no admitida por la imagen predeterminada. En estos casos, tiene sentido implementar la función en un contenedor de Docker personalizado.

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a>¿Cuándo debe evitarse el uso de contenedores con Azure Functions?

Si desea usar la facturación de consumo, no podrá ejecutar la función en un contenedor. Además, si implementa la función en un clúster de Kubernetes, ya no se beneficiará del escalado integrado proporcionado por Azure Functions. Tendrá que usar las características de escalado de Kubernetes, descritas anteriormente en este capítulo.

## <a name="how-to-combine-serverless-and-docker-containers"></a>Cómo combinar contenedores de Docker y sin servidor

Para encapsular una función de Azure en un contenedor de Docker, instale el [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) y, a continuación, ejecute el siguiente comando:

```console
func init ProjectName --worker-runtime dotnet --docker
```

Cuando se cree el proyecto, incluirá un Dockerfile y el tiempo de ejecución de trabajo `dotnet`configurado para. Ahora puede crear y probar la función de forma local. Compilarlo y ejecutarlo `docker build` con `docker run` los comandos y. Para obtener pasos detallados para empezar a crear Azure Functions con compatibilidad con Docker, consulte el tutorial [creación de una función en Linux con una imagen personalizada](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) .

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a>Cómo combinar sin servidor y Kubernetes con KEDA

Azure Functions se escala automáticamente para satisfacer la demanda en función de la tasa de eventos que tienen como destino. Siempre puede aprovechar AKS para hospedar sus funciones y usar el escalado automático basado en eventos basado en Kubernetes o KEDA. Cuando no se producen eventos, KEDA se puede reducir verticalmente a cero instancias. [Más información sobre el escalado de Azure Functions con keda](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).

>[!div class="step-by-step"]
>[Anterior](leverage-serverless-functions.md)
>[Siguiente](deploy-containers-azure.md)
