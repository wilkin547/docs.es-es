---
title: Procedimiento para configurar el comportamiento inactivo con WorkflowServiceHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
ms.openlocfilehash: a676f03b4e6f9dd210b843a6f3bf00c735889500
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699609"
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a>Procedimiento para configurar el comportamiento inactivo con WorkflowServiceHost
Los flujos de trabajo pasan a estar inactivos cuando encuentran un marcador que se debe reanudar mediante algún estímulo externo, por ejemplo cuando la instancia de flujo de trabajo está esperando la entrega de un mensaje usando una actividad <xref:System.ServiceModel.Activities.Receive> . <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> es un comportamiento que le permite especificar el tiempo transcurrido desde que una instancia de servicio pasa a estado inactivo hasta que la instancia se guarda o se descarga. Contiene dos propiedades que permiten establecer estas duraciones. <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> especifica el período de tiempo entre el momento en el que una instancia de servicio del flujo de trabajo se inactiva y el momento en el que dicha instancia se guarda. <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> especifica el intervalo de tiempo entre el momento en el que una instancia de servicio del flujo de trabajo se inactiva y el momento en el que dicha instancia se descarga, donde la descarga significa guardar la instancia en el almacén de instancia y eliminarla de la memoria. En este tema, se explica cómo configurar la clase <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> en un archivo de configuración.  
  
### <a name="to-configure-workflowidlebehavior"></a>Para configurar WorkflowIdleBehavior  
  
1. Agregar un <`workflowIdle`> elemento para el <`behavior`> elemento dentro de la <`serviceBehaviors`> elemento tal como se muestra en el ejemplo siguiente.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     El atributo `timeToUnload` especifica el período de tiempo entre el momento en el que una instancia de servicio del flujo de trabajo se inactiva y el momento en el que dicho servicio se descarga. El atributo `timeToPersist` especifica el período de tiempo entre el momento en el que una instancia de servicio del flujo de trabajo se inactiva y el momento en el que dicha instancia se guarda. El valor predeterminado de `timeToUnload` es 1 minuto. El valor predeterminado de `timeToPersist` es <xref:System.TimeSpan.MaxValue>. Si desea conservar las instancias inactivas en memoria pero hacer que persistan por integridad, establezca los valores de modo que `timeToPersist` < `timeToUnload`. Si desea impedir que las instancias inactivas se carguen, establezca `timeToUnload` en <xref:System.TimeSpan.MaxValue>. Para obtener más información acerca de <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, consulte [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
  
    > [!NOTE]
    >  En el ejemplo de configuración anterior, se usa la configuración simplificada. Para obtener más información, consulte [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).  
  
### <a name="to-change-idle-behavior-in-code"></a>Para cambiar el comportamiento inactivo en el código  
  
- En el siguiente ejemplo se cambia el tiempo que se espera antes de persistir y descargar mediante programación.  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Extensibilidad de host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md)
- [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
