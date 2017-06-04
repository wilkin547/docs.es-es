---
title: "Persistencia del flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "programar [WF], persistencia"
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
caps.latest.revision: 26
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 26
---
# Persistencia del flujo de trabajo
La persistencia del flujo de trabajo es la captura duradera de un estado de la instancia de flujo de trabajo, independientemente de la información del proceso o del equipo.Esto sirve para proporcionar un punto de recuperación conocido para la instancia de flujo de trabajo en caso de error del sistema, para conservar la memoria descargando instancias de flujo de trabajo que no están funcionando de forma activa o para mover el estado de la instancia de flujo de trabajo de un nodo a otro en una granja de servidores.  
  
 La persistencia permite procesar la agilidad, escalabilidad, recuperación en caso de error y la capacidad de administrar la memoria más eficazmente.El proceso de persistencia incluye la identificación de un punto de persistencia, la recopilación de los datos que se van a guardar y finalmente la delegación del almacenamiento real de los datos a un proveedor de persistencia.  
  
 Para habilitar la persistencia para un flujo de trabajo, necesita asociar un almacén de instancias a **WorkflowApplication** o **WorkflowServiceHost**, tal y como se menciona en [Cómo: Habilitar persistencia para flujos de trabajo y servicios de flujo de trabajo](../../../docs/framework/windows-workflow-foundation//how-to-enable-persistence-for-workflows-and-workflow-services.md).**WorkflowApplication** y **WorkflowServiceHost** usan el almacén de instancias asociado a ellos para permitir la conservación de instancias de flujo de trabajo en un almacén de persistencia y la carga de instancias de flujo de trabajo en la memoria según los datos de la instancia de flujo de trabajo almacenados en el almacén de persistencia.  
  
 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] se distribuye con la clase **SqlWorkflowInstanceStore**, que permite la persistencia de datos y metadatos sobre las instancias de flujo de trabajo en una base de datos de SQL Server 2005 o SQL Server 2008.Vea [Almacén de instancias de flujo de trabajo de SQL](../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md) para obtener más información.  
  
 Para almacenar y cargar los datos específicos de la aplicación junto con la información relacionada con la instancia de flujo de trabajo, puede crear participantes de persistencia que extienden la clase <xref:System.Activities.Persistence.PersistenceParticipant>.Los participantes de persistencia participan en el proceso de persistencia para guardar los datos serializables personalizados en el almacén de persistencia, para cargar los datos del almacén de instancias en la memoria y para realizar cualquier lógica adicional en una transacción de persistencia.Para obtener más información, vea [Participantes de persistencia](../../../docs/framework/windows-workflow-foundation//persistence-participants.md).  
  
 Windows Server APp Fabric simplifica el proceso de configuración de persistencia.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Conceptos de persistencia con Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201200)  
  
## Puntos de persistencia implícitos  
 La siguiente lista contiene ejemplos de las condiciones en las que se conserva un flujo de trabajo cuando se asocia un almacén de instancias a este.  
  
-   Cuando se completa una actividad **TransactionScope** o una actividad **TransactedReceiveScope**.  
  
-   Cuando una instancia de flujo de trabajo se vuelve inactiva y la clase **WorkflowIdleBehavior** está establecida en el host de flujo de trabajo.Por ejemplo, esto se produce al usar actividades de mensajería o una actividad **Delay**.  
  
-   Cuando WorkflowApplication se vuelve inactivo y la propiedad **PersistableIdle** de la aplicación está establecida en **PersistableIdleAction.Persist**.  
  
-   Cuando se indica a una aplicación host que conserve o descargue una instancia de flujo de trabajo.  
  
-   Cuando se finaliza o termina una instancia de flujo de trabajo.  
  
-   Cuando se ejecuta una actividad **Persist**.  
  
-   Cuando una instancia de un flujo de trabajo desarrollada con una versión anterior de Windows Workflow Foundation encuentra un punto de persistencia durante la ejecución interoperable.  
  
## En esta sección  
  
-   [Almacén de instancias de flujo de trabajo de SQL](../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md)  
  
-   [Almacenes de instancias](../../../docs/framework/windows-workflow-foundation//instance-stores.md)  
  
-   [Participantes de persistencia](../../../docs/framework/windows-workflow-foundation//persistence-participants.md)  
  
-   [Procedimientos recomendados de persistencia](../../../docs/framework/windows-workflow-foundation//persistence-best-practices.md)  
  
-   [Instancias de flujo de trabajo no persistentes](../../../docs/framework/windows-workflow-foundation//non-persisted-workflow-instances.md)  
  
-   [Pausar y reanudar un flujo de trabajo](../../../docs/framework/windows-workflow-foundation//pausing-and-resuming-a-workflow.md)