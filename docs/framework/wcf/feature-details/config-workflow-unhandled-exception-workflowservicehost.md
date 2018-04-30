---
title: 'Cómo: Configurar el comportamiento de excepción no controlada del flujo de trabajo con WorkflowServiceHost'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a49b3d42e51ed7a0a57deb392f5728f407909b00
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>Cómo: Configurar el comportamiento de excepción no controlada del flujo de trabajo con WorkflowServiceHost
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> es un comportamiento que le permite especificar la acción que se debe llevar a cabo si se produce una excepción no controlada en un flujo de trabajo hospedado en <xref:System.ServiceModel.Activities.WorkflowServiceHost>. En este tema, se muestra cómo configurar este comportamiento en un archivo de configuración.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>Para configurar WorkflowUnhandledExceptionBehavior  
  
1.  Agregar un <`workflowUnhandledException`> elemento en un <`behavior`> elemento dentro de un <`serviceBehaviors`> elemento, con el `action` atributo para especificar la acción que se realizará cuando se produce una excepción no controlada tal como se muestra en el ejemplo siguiente.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    >  En el ejemplo de configuración anterior, se usa la configuración simplificada. Para obtener más información, consulte [configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     Este comportamiento se puede configurar en código, tal y como se muestra en el siguiente ejemplo.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     El `action` atributo de la <`workflowUnhandledException`> elemento puede establecerse en uno de los siguientes valores:  
  
     **Abandono**  
     Anula la instancia en memoria sin modificar el estado de instancia persistente (es decir, vuelta al último punto persistente).  
  
     **abandonAndSuspend**  
     Anula la instancia en memoria y actualiza la instancia persistente que se desea suspender.  
  
     **Cancelar**  
     Llama a los controladores de cancelaciones de la instancia y, a continuación, completa la instancia en memoria, de manera que también puede eliminarse del almacén de instancias.  
  
     **terminate**  
     Completa la instancia en memoria y la elimina del almacén de instancias.  
  
     Para obtener más información acerca de <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, consulte [extensibilidad de Host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="see-also"></a>Vea también  
 [Extensibilidad de host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
