---
title: "Cómo: Habilitar persistencia para flujos de trabajo y servicios de flujo de trabajo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8f282eddc61ef8e1426c60b7a4383fc42242ccfb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a>Cómo: Habilitar persistencia para flujos de trabajo y servicios de flujo de trabajo
En este tema se describe cómo habilitar la persistencia para los flujos de trabajo y los servicios de flujo de trabajo.  
  
## <a name="enable-persistence-for-workflows"></a>Habilitar persistencia para los flujos de trabajo  
 Puede asociar un almacén de instancias con una **WorkflowApplication** mediante el uso de la <xref:System.Activities.WorkflowApplication.InstanceStore%2A> propiedad de la <xref:System.Activities.WorkflowApplication> clase. El método <xref:System.Activities.WorkflowApplication.Persist%2A> guarda o conserva un flujo de trabajo en el almacén de instancias asociado a la aplicación. El método <xref:System.Activities.WorkflowApplication.Unload%2A> conserva un flujo de trabajo en el almacén de instancias y, a continuación, descarga la instancia de la memoria. El **carga** método carga un flujo de trabajo en la memoria usando los datos de flujo de trabajo almacenados en el almacén de persistencia de instancias.  
  
 El **Persist** método lleva a cabo los pasos siguientes:  
  
1.  Pausa el programador del flujo de trabajo y espera hasta que el flujo de trabajo entre en el estado inactivo.  
  
2.  Conserva o guarda el flujo de trabajo en el almacén de persistencia.  
  
3.  Reanuda el programador del flujo de trabajo.  
  
 El **Unload** método lleva a cabo los pasos siguientes:  
  
1.  Pausa el programador del flujo de trabajo y espera hasta que el flujo de trabajo entre en el estado inactivo.  
  
2.  Conserva o guarda el flujo de trabajo en el almacén de persistencia.  
  
3.  Elimina la instancia de flujo de trabajo en la memoria.  
  
 Tanto el **Persist** y **Unload** métodos se bloquean mientras un flujo de trabajo está en una zona sin persistencia hasta que el flujo de trabajo salga de ella. El método continúa con la operación de persistencia o descarga después de que se complete la zona sin persistencia. Si la zona sin persistencia no se completa antes de que transcurra el tiempo de espera o, si el proceso de persistencia tarda demasiado, se iniciará una TimeoutException.  
  
## <a name="enable-persistence-for-workflow-services-in-code"></a>Habilitar persistencia para los servicios de flujo de trabajo en código  
 El **DurableInstancingOptions** miembro de la <xref:System.ServiceModel.WorkflowServiceHost> clase tiene una propiedad denominada **InstanceStore** que puede utilizar para asociar un almacén de instancias con el **WorkflowServiceHost** .  
  
```  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
```  
  
 Cuando el **WorkflowServiceHost** está abierto, persistencia se habilita automáticamente si el **DurableInstancingOptions.InstanceStore** no es null.  
  
 Normalmente, un comportamiento de servicio proporciona el almacén de instancias concreto para su uso con un host de servicio de flujo de trabajo mediante el uso de la **InstanceStore** propiedad. Por ejemplo, SqlWorkflowInstanceStoreBehavior crea una instancia de la **SqlWorkflowInstanceStore**, lo configura y lo asigna a la **DurableInstancingOptions.InstanceStore**.  
  
## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a>Habilita la persistencia para los servicios de flujo de trabajo usando un archivo de configuración de la aplicación  
 La persistencia puede habilitarse mediante un archivo de configuración de la aplicación agregando el código siguiente al archivo app.config o web.config:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="myBehavior">  
          <SqlWorkflowInstanceStore connectionString="Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase">  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
```
