---
title: Resistencia de la plataforma Azure
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Resistencia de la infraestructura de la nube con Azure
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 752f1320d9dfa18e52b078763d221a787da15e8e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613985"
---
# <a name="azure-platform-resiliency"></a>Resistencia de la plataforma Azure

La creación de una aplicación confiable en la nube es diferente del desarrollo de aplicaciones local tradicional. Aunque históricamente ha adquirido hardware de mayor tamaño para escalar verticalmente, en un entorno de nube que escala horizontalmente. En lugar de intentar evitar errores, el objetivo es minimizar sus efectos y mantener el sistema estable.

Dicho esto, las aplicaciones en la nube confiables muestran características distintas:

- Son resistentes, se recuperan correctamente de los problemas y continúan funcionando.
- Son de alta disponibilidad (HA) y se ejecutan tal y como están diseñados en un estado correcto sin tiempo de inactividad significativo.

Comprender cómo funcionan estas características juntas y cómo afectan al costo: es esencial para crear una aplicación confiable de la nube nativa. A continuación, veremos cómo puede crear resistencia y disponibilidad en las aplicaciones nativas de la nube que aprovechan las características de la nube de Azure.

## <a name="design-with-resiliency"></a>Diseño con resistencia

Nuestra resistencia permite que la aplicación reaccione ante errores y siga siendo funcional. En las notas del producto sobre [resistencia de Azure](https://azure.microsoft.com/mediahandler/files/resourcefiles/resilience-in-azure-whitepaper/Resilience%20in%20Azure.pdf), se proporcionan instrucciones para lograr resistencia en la plataforma Azure. Estas son algunas recomendaciones clave:

- *Error de hardware.* Cree redundancia en la aplicación mediante la implementación de componentes en distintos dominios de error. Por ejemplo, asegúrese de que las máquinas virtuales de Azure se colocan en bastidores diferentes mediante conjuntos de disponibilidad.

- *Error del centro de recursos.* Cree redundancia en la aplicación con zonas de aislamiento de errores en los centros de recursos. Por ejemplo, asegúrese de que las máquinas virtuales de Azure se colocan en distintos centros de recursos aislados por error mediante Azure Availability Zones.

- *Error regional.* Replique los datos y componentes en otra región para que las aplicaciones puedan recuperarse rápidamente. Por ejemplo, use Azure Site Recovery para replicar máquinas virtuales de Azure en otra región de Azure.

- *Carga pesada.* Equilibrio de carga entre instancias para controlar los picos de uso. Por ejemplo, coloque dos o más máquinas virtuales de Azure detrás de un equilibrador de carga para distribuir el tráfico a todas las máquinas virtuales.

- *Eliminación o daños accidentales de los datos.* Realice una copia de seguridad de los datos para que se puedan restaurar si hay algún daño o eliminación. Por ejemplo, use Azure Backup para realizar copias de seguridad periódicas de las máquinas virtuales de Azure.

## <a name="design-with-redundancy"></a>Diseño con redundancia

Los errores varían en el ámbito del impacto. Un error de hardware, como un disco con errores, puede afectar a un solo nodo de un clúster. Un conmutador de red con error puede afectar a todo el bastidor del servidor. Los errores menos comunes, como la pérdida de energía, pueden interrumpir todo un centro de recursos. Rara vez, toda una región deja de estar disponible.

La [redundancia](https://docs.microsoft.com/azure/architecture/guide/design-principles/redundancy) es una manera de proporcionar resistencia de la aplicación. El nivel exacto de redundancia necesaria depende de los requisitos de su empresa y afectará tanto al costo como a la complejidad del sistema. Por ejemplo, una implementación de varias regiones es más costosa y más compleja de administrar que una implementación de una sola región. Necesitará procedimientos operativos para administrar la conmutación por error y la conmutación por recuperación. El costo y la complejidad adicionales pueden estar justificados en algunos escenarios empresariales, pero no en otros.

Para diseñar la redundancia, debe identificar las rutas críticas en la aplicación y, a continuación, determinar si hay redundancia en cada punto de la ruta de acceso. Si se produce un error en un subsistema, ¿la aplicación conmutará por error a otra cosa? Por último, necesita comprender claramente las características integradas en la plataforma en la nube de Azure que puede aprovechar para satisfacer sus requisitos de redundancia. Estas son algunas recomendaciones para la arquitectura de la redundancia:

- *Implemente varias instancias de servicios.* Si la aplicación depende de una única instancia de un servicio, crea un único punto de error. El aprovisionamiento de varias instancias mejora tanto la resistencia como la escalabilidad. Al hospedar en Azure Kubernetes Service, puede configurar mediante declaración instancias redundantes (conjuntos de réplicas) en el archivo de manifiesto Kubernetes. El valor de recuento de réplicas se puede administrar mediante programación, en el portal o a través de las características de escalado automático.

- *Aprovechamiento de un equilibrador de carga.* El equilibrio de carga distribuye las solicitudes de la aplicación a las instancias de servicio en buen estado y quita automáticamente las instancias incorrectas de la rotación. Cuando se implementa en Kubernetes, el equilibrio de carga se puede especificar en el archivo de manifiesto Kubernetes en la sección servicios.

- *Plan para la implementación en la región.* Si implementa la aplicación en una sola región y dicha región deja de estar disponible, la aplicación también dejará de estar disponible. Esto puede ser inaceptable en los términos de los contratos de nivel de servicio de la aplicación. En su lugar, considere la posibilidad de implementar la aplicación y sus servicios en varias regiones. Por ejemplo, un clúster de Azure Kubernetes Service (AKS) se implementa en una sola región. Para proteger el sistema de un error regional, puede implementar la aplicación en varios clústeres de AKS en diferentes regiones y usar la característica de [regiones emparejadas](https://buildazure.com/2017/01/06/azure-region-pairs-explained/) para coordinar las actualizaciones de plataforma y priorizar los esfuerzos de recuperación.

- *Habilite [la replicación geográfica](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication).* La replicación geográfica para servicios como Azure SQL Database y Cosmos DB creará réplicas secundarias de los datos en varias regiones. Aunque ambos servicios replicarán automáticamente los datos dentro de la misma región, la replicación geográfica le protege contra una interrupción regional al permitir la conmutación por error a una región secundaria. Otro procedimiento recomendado para los centros de replicación geográfica alrededor del almacenamiento de imágenes de contenedor. Para implementar un servicio en AKS, debe almacenar y extraer la imagen de un repositorio. Azure Container Registry se integra con AKS y puede almacenar imágenes de contenedor de forma segura. Para mejorar el rendimiento y la disponibilidad, considere la posibilidad de replicar geográficamente las imágenes en un registro en cada región donde tenga un clúster de AKS. Cada clúster de AKS extrae las imágenes de contenedor del registro de contenedor local en su región, tal como se muestra en la figura 6-4:

![Recursos replicados entre regiones](./media/replicated-resources.png)

**Figura 6-4**. Recursos replicados entre regiones

- *Implemente un equilibrador de carga de tráfico DNS.* [Azure Traffic Manager](https://docs.microsoft.com/azure/traffic-manager/traffic-manager-overview) proporciona alta disponibilidad para las aplicaciones críticas mediante el equilibrio de carga en el nivel de DNS. Puede enrutar el tráfico a diferentes regiones según la geografía, el tiempo de respuesta del clúster e incluso el estado del punto de conexión de la aplicación. Por ejemplo, Azure Traffic Manager puede dirigir a los clientes al clúster de AKS más cercano y a la instancia de la aplicación. Si tiene varios clústeres de AKS en distintas regiones, use Traffic Manager para controlar cómo fluye el tráfico a las aplicaciones que se ejecutan en cada clúster. En la figura 6-5 se muestra este escenario.

![AKS y Azure Traffic Manager](./media/aks-traffic-manager.png)

**Figura 6-5**. AKS y Azure Traffic Manager

## <a name="design-for-scalability"></a>Diseño para escalabilidad

La nube prospera en el escalado. La capacidad de aumentar o disminuir los recursos del sistema para solucionar el aumento o la disminución de la carga del sistema es un principio clave de la nube de Azure. Sin embargo, para escalar eficazmente una aplicación, necesita comprender las características de escalado de cada servicio de Azure que se incluye en la aplicación.  Estas son algunas recomendaciones para implementar eficazmente el escalado en el sistema.

- *Diseño para el escalado.* Una aplicación debe diseñarse para el escalado. Para empezar, los servicios no deben tener estado, por lo que las solicitudes se pueden enrutar a cualquier instancia. Tener servicios sin estado también significa que la adición o eliminación de una instancia no afecta negativamente a los usuarios actuales.

- *Cargas de trabajo de partición*. La descomposición de dominios en microservicios independientes y autónomos permite que cada servicio Escale de forma independiente a los demás. Normalmente, los servicios tendrán diferentes requisitos y necesidades de escalabilidad. La creación de particiones permite escalar solo lo que se debe escalar sin el costo innecesario de escalar una aplicación completa.

- *Favorecer el escalado horizontal.* Las aplicaciones basadas en la nube favorecen el escalado horizontal de los recursos en lugar de escalar verticalmente. El escalado horizontal (también conocido como escala horizontal) implica agregar más recursos de servicio a un sistema existente para cumplir y compartir un nivel de rendimiento deseado. El escalado vertical (también conocido como escala vertical) implica el reemplazo de recursos existentes con hardware más eficaz (más núcleos de disco, memoria y procesamiento). El escalado horizontal se puede invocar automáticamente con las características de escalado automático disponibles en algunos recursos de la nube de Azure. El escalado horizontal entre varios recursos también agrega redundancia al sistema global. Por último, el escalado vertical de un solo recurso es normalmente más caro que el escalado horizontal entre muchos recursos más pequeños. En la figura 6-6 se muestran los dos enfoques:

![Escalar verticalmente frente a escalabilidad horizontal](./media/scale-up-scale-out.png)

**Figura 6-6.** Escalar verticalmente frente a escalabilidad horizontal

- *Escale proporcionalmente.* Al escalar un servicio, piense en lo que respecta a los *conjuntos de recursos*. Si fuera a escalar considerablemente un servicio específico, ¿qué impacto tendría en los almacenes de datos de back-end, en las memorias caché y en los servicios dependientes? Algunos recursos como Cosmos DB se pueden escalar horizontalmente de forma proporcional, mientras que muchos otros no. Desea asegurarse de que no se escala horizontalmente un recurso a un punto en el que se agotarán otros recursos asociados.

- *Evite la afinidad.* Un procedimiento recomendado es asegurarse de que un nodo no requiera afinidad local, lo que a menudo se conoce como una *sesión permanente*. Una solicitud debe ser capaz de enrutar a cualquier instancia de. Si necesita conservar el estado, debe guardarse en una caché distribuida, como [Azure Redis cache](https://azure.microsoft.com/services/cache/).

- *Aproveche las características de escalado automático de la plataforma.* Use las características de escalado automático integradas siempre que sea posible, en lugar de mecanismos personalizados o de terceros. Siempre que sea posible, use reglas de escalado programadas para asegurarse de que los recursos estén disponibles sin un retraso de inicio, pero agregue el escalado automático reactivo a las reglas según corresponda, para hacer frente a los cambios inesperados en la demanda. Para obtener más información, consulte [Guía de escalado automático](https://docs.microsoft.com/azure/architecture/best-practices/auto-scaling).

- *Escale horizontalmente de forma agresiva.* Una práctica final sería escalar horizontalmente de forma agresiva para que pueda satisfacer rápidamente picos inmediatos de tráfico sin perder su negocio. Y, a continuación, escale horizontalmente (es decir, quite las instancias innecesarias) para mantener el sistema estable. Una manera sencilla de implementar esto es establecer el período de enfriamiento, que es el tiempo de espera entre las operaciones de escalado, hasta cinco minutos para agregar recursos y hasta 15 minutos para quitar instancias.

## <a name="built-in-retry-in-services"></a>Reintento integrado en los servicios

Se recomienda el procedimiento recomendado para implementar operaciones de reintento mediante programación en una sección anterior. Tenga en cuenta que muchos servicios de Azure y sus SDK de cliente correspondientes también incluyen mecanismos de reintento. En la lista siguiente se resumen las características de reintentos de la mayoría de los servicios de Azure que se describen en este libro:

- *Azure Cosmos DB.* La <xref:Microsoft.Azure.Documents.Client.DocumentClient> clase de la API de cliente retira automáticamente los intentos fallidos. El número de reintentos y el tiempo de espera máximo se pueden configurar. Las excepciones iniciadas por la API de cliente son solicitudes que superan la Directiva de reintentos o errores no transitorios.

- *Azure Redis Cache.* El cliente de StackExchange de Redis usa una clase de administrador de conexiones que incluye reintentos en intentos con error. El número de reintentos, la Directiva de reintentos específica y el tiempo de espera se pueden configurar.

- *Azure Service Bus.* El cliente Service Bus expone una [clase RetryPolicy](xref:Microsoft.ServiceBus.RetryPolicy) que se puede configurar con un intervalo de interrupción, un recuento de reintentos y <xref:Microsoft.ServiceBus.RetryExponential.TerminationTimeBuffer%2A> , que especifica el tiempo máximo que puede tardar una operación. La directiva predeterminada es nueve reintentos máximos con un período de interrupción de 30 segundos entre los intentos.

- *Azure SQL Database.* Se proporciona compatibilidad con el reintento cuando se usa la biblioteca de [Entity Framework Core](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency) .

- *Azure Storage.* La biblioteca de cliente de almacenamiento admite operaciones de reintento. Las estrategias varían en las tablas, los blobs y las colas de Azure Storage. Además, los reintentos alternativos cambian entre las ubicaciones de servicios de almacenamiento principales y secundarios cuando la característica de redundancia geográfica está habilitada.

- *Azure Event Hubs.* La biblioteca de cliente del centro de eventos presenta una propiedad RetryPolicy, que incluye una característica de retroceso exponencial configurable.

>[!div class="step-by-step"]
>[Anterior](application-resiliency-patterns.md)
>[Siguiente](resilient-communications.md)
