---
title: Combinación de contenedores y enfoques sin servidor para servicios nativos de la nube
description: Combinación de contenedores y Kubernetes con enfoques sin servidor
ms.date: 05/13/2020
ms.openlocfilehash: 67eee89659026db06eb16ef6f1154ab6935725a4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614206"
---
# <a name="combining-containers-and-serverless-approaches"></a>Combinación de los enfoques sin servidor y los contenedores

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

Cuando se cree el proyecto, incluirá un Dockerfile y el tiempo de ejecución de trabajo configurado para `dotnet` . Ahora puede crear y probar la función de forma local. Compilarlo y ejecutarlo con los `docker build` `docker run` comandos y. Para obtener pasos detallados para empezar a crear Azure Functions con compatibilidad con Docker, consulte el tutorial [creación de una función en Linux con una imagen personalizada](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) .

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a>Cómo combinar sin servidor y Kubernetes con KEDA

En este capítulo, ha visto que la plataforma de Azure Functions se escala horizontalmente de forma automática para satisfacer la demanda. Sin embargo, cuando se implementan funciones en contenedor en AKS, se pierde la funcionalidad de escalado integrada. Al rescate viene [basado en Kubernetes (keda)](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda). Habilita el escalado automático específico para `event-driven Kubernetes workloads,` Incluir funciones en contenedor.

KEDA proporciona funcionalidad de escalado orientada a eventos al tiempo de ejecución de las funciones en un contenedor de Docker. KEDA se puede escalar desde cero instancias (cuando no se producen eventos) `n instances` , en función de la carga. Habilita el escalado automático mediante la exposición de métricas personalizadas al escalador automático de Kubernetes (escalado automático del Pod horizontal). El uso de contenedores de Functions con KEDA hace posible replicar las capacidades de la función sin servidor en cualquier clúster de Kubernetes.

Merece la pena mencionar que el proyecto KEDA está ahora administrado por Cloud Native Computing Foundation (CNCF).

>[!div class="step-by-step"]
>[Anterior](leverage-serverless-functions.md)
>[Siguiente](deploy-containers-azure.md)
