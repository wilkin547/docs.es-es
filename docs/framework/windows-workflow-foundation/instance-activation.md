---
title: "Activaci&#243;n de instancias | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 134c3f70-5d4e-46d0-9d49-469a6643edd8
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Activaci&#243;n de instancias
El almacén de instancias de flujo de trabajo de SQL ejecuta una tarea interna que se inicia periódicamente y que detecta instancias de flujo de trabajo ejecutables o activables en la base de datos de persistencia.Si encuentra una instancia de flujo de trabajo ejecutable, notifica al host de flujo de trabajo que es capaz de activar la instancia.Si el almacén de instancias encuentra una instancia de flujo de trabajo activable, notifica a un host genérico que activa un host del flujo de trabajo, que a su vez ejecuta la instancia de flujo de trabajo.Las siguientes secciones en este tema explican el proceso de activación de la instancia en detalle.  
  
##  <a name="RunnableSection"></a> Detectar y activar instancias de flujo de trabajo ejecutables  
 El almacén de instancias de flujo de trabajo de SQL considera que una instancia de flujo de trabajo es *ejecutable* si la instancia no está en estado suspendido o completado y cumple las condiciones siguientes:  
  
-   La instancia se desbloquea y tiene un temporizador pendiente que ha expirado.  
  
-   La instancia tiene un bloqueo expirado en ella.  
  
-   La instancia está desbloqueada y su estado es **En ejecución**.  
  
 El almacén de instancias de flujo de trabajo de SQL genera <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> cuando encuentra una instancia ejecutable.Después de esto, SqlWorkflowInstanceStore detiene la supervisión hasta que se llame a <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand> cuando se encuentre en el almacén.  
  
 Un host del flujo de trabajo que se ha suscrito para <xref:System.Activities.DurableInstancing.HasRunnableWorkflowEvent> y que es capaz de cargar la instancia ejecuta <xref:System.Activities.DurableInstancing.TryLoadRunnableWorkflowCommand> en el almacén de instancias para cargar la instancia en la memoria.Se considera que un host del flujo de trabajo es capaz de cargar una instancia de flujo de trabajo si el host y la instancia tienen la propiedad de metadatos **WorkflowServiceType** establecida en el mismo valor.  
  
## Detectar y activar instancias de flujo de trabajo activables  
 Se considera que una instancia de flujo de trabajo es *activable* si la instancia es ejecutable y si no hay ningún host de flujo de trabajo capaz de cargar la instancia que se esté ejecutando en el equipo.Vea en la sección Detectar y activar instancias de flujo de trabajo ejecutables anterior la definición de una instancia de flujo de trabajo ejecutable.  
  
 El almacén de instancias de flujo de trabajo de SQL genera <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> cuando encuentra una instancia de flujo de trabajo activable en la base de datos.Después de esto, SqlWorkflowInstanceStore detiene la supervisión hasta que se llame a <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand> cuando se encuentre en el almacén.  
  
 Cuando un host genérico que ha suscrito para <xref:System.Activities.DurableInstancing.HasActivatableWorkflowEvent> recibe el evento, ejecuta <xref:System.Activities.DurableInstancing.QueryActivatableWorkflowsCommand> en el almacén de instancias para obtener parámetros de activación necesarios para crear un host del flujo de trabajo.El host genérico usa estos parámetros de activación para crear un host del flujo de trabajo, que a su vez carga y ejecuta la instancia de servicio ejecutable.  
  
## Hosts genéricos  
 Un host genérico es un host en el que el valor de la propiedad de metadatos **WorkflowServiceType** para los hosts genéricos está establecido en **WorkflowServiceType.Any** para indicar que puede controlar cualquier tipo de flujo de trabajo.Un host genérico tiene un parámetro XName denominado **ActivationType**.  
  
 Actualmente, el almacén de instancias de flujo de trabajo de SQL admite los hosts genéricos con el valor del parámetro ActivationType establecido en **WAS**.Si el tipo de activación no está definido en WAS, el almacén de instancias de flujo de trabajo SQL inicia <xref:System.Runtime.DurableInstancing.InstancePersistenceException>.El Servicio de administración de flujos de trabajo que viene con [!INCLUDE[dublin](../../../includes/dublin-md.md)] es un host genérico que tiene el tipo de activación definido en **WAS**.  
  
 Para la activación WAS, un host genérico exige que un conjunto de parámetros de activación derive la dirección del extremo en la que se pueden activar los nuevos hosts.Los parámetros de activación para la activación WAS son los nombre del sitio, la ruta de acceso a la aplicación relativa al sitio y la ruta de acceso al servicio relativa a la aplicación.El almacén de instancias de flujo de trabajo de SQL almacena estos parámetros de activación durante la ejecución de <xref:System.Activities.DurableInstancing.SaveWorkflowCommand>.  
  
## Período de detección de instancias ejecutables  
 La propiedad **Período de detección de instancias ejecutables** del almacén de instancias de flujo de trabajo de SQL especifica el período de tiempo transcurrido el cual este almacén ejecuta una tarea de detección para detectar cualquier instancia de flujo de trabajo ejecutable o activable en la base de datos de persistencia después del ciclo de detección anterior.Vea [Período de detección de instancias ejecutables](../../../docs/framework/windows-workflow-foundation//runnable-instances-detection-period.md) para obtener información detallada sobre esta propiedad.