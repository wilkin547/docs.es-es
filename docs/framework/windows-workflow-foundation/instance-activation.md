---
description: 'Más información sobre: activación de instancia'
title: Activación de instancias
ms.date: 03/30/2017
ms.assetid: 134c3f70-5d4e-46d0-9d49-469a6643edd8
ms.openlocfilehash: a301f49fb79e7c74cd3a64e891526e5b89fdd1c6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631208"
---
# <a name="instance-activation"></a>Activación de instancias

El almacén de instancias de flujo de trabajo de SQL ejecuta una tarea interna que se inicia periódicamente y que detecta instancias de flujo de trabajo ejecutables o activables en la base de datos de persistencia. Si encuentra una instancia de flujo de trabajo ejecutable, notifica al host de flujo de trabajo que es capaz de activar la instancia. Si el almacén de instancias encuentra una instancia de flujo de trabajo activable, notifica a un host genérico que activa un host del flujo de trabajo, que a su vez ejecuta la instancia de flujo de trabajo. Las siguientes secciones en este tema explican el proceso de activación de la instancia en detalle.  
  
## <a name="detecting-and-activating-runnable-workflow-instances"></a><a name="RunnableSection"></a> Detectar y activar instancias de flujo de trabajo ejecutables  

 El almacén de instancias de flujo de trabajo de SQL considera una instancia de flujo de trabajo *ejecutable* si la instancia no está en el estado suspendido o el estado completado y satisface las condiciones siguientes:  
  
- La instancia se desbloquea y tiene un temporizador pendiente que ha expirado.  
  
- La instancia tiene un bloqueo expirado en ella.  
  
- La instancia se desbloquea y su estado es en **ejecución**.  
  
 El almacén de instancias de flujo de trabajo de SQL genera <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> cuando encuentra una instancia ejecutable. Después de esto, SqlWorkflowInstanceStore detiene la supervisión hasta que se llame a <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand> cuando se encuentre en el almacén.  
  
 Un host del flujo de trabajo que se ha suscrito para <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> y que es capaz de cargar la instancia ejecuta <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand> en el almacén de instancias para cargar la instancia en la memoria. Un host de flujo de trabajo se considera capaz de cargar una instancia de flujo de trabajo si el host y la instancia tienen la propiedad de metadatos **WorkflowServiceType** establecida en el mismo valor.  
  
## <a name="detecting-and-activating-activatable-workflow-instances"></a>Detectar y activar instancias de flujo de trabajo activables  

 Una instancia de flujo de trabajo *se considera* activable si la instancia es ejecutable y no hay ningún host de flujo de trabajo capaz de cargar la instancia que se está ejecutando en el equipo. Vea en la sección Detectar y activar instancias de flujo de trabajo ejecutables anterior la definición de una instancia de flujo de trabajo ejecutable.  
  
 El almacén de instancias de flujo de trabajo de SQL genera <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> cuando encuentra una instancia de flujo de trabajo activable en la base de datos. Después de esto, SqlWorkflowInstanceStore detiene la supervisión hasta que se llame a <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand> cuando se encuentre en el almacén.  
  
 Cuando un host genérico que ha suscrito para <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> recibe el evento, ejecuta <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand> en el almacén de instancias para obtener parámetros de activación necesarios para crear un host del flujo de trabajo. El host genérico usa estos parámetros de activación para crear un host del flujo de trabajo, que a su vez carga y ejecuta la instancia de servicio ejecutable.  
  
## <a name="generic-hosts"></a>Hosts genéricos  

 Un host genérico es un host con el valor de la propiedad de metadatos **WorkflowServiceType** para hosts genéricos se establece en **WorkflowServiceType. any** para indicar que puede controlar cualquier tipo de flujo de trabajo. Un host genérico tiene un parámetro XName denominado **ActivationType**.  
  
 Actualmente, el almacén de instancias de flujo de trabajo de SQL admite hosts genéricos con el valor del parámetro ActivationType establecido en **was**. Si el tipo de activación no está definido en WAS, el almacén de instancias de flujo de trabajo SQL inicia <xref:System.Runtime.DurableInstancing.InstancePersistenceException>. El servicio de administración de flujos de trabajo que se incluye con las características de hospedaje de Windows Server AppFabric es un host genérico que tiene el tipo de activación establecido en **was**.  
  
 Para la activación WAS, un host genérico exige que un conjunto de parámetros de activación derive la dirección del extremo en la que se pueden activar los nuevos hosts. Los parámetros de activación para la activación WAS son los nombre del sitio, la ruta de acceso a la aplicación relativa al sitio y la ruta de acceso al servicio relativa a la aplicación. El almacén de instancias de flujo de trabajo de SQL almacena estos parámetros de activación durante la ejecución de <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>.  
  
## <a name="runnable-instances-detection-period"></a>Período de detección de instancias ejecutables  

 La propiedad **período de detección de instancias ejecutables** del almacén de instancias de flujo de trabajo de SQL especifica el período de tiempo después del cual el almacén de instancias de flujo de trabajo de SQL ejecuta una tarea de detección para detectar las instancias de flujo de trabajo ejecutables o activables en la base de datos de persistencia después del ciclo Vea [período de detección de instancias ejecutables](runnable-instances-detection-period.md) para obtener más detalles sobre esta propiedad.
