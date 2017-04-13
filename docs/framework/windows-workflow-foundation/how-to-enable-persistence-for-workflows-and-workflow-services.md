---
title: "C&#243;mo: Habilitar persistencia para flujos de trabajo y servicios de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# C&#243;mo: Habilitar persistencia para flujos de trabajo y servicios de flujo de trabajo
En este tema se describe cómo habilitar la persistencia para los flujos de trabajo y los servicios de flujo de trabajo.  
  
## Habilitar persistencia para los flujos de trabajo  
 Puede asociar un almacén de instancias con **WorkflowApplication** mediante el uso de la propiedad <xref:System.Activities.WorkflowApplication.InstanceStore%2A> de la clase <xref:System.Activities.WorkflowApplication>.El método <xref:System.Activities.WorkflowApplication.Persist%2A> guarda o conserva un flujo de trabajo en el almacén de instancias asociado a la aplicación.El método <xref:System.Activities.WorkflowApplication.Unload%2A> conserva un flujo de trabajo en el almacén de instancias y, a continuación, descarga la instancia de la memoria.El método **Load** carga un flujo de trabajo en la memoria usando los datos del flujo de trabajo almacenados en el almacén de persistencia de instancias.  
  
 El método **Persist** lleva a cabo los pasos siguientes:  
  
1.  Pausa el programador del flujo de trabajo y espera hasta que el flujo de trabajo entre en el estado inactivo.  
  
2.  Conserva o guarda el flujo de trabajo en el almacén de persistencia.  
  
3.  Reanuda el programador del flujo de trabajo.  
  
 El método **Unload** lleva a cabo los pasos siguientes:  
  
1.  Pausa el programador del flujo de trabajo y espera hasta que el flujo de trabajo entre en el estado inactivo.  
  
2.  Conserva o guarda el flujo de trabajo en el almacén de persistencia.  
  
3.  Elimina la instancia de flujo de trabajo en la memoria.  
  
 Los métodos **Persist** y **Unload** se bloquean mientras el flujo de trabajo se encuentra en una zona sin persistencia hasta que el flujo de trabajo salga de ella.El método continúa con la operación de persistencia o descarga después de que se complete la zona sin persistencia.Si la zona sin persistencia no se completa antes de que transcurra el tiempo de espera o, si el proceso de persistencia tarda demasiado, se iniciará una TimeoutException.  
  
## Habilitar persistencia para los servicios de flujo de trabajo en código  
 El miembro **DurableInstancingOptions** de la clase <xref:System.ServiceModel.WorkflowServiceHost> tiene una propiedad denominada **InstanceStore** que puede usar para asociar un almacén de instancias con **WorkflowServiceHost**.  
  
```  
  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
  
```  
  
 Cuando se abre **WorkflowServiceHost**, la persistencia está habilitada automáticamente si **DurableInstancingOptions.InstanceStore** no tiene un valor nulo.  
  
 Normalmente, el comportamiento de servicio proporciona el almacén de instancias concreto que se va a usar con un host de servicio de flujo de trabajo usando la propiedad **InstanceStore**.Por ejemplo, SqlWorkflowInstanceStoreBehavior crea una instancia de **SqlWorkflowInstanceStore**, lo configura y lo asigna a **DurableInstancingOptions.InstanceStore**.  
  
## Permiso persistencia para los servicios de flujo de trabajo usando un archivo de configuración de la aplicación  
 La persistencia puede habilitarse mediante un archivo de configuración de la aplicación agregando el código siguiente al archivo app.config o web.config:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name=”myBehavior”>  
          <SqlWorkflowInstanceStore connectionString=”Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase”>  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
  
```