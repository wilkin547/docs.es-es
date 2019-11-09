---
title: Combinación de los enfoques sin servidor y los contenedores
description: Combinación de contenedores y Kubernetes con enfoques sin servidor
ms.date: 06/30/2019
ms.openlocfilehash: 58aff43adbdd2e629370cc685f32c7b61c25f85e
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840596"
---
# <a name="combining-containers-and-serverless-approaches"></a>Combinación de los enfoques sin servidor y los contenedores

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Con frecuencia, las aplicaciones basadas en microservicios dependen mucho de los contenedores, la orquestación y el paso de mensajes para la comunicación entre los nodos. Esta mensajería es una tarea ideal para Azure Functions, pero con el resto de la aplicación configurada e implementada mediante Kubernetes y herramientas relacionadas, sería conveniente poder aprovechar Azure Functions dentro de este mismo conjunto de herramientas. Afortunadamente, puede ajustar Azure Functions en contenedores de Docker e implementarlos con los mismos procesos y herramientas que el resto de la aplicación basada en Kubernetes.

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a>¿Cuándo tiene sentido usar contenedores sin servidor?

De forma predeterminada, las funciones sin servidor no tienen conocimiento de la plataforma en la que se ejecutarán. Sin embargo, en algunos casos, puede tener requisitos específicos que hacen que sea importante personalizar la imagen de contenedor en la que se ejecutará el código. Puede usar una imagen personalizada porque la función se basa en una versión de idioma concreta o tiene dependencias o requisitos de configuración que no son compatibles con la imagen predeterminada. En estos casos, puede tener sentido personalizar su propio contenedor e implementar la función en un contenedor de Docker personalizado.

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a>¿Cuándo debe evitarse el uso de contenedores con Azure Functions?

Si está esperando beneficiarse de la facturación del plan de consumo de la función, no podrá hacerlo si usa su propio contenedor. Lo que es más, si va más allá del uso de un contenedor de Docker e implementa sus funciones en su propio clúster de Kubernetes, ya no se beneficiará del escalado integrado proporcionado por Azure Functions. Deberá usar las características de escalado de Kubernetes, que se describen a continuación.

## <a name="how-to-combine-serverless-and-docker-containers"></a>Cómo combinar contenedores de Docker y sin servidor

Para encapsular una función de Azure en un contenedor de Docker, instale el Azure Functions Core Tools y, a continuación, ejecute el siguiente comando:

```console
func init ProjectName --docker
```

Elija el tiempo de ejecución de trabajo que desea de las siguientes opciones:

- `dotnet` (C#)
- `node` (JavaScript)
- `python`

Cuando se cree el proyecto, incluirá un Dockerfile. Ahora puede crear y probar la función de forma local. Compilarlo y ejecutarlo con los comandos `docker build` y `docker run`. Para obtener pasos detallados para empezar a crear Azure Functions con compatibilidad con Docker, consulte el tutorial [creación de una función en Linux con una imagen personalizada](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) .

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a>Cómo combinar sin servidor y Kubernetes con KEDA

Azure Functions se escala automáticamente para satisfacer la demanda en función de la tasa de eventos que se dirigen a una función determinada. Además, puede aprovechar Kubernetes para hospedar sus funciones y usar el escalado automático basado en eventos Kubernetes o KEDA. Cuando no se producen eventos, KEDA puede reducir verticalmente a 0 instancias y, a continuación, en respuesta a los eventos, puede escalar verticalmente el número de contenedores para satisfacer la demanda mediante el escalador automático del Pod horizontal. [Más información sobre el escalado de Azure Functions con keda](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).

## <a name="references"></a>Referencias

- [Ejecución de Azure Functions en un contenedor de Docker](https://markheath.net/post/azure-functions-docker)
- [Creación de una función en Linux con una imagen personalizada](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Azure Functions con el escalado automático basado en eventos de Kubernetes](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)

>[!div class="step-by-step"]
>[Anterior](leverage-serverless-functions.md)
>[Siguiente](deploy-containers-azure.md)
