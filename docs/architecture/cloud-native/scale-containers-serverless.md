---
title: Escalado de contenedores y aplicaciones sin servidor
description: Escalado de aplicaciones nativas en la nube con Azure Kubernetes Service para satisfacer la demanda de los usuarios mediante el aumento de los recursos individuales del equipo o el aumento del número de máquinas en un clúster de aplicaciones.
ms.date: 09/23/2019
ms.openlocfilehash: 2d0537fb3ed56beb4eccbf9b8c34a5d87793413b
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841016"
---
# <a name="scaling-containers-and-serverless-applications"></a>Escalado de contenedores y aplicaciones sin servidor

Hay dos formas típicas de escalar una aplicación: escalar verticalmente y escalar horizontalmente. El primero hace referencia a la adición de funcionalidades a un host, mientras que la última hace referencia a agregar al número total de hosts. Una analogía común que se usa para pensar en esto es cómo conseguirse a usted mismo y a algunos amigos de la ciudad. Si solo es un amigo, podría saltar a su coche de carreras de dos plazas. Pero si es tres o cuatro, es posible que necesite realizar una de las SUVs o un furgoneta, escalando verticalmente para aumentar la capacidad. Sin embargo, cuando el número total salta hasta una docena o más, es probable que necesite realizar varios vehículos (a menos que alguien impulse un bus), que muestra el concepto de escalado horizontal mediante la adición de más instancias (en este caso, más vehículos). Veamos cómo se aplica a nuestras aplicaciones.

## <a name="the-simple-solution-scaling-up"></a>Solución simple: escalado vertical

El proceso de actualización de los servidores existentes para darles más recursos (CPU, memoria, velocidad de e/s de disco, velocidad de e/s de red) se conoce como *escalado*vertical. En las aplicaciones nativas de la nube, el escalado vertical no se refiere normalmente a la compra e instalación de hardware real en máquinas físicas, así que elegir un plan más capaz en una lista de opciones disponibles. Normalmente, las aplicaciones nativas en la nube se escalan verticalmente mediante la modificación del tamaño de la máquina virtual (VM) que se usa para hospedar los nodos individuales en el grupo de nodos de Kubernetes. Los conceptos de Kubernetes, como los nodos, los clústeres y los pods se describen en [la sección siguiente](leverage-containers-orchestrators.md). Azure admite una amplia variedad de tamaños de máquina virtual que ejecutan [Windows](https://docs.microsoft.com/azure/virtual-machines/windows/sizes?toc=%2fazure%2fvirtual-machines%2fwindows%2ftoc.json) y [Linux](https://docs.microsoft.com/azure/virtual-machines/linux/sizes). Para escalar verticalmente la aplicación, cree un nuevo grupo de nodos con un tamaño de máquina virtual de nodo mayor y, a continuación, migre las cargas de trabajo al nuevo grupo. Esto requiere [varios grupos de nodos para el clúster de AKS](https://docs.microsoft.com/azure/aks/use-multiple-node-pools), una característica que se encuentra actualmente en versión preliminar. Las aplicaciones sin servidor se escalan verticalmente eligiendo un [plan Premium](https://docs.microsoft.com/azure/azure-functions/functions-scale) y tamaños de instancia Premium o eligiendo un plan de App Service dedicado diferente.

## <a name="scaling-out-cloud-native-apps"></a>Escalado horizontal de aplicaciones nativas en la nube

Las aplicaciones nativas para la nube admiten el escalado horizontal mediante la adición de nodos o pods adicionales a las solicitudes de servicio. Esto puede realizarse manualmente ajustando los valores de configuración de la aplicación (por ejemplo, [escalando un grupo de nodos](https://docs.microsoft.com/azure/aks/use-multiple-node-pools#scale-a-node-pool-manually)) o mediante el *escalado automático*. El escalado automático ajusta los recursos usados por una aplicación para responder a la demanda, de forma similar a como un termostato responde a la temperatura mediante una llamada a para calefacción o refrigeración adicional. Al usar el escalado automático, se deshabilita el escalado manual.

Los clústeres de AKS se pueden escalar de una de estas dos maneras:

- El [escalador automático del clúster](https://docs.microsoft.com/azure/aks/cluster-autoscaler) supervisa los pods que no se pueden programar en los nodos debido a las restricciones de recursos. Agrega nodos adicionales según sea necesario.
- El **escalador automático del Pod horizontal** usa el servidor de métricas en un clúster de Kubernetes para supervisar las demandas de recursos de los pods. Si un servicio necesita más recursos, el escalado automático aumenta el número de pods.

En la figura 3-13 se muestra la relación entre estos dos servicios de escalado.

![Escalado horizontal de un plan de App Service.](./media/aks-cluster-autoscaler.png)

**Figura 3-13**. Escalado horizontal de un plan de App Service.

Estos servicios también pueden reducir el número de pods o nodos según sea necesario. Estos dos servicios pueden funcionar juntos y, a menudo, se implementan juntos en un clúster. Cuando se combina, el escalador automático del Pod horizontal se centra en ejecutar el número de pods necesarios para satisfacer la demanda de la aplicación. El escalador automático del clúster se centra en ejecutar el número de nodos necesarios para admitir los pods programados.

### <a name="scaling-azure-functions"></a>Azure Functions de escalado

Azure Functions admite automáticamente el escalado horizontal. El plan de consumo predeterminado agrega (y quita) recursos dinámicamente en función del número de eventos que entran en la activación. Solo se le cobrará por los recursos de proceso que se usan cuando se ejecutan las funciones en función del número de ejecuciones, el tiempo de ejecución y la memoria usada. Con el plan Premium, obtiene estas mismas características, pero también puede controlar los tamaños de instancia que se usan, tener instancias ya preparadas (para evitar retrasos de inicio en frío) y configurar máquinas virtuales dedicadas en las que ejecutar las funciones. Aunque la configuración predeterminada debe proporcionar una solución económica y escalable para la mayoría de las aplicaciones, la opción Premium permite a los desarrolladores disponer de flexibilidad para los requisitos de Azure Functions personalizados.

## <a name="references"></a>Referencias

- [Grupos de varios nodos de AKS](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)
- [Escalador automático de clústeres de AKS](https://docs.microsoft.com/azure/aks/cluster-autoscaler)
- [Tutorial: escalado de aplicaciones en AKS](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale)
- [Escalado y hospedaje Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-scale)

>[!div class="step-by-step"]
>[Anterior](deploy-containers-azure.md)
>[Siguiente](other-deployment-options.md)
