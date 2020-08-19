---
title: Almacenamiento en caché en una aplicación nativa en la nube
description: Obtenga información sobre las estrategias de almacenamiento en caché en una aplicación nativa en la nube.
author: robvet
ms.date: 05/17/2020
ms.openlocfilehash: a33f143499b5f9545493bc4bc757cc3d152f7aa9
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557521"
---
# <a name="caching-in-a-cloud-native-app"></a>Almacenamiento en caché en una aplicación nativa en la nube

Las ventajas del almacenamiento en caché se entienden bien. La técnica funciona mediante la copia temporal de los datos a los que se accede con frecuencia desde un almacén de datos de back-end a un *almacenamiento rápido* que se encuentra más cerca de la aplicación. El almacenamiento en caché se implementa a menudo...

- Los datos permanecen relativamente estáticos.
- El acceso a los datos es lento, especialmente en comparación con la velocidad de la memoria caché.
- Los datos están sujetos a altos niveles de contención.

## <a name="why"></a>¿Por qué?

Como se describe en la [Guía de almacenamiento en caché de Microsoft](https://docs.microsoft.com/azure/architecture/best-practices/caching), el almacenamiento en caché puede aumentar el rendimiento, la escalabilidad y la disponibilidad de microservicios individuales y del sistema en su conjunto. Reduce la latencia y la contención de administrar grandes volúmenes de solicitudes simultáneas en un almacén de datos. A medida que el volumen de datos y el número de usuarios aumentan, mayores son las ventajas del almacenamiento en caché.

El almacenamiento en caché es más eficaz cuando un cliente Lee repetidamente datos que son inmutables o que cambian con poca frecuencia. Entre los ejemplos se incluye información de referencia, como información de productos y precios, o recursos estáticos compartidos que son costosos de construir.

Aunque los microservicios no deben tener estado, una caché distribuida puede admitir el acceso simultáneo a los datos de estado de sesión cuando es absolutamente necesario.

Considere también el almacenamiento en caché para evitar cálculos repetitivos. Si una operación transforma datos o realiza un cálculo complicado, almacene en caché el resultado de las solicitudes posteriores.

## <a name="caching-architecture"></a>Arquitectura de almacenamiento en caché

Las aplicaciones nativas en la nube suelen implementar una arquitectura de almacenamiento en caché distribuida. La memoria caché se hospeda como un servicio de [respaldo](./definition.md#backing-services)basado en la nube, independiente de los microservicios. En la figura 5-15 se muestra la arquitectura.

![Almacenamiento en caché en una aplicación nativa en la nube](media/caching-in-a-cloud-native-app.png)

**Figura 5-15**: almacenamiento en caché en una aplicación nativa en la nube

En la ilustración anterior, observe cómo la memoria caché es independiente y compartida por los microservicios. En este escenario, la [puerta de enlace de API](./front-end-communication.md)invoca la memoria caché. Como se describe en el capítulo 4, la puerta de enlace actúa como front-end para todas las solicitudes entrantes. La caché distribuida aumenta la capacidad de respuesta del sistema al devolver los datos almacenados en caché siempre que sea posible. Además, la separación de la memoria caché de los servicios permite escalar vertical u horizontalmente la memoria caché de forma independiente para satisfacer mayores demandas de tráfico.

En la ilustración anterior se muestra un patrón de almacenamiento en caché común conocido como el [patrón de reserva de caché](https://docs.microsoft.com/azure/architecture/patterns/cache-aside). En el caso de una solicitud entrante, primero se consulta la caché (paso \# 1) para obtener una respuesta. Si se encuentra, los datos se devuelven inmediatamente. Si los datos no existen en la memoria caché (lo que se conoce como un error de [caché](https://www.techopedia.com/definition/6308/cache-miss)), se recuperan de una base de datos local en un servicio de nivel inferior (paso \# 2). A continuación, se escribe en la caché para las solicitudes futuras (paso \# 3) y se devuelve al autor de la llamada. Se debe tener cuidado de expulsar periódicamente los datos almacenados en caché para que el sistema siga siendo puntual y coherente.

A medida que crece la memoria caché compartida, es posible que resulte beneficioso particionar sus datos en varios nodos. Esto puede ayudar a minimizar la contención y mejorar la escalabilidad. Muchos servicios de almacenamiento en caché admiten la capacidad de agregar y quitar nodos de forma dinámica y de reequilibrar los datos entre las particiones. Normalmente, este enfoque implica la agrupación en clústeres. La agrupación en clústeres expone una colección de nodos federados como una sola memoria caché sin problemas. Sin embargo, internamente, los datos están dispersos en los nodos después de una estrategia de distribución predefinida que equilibra la carga uniformemente.

## <a name="azure-cache-for-redis"></a>Azure Cache for Redis

[Caché de Azure para Redis](https://azure.microsoft.com/services/cache/) es un servicio de agente de mensajería y almacenamiento en caché de datos seguro, totalmente administrado por Microsoft. Se consume como una oferta de plataforma como servicio (PaaS), que proporciona un alto rendimiento y un acceso de baja latencia a los datos. El servicio es accesible para cualquier aplicación dentro o fuera de Azure.

La caché de Azure para el servicio ReDiS administra el acceso a los servidores de Redis de código abierto hospedados en los centros de datos de Azure. El servicio actúa como una fachada que proporciona administración, control de acceso y seguridad. El servicio admite de forma nativa un amplio conjunto de estructuras de datos, como cadenas, valores hash, listas y conjuntos. Si su aplicación ya usa Redis, funcionará tal cual con la memoria caché de Azure para Redis.

La caché de Azure para Redis es más que un servidor de caché simple. Puede admitir varios escenarios para mejorar una arquitectura de microservicios:

- Un almacén de datos en memoria
- Una base de datos no relacional distribuida
- Un agente de mensajes
- Un servidor de configuración o de detección
  
En el caso de escenarios avanzados, una copia de los datos en caché puede [almacenarse en el disco](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-how-to-premium-persistence). Si un evento catastrófico deshabilita las cachés principal y de réplica, la memoria caché se reconstruye a partir de la instantánea más reciente.

Azure Redis Cache está disponible en varias configuraciones predefinidas y planes de tarifa. El [nivel Premium](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-overview#service-tiers) incluye muchas características de nivel empresarial, como la agrupación en clústeres, la persistencia de datos, la replicación geográfica y el aislamiento de red virtual.

>[!div class="step-by-step"]
>[Anterior](relational-vs-nosql-data.md)
>[Siguiente](elastic-search-in-azure.md)
