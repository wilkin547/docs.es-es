---
description: 'Más información sobre: procedimientos recomendados de persistencia'
title: Procedimientos recomendados de persistencia
ms.date: 03/30/2017
ms.assetid: 6974c5a4-1af8-4732-ab53-7d694608a3a0
ms.openlocfilehash: 788c025d52e504e7a767a4aa0841ae01a7d3327c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787882"
---
# <a name="persistence-best-practices"></a>Procedimientos recomendados de persistencia

Este documento trata de los procedimientos recomendados el diseño de flujo de trabajo y de la configuración relacionada con la persistencia del flujo de trabajo.  
  
## <a name="design-and-implementation-of-durable-workflows"></a>Diseño e implementación de flujos de trabajo duraderos  

 En general, los flujos de trabajo realizan el trabajo en períodos breves que se intercalan con tiempos durante los que el flujo de trabajo está inactivo porque está esperando un evento. Este evento puede ser varias cosas, como un mensaje o un temporizador de límite. Para poder descargar la instancia de flujo de trabajo cuando se vuelve inactivo, el host del servicio debe guardar la instancia de flujo de trabajo. Esto solo es posible si la instancia de flujo de trabajo no está en un zona sin persistencia (por ejemplo, esperando a que se complete una transacción complete o una devolución de llamada asincrónica). Para permitir la descarga de una instancia de flujo de trabajo inactiva, el autor del flujo de trabajo solo debería utilizar ámbitos de transacción y actividades asincrónicas para acciones efímeras. En particular, el autor debería mantener lo más breves posible las actividades de retraso dentro de estas zonas sin persistencia.  
  
 Solo se puede conservar un flujo de trabajo si todos los tipos de datos utilizados por el flujo de trabajo son serializables. Además, los tipos personalizados utilizados en los flujos de trabajo persistentes deben ser serializables con <xref:System.Runtime.Serialization.NetDataContractSerializer> para que sean conservados por <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.  
  
 Una instancia de flujo de trabajo no se puede recuperar en caso de un error de host o equipo si no se ha conservado. En general, recomendamos que conserve una instancia de flujo de trabajo al principio del ciclo de vida del flujo de trabajo.  
  
 Si su flujo de trabajo está ocupado durante mucho tiempo, le recomendamos conservar la instancia de flujo de trabajo con regularidad a lo largo de su período ocupación. Puede hacer esto agregando las actividades <xref:System.Activities.Statements.Persist> a lo largo de la secuencia de actividades que mantienen ocupada la instancia de flujo de trabajo. De esta manera, reciclando el dominio de la aplicación, los errores del host o del equipo no hacen que el sistema revierta hasta el inicio del período de ocupación. Sea consciente de que agregar las actividades <xref:System.Activities.Statements.Persist> a su flujo de trabajo podría provocar una degradación del rendimiento.  
  
 Windows Server App Fabric simplifica mucho la configuración y el uso de la persistencia. Para obtener más información, consulte [persistencia de Windows Server App fabric](/previous-versions/appfabric/ee677272(v=azure.10)) .  
  
## <a name="configuration-of-scalability-parameters"></a>Configuración de los parámetros de escalabilidad  

 Los requisitos de escalabilidad y rendimiento determinan la configuración de los siguientes parámetros:  
  
- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A>  
  
- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A>  
  
- <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior.InstanceLockedExceptionAction%2A>  
  
 Estos parámetros se deberían establecer como sigue, según sea el escenario.  
  
### <a name="scenario-a-small-number-of-workflow-instances-that-require-optimal-response-time"></a>Escenario: un número pequeño de instancias de flujo de trabajo que requieren un tiempo de respuesta óptimo  

 En este escenario, todas las instancias de flujo de trabajo deberían permanecer cargadas cuando se vuelven inactivas. Establezca <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> en un valor grande. El uso de esta configuración evita que una instancia de flujo de trabajo se mueva entre equipos. Utilice esta configuración solo se se cumplen una o más de las condiciones siguientes:  
  
- Una instancia de flujo de trabajo recibe un mensaje único a lo largo de su duración.  
  
- Todas las instancias de flujo de trabajo se ejecutan en un solo equipo  
  
- El mismo equipo recibe todos los mensajes que son recibidos por una instancia de flujo de trabajo.  
  
 Utilice las actividades <xref:System.Activities.Statements.Persist> o establezca <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> en 0 para habilitar la recuperación de su instancia de flujo de trabajo después de errores en el host de servicio o en el equipo.  
  
### <a name="scenario-workflow-instances-are-idle-for-long-periods-of-time"></a>Escenario: las instancias de flujo de trabajo están inactivas durante largos períodos de tiempo  

 En este escenario, establezca <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> en 0 para liberar los recursos lo antes posible.  
  
### <a name="scenario-workflow-instances-receive-multiple-messages-in-a-short-period-of-time"></a>Escenario: las instancias de flujo de trabajo reciben varios mensajes en un período de tiempo corto  

 En este escenario, establezca <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> en 60 segundos si el mismo equipo recibe estos mensajes. Esto evita una secuencia rápida de descarga y carga de una instancia de flujo de trabajo. Esto permite que la instancia no se mantenga demasiado tiempo en memoria.  
  
 Establezca <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> en 0 y <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior.InstanceLockedExceptionAction%2A> en BasicRetry o AggressiveRetry si estos mensajes pueden ser recibidos por equipos diferentes. Esto permite que la instancia de flujo de trabajo pueda ser cargada por otro equipo.  
  
