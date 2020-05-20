---
title: Procedimiento para habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo
description: Aprenda a configurar el almacén de instancias de flujo de trabajo de SQL para habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo mediante programación y mediante un archivo de configuración.
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 31fe6e3f06989e9a42254747565342cf97e4b9f1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421519"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a>Procedimiento para habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo

En este tema se describe cómo habilitar la persistencia para los flujos de trabajo y los servicios de flujo de trabajo.

## <a name="enable-persistence-for-workflows"></a>Habilitar persistencia para los flujos de trabajo

Puede asociar un almacén de instancias con **WorkflowApplication** mediante la <xref:System.Activities.WorkflowApplication.InstanceStore%2A> propiedad de la <xref:System.Activities.WorkflowApplication> clase. El método <xref:System.Activities.WorkflowApplication.Persist%2A> guarda o conserva un flujo de trabajo en el almacén de instancias asociado a la aplicación. El método <xref:System.Activities.WorkflowApplication.Unload%2A> conserva un flujo de trabajo en el almacén de instancias y, a continuación, descarga la instancia de la memoria. El método **Load** carga un flujo de trabajo en la memoria utilizando los datos de flujo de trabajo almacenados en el almacén de persistencia de la instancia.

El método **Persist** realiza los siguientes pasos:

1. Pausa el programador del flujo de trabajo y espera hasta que el flujo de trabajo entre en el estado inactivo.

2. Conserva o guarda el flujo de trabajo en el almacén de persistencia.

3. Reanuda el programador del flujo de trabajo.

 El método **Unload** realiza los siguientes pasos:

1. Pausa el programador del flujo de trabajo y espera hasta que el flujo de trabajo entre en el estado inactivo.

2. Conserva o guarda el flujo de trabajo en el almacén de persistencia.

3. Elimina la instancia de flujo de trabajo en la memoria.

Los métodos de **persistencia** y **descarga** se bloquearán mientras un flujo de trabajo se encuentra en una zona sin persistencia hasta que el flujo de trabajo salga de la zona sin persistencia. El método continúa con la operación de persistencia o descarga después de que se complete la zona sin persistencia. Si la zona sin persistencia no se completa antes de que transcurra el tiempo de espera o, si el proceso de persistencia tarda demasiado, se iniciará una TimeoutException.

## <a name="enable-persistence-for-workflow-services-in-code"></a>Habilitar persistencia para los servicios de flujo de trabajo en código

El miembro **DurableInstancingOptions** de la <xref:System.ServiceModel.WorkflowServiceHost> clase tiene una propiedad denominada **InstanceStore** que puede usar para asociar un almacén de instancias a **WorkflowServiceHost**.

```csharp
// wsh is an instance of WorkflowServiceHost class
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();
```

Cuando se abre **WorkflowServiceHost** , la persistencia se habilita automáticamente si **DurableInstancingOptions. InstanceStore** no es NULL.

Normalmente, un comportamiento de servicio proporciona el almacén de instancias concreto que se va a usar con un host de servicio de flujo de trabajo mediante la propiedad **InstanceStore** . Por ejemplo, el SqlWorkflowInstanceStoreBehavior crea una instancia de **SqlWorkflowInstanceStore**, la configura y la asigna a **DurableInstancingOptions. InstanceStore**(puede estar en inglés).

## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a>Habilita la persistencia para los servicios de flujo de trabajo usando un archivo de configuración de la aplicación

La persistencia puede habilitarse mediante un archivo de configuración de la aplicación agregando el código siguiente al archivo app.config o web.config:

```xml
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="myBehavior">
          <sqlWorkflowInstanceStore connectionString="Data Source=myDatabaseServer;Initial Catalog=myPersistenceDatabase" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```
