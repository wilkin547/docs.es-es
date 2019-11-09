---
title: Otras opciones de implementación de contenedores
description: Otras opciones de implementación de contenedores con Azure
ms.date: 06/30/2019
ms.openlocfilehash: 1fcb57eedec8c9f5574fffcf409b316332032062
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841166"
---
# <a name="other-container-deployment-options"></a>Otras opciones de implementación de contenedores

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Además de implementar en AKS, también puede implementar contenedores en Azure App Service para contenedores y Azure Container Instances.

## <a name="when-does-it-make-sense-to-deploy-to-app-service-for-containers"></a>¿Cuándo tiene sentido implementar en App Service para contenedores?

Las aplicaciones de producción sencillas que no requieren orquestación son adecuadas para Azure App Service para contenedores.

## <a name="how-to-deploy-to-app-service-for-containers"></a>Cómo implementar en App Service para contenedores

Para implementar en [Azure App Service para contenedores](https://azure.microsoft.com/services/app-service/containers/), debe haber configurado un Azure Container Registry (ACR) y las credenciales para tener acceso a él. Inserte el contenedor que desea hospedar en el registro para que esté disponible para la extracción en el Azure App Service. Una vez creada, puede configurar la aplicación para la implementación continua, que implementará automáticamente las actualizaciones de la aplicación cada vez que actualice su imagen correspondiente en ACR.

## <a name="when-does-it-make-sense-to-deploy-to-azure-container-instances"></a>¿Cuándo tiene sentido implementar en Azure Container Instances?

Azure Container Instances se usan mejor para escenarios de prueba. Proporcionan una manera rápida y sencilla de implementar una aplicación en una instancia de contenedor hospedada en la nube. Úselos para probar o demostrar aplicaciones cuando no necesite las características de escalado y orquestación que ofrece Azure Kubernetes Service.

## <a name="how-to-deploy-an-app-to-azure-container-instances"></a>Cómo implementar una aplicación en Azure Container Instances

Para realizar la implementación en [Azure Container Instances (ACI)](https://docs.microsoft.com/azure/container-instances/), debe haber configurado un Azure Container Registry (ACR) y las credenciales para tener acceso a él. También debe haber insertado previamente la imagen de contenedor en el registro, por lo que está disponible para la extracción en ACI. Puede trabajar con ACI mediante el CLI de Azure o a través del portal. Los registros de contenedor de Azure facilitan la implementación de instancias de contenedores individuales en ACI directamente desde el registro, como se muestra en la figura 3-14.

![Azure Container Registry ejecutar instancia](./media/acr-runinstance-contextmenu.png)

**Figura 3-14**. Azure Container Registry ejecutar instancia

La creación de una instancia de contenedor desde el registro solo requiere que especifique la configuración habitual de Azure (nombre, suscripción, grupo de recursos y ubicación), cuánta memoria se va a asignar al contenedor y en qué puerto debe escuchar. En esta guía de [Inicio rápido se muestra cómo implementar una instancia de contenedor en ACI mediante el Azure portal](https://docs.microsoft.com/azure/container-instances/container-instances-quickstart-portal).

Una vez finalizada la implementación, busque la dirección IP del contenedor recién implementado y comuníquese con ella a través del puerto especificado.

Azure Container Instances ofrece la manera más rápida y sencilla de ejecutar un contenedor en Azure. No es necesario configurar una aplicación de App Service o un orquestador ni tratar las máquinas virtuales. Sin embargo, debido a su simplicidad, ACI debe usarse principalmente con fines de prueba. Si su aplicación requiere escalabilidad automática, varios contenedores configurados para funcionar juntos o cualquier característica más compleja, hay otros servicios de Azure más adecuados y disponibles para hospedar su aplicación.

## <a name="references"></a>Referencias

- [Azure Container Instances docs](https://docs.microsoft.com/azure/container-instances/)
- [Implementación de la instancia de contenedor desde ACR](https://docs.microsoft.com/azure/container-instances/container-instances-using-azure-container-registry#deploy-with-azure-portal)

>[!div class="step-by-step"]
>[Anterior](scale-containers-serverless.md)
>[Siguiente](communication-patterns.md)