### <a name="scenario-workflow-uses-delay-activities-with-short-durations"></a>Escenario: el flujo de trabajo utiliza las actividades de retraso con duraciones cortas  

 En este escenario, <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> sondea regularmente la base de datos de persistencia buscando las instancias que se deberían cargar por una actividad <xref:System.Activities.Statements.Delay> expirada. Si <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> encuentra un temporizador que expirará en el intervalo de sondeo siguiente, el Almacén de instancias de flujo de trabajo de SQL acorta el intervalo de sondeo. El siguiente sondeo se producirá después de que el temporizador haya expirado. De esta manera, el el Almacén de instancias de flujo de trabajo de SQL logra una gran exactitud de temporizadores que se ejecutan durante más tiempo que el intervalo de sondeo, que es establecida por <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>. Para habilitar el procesamiento oportuno de los retrasos más cortos, la instancia de flujo de trabajo debe permanecer en memoria durante al menos un intervalo de sondeo.  
  
 Establezca <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> en 0 para escribir la fecha de expiración en la base de datos de persistencia.  
  
 Establezca <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> para que dure más o igual que <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>, para que la instancia se mantenga en memoria por lo menos durante un intervalo de sondeo.  
  
 No recomendamos reducir <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>, porque eso provoca in incremento de la carga en la base de datos de persistencia. Cada host de servicio que utiliza <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> sondea la base de datos un vez por cada período de detección. Al establecer <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A> en un intervalo de tiempo demasiado pequeño, el rendimiento del sistema se puede reducir si el número de hosts de servicio es grande.  
  
## <a name="configuring-the-sql-workflow-instance-store"></a>Configurar el Almacén de instancias de flujo de trabajo de SQL  

 El Almacén de instancias de flujo de trabajo de SQL tiene los siguientes parámetros de configuración:  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceEncodingOption%2A>  
 Este parámetro da a <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> la instrucción de que comprima el estado de la instancia de flujo de trabajo. La compresión reduce la cantidad de datos que se almacenan en la base de datos de persistencia y reduce el tráfico de red en caso de que la base de datos de persistencia resida en un servidor de bases de datos dedicado. Si se utiliza la compresión, los recursos computacionales deben comprimir y extraer el estado de la instancia. En la mayoría de los casos, los resultados de la compresión aumentaron el rendimiento.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceCompletionAction%2A>  
 Este parámetro le indica a <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> que mantenga o elimine las instancias completadas. Mantener las instancias completadas incrementa los requisitos de almacenamiento de bases de datos de persistencia y hace que las tablas sean mayores, lo que aumentan los tiempos de búsqueda en tablas. A menos que se necesiten instancias instancias para depurar o auditar, es mejor para indicar a <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> que elimine las instancias completadas. Las instancias eliminadas solo se deberían mantener si el usuario establece un proceso para quitarlas en el futuro. Observe que no se pueden reutilizar las claves de correlación mientras la instancia de flujo de trabajo completada resida en el almacén de la instancia.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>  
 Este parámetro define el intervalo máximo con el que <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> sondea la base de datos de persistencia buscando instancias que se deberían cargar cuando una actividad <xref:System.Activities.Statements.Delay> expira. Si <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> encuentra un temporizador que expirará en el intervalo de sondeo siguiente, acorta el intervalo de sondeo para que el siguiente sondeo se produzca después de que el temporizador haya expirado. De esta manera, el Almacén de instancias de flujo de trabajo de SQL logra una gran exactitud de los temporizadores que se ejecutan más tiempo que <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>.  
  
 No recomendamos reducir <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A>, porque provoca in incremento de la carga en la base de datos de persistencia. Cada host de servicio que utiliza <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> sondea la base de datos un vez por cada período de detección. Al establecer <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.RunnableInstancesDetectionPeriod%2A> en un intervalo de tiempo demasiado pequeño, el rendimiento del sistema se puede reducir si el número de hosts de servicio es grande.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.HostLockRenewalPeriod%2A>  
 Este parámetro define el intervalo con el que el host renueva su bloqueo en la base de datos de persistencia. Acortar este intervalo habilitará una recuperación más rápida de las instancias de flujo de trabajo en caso de error de un host o equipo. Por otro lado, un período de renovación de bloqueo corto aumenta la carga en la base de datos de persistencia. Cada host de servicio que utiliza <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> actualizará sus bloqueos en la base de datos una vez por cada período de renovación. Si un equipo ejecuta muchos hosts de servicio, asegúrese de que la carga producida por la renovación del bloqueo no disminuya el rendimiento del sistema. Si lo hace, considere un incremento de <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.HostLockRenewalPeriod%2A>.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A>  
 Si está habilitado, <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> reintenta cargar una instancia bloqueada durante los 30 segundos siguientes. Establezca <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A> en BasicRetry o AggressiveRetry si el flujo de trabajo recibe varios mensajes en un tiempo corto y estos mensajes los reciben equipos diferentes.  
  
 Dado que el mecanismo de reintento de carga no introduce ninguna sobrecarga de rendimiento mientras  los reintentos de carga no se realicen, <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A> debería estar siempre habilitado.
