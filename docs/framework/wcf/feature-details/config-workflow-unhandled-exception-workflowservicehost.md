---
title: Procedimiento Configurar el flujo de trabajo no controla el comportamiento de excepción con WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 9a13bb9390e891295491722898bd780bc1cac587
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636162"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>Procedimiento Configurar el flujo de trabajo no controla el comportamiento de excepción con WorkflowServiceHost
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> es un comportamiento que le permite especificar la acción que se debe llevar a cabo si se produce una excepción no controlada en un flujo de trabajo hospedado en <xref:System.ServiceModel.Activities.WorkflowServiceHost>. En este tema, se muestra cómo configurar este comportamiento en un archivo de configuración.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>Para configurar WorkflowUnhandledExceptionBehavior  
  
1.  Agregar un <`workflowUnhandledException`> elemento en un <`behavior`> elemento dentro de un <`serviceBehaviors`> elemento, mediante el `action` atributo para especificar la acción que se realizará cuando se produce una excepción no controlada tal como se muestra en el ejemplo siguiente.  
  
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
    >  En el ejemplo de configuración anterior, se usa la configuración simplificada. Para obtener más información, consulte [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     Este comportamiento se puede configurar en código, tal y como se muestra en el siguiente ejemplo.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     El `action` atributo de la <`workflowUnhandledException`> elemento se puede establecer en uno de los siguientes valores:  
  
     **abandon**  
     Anula la instancia en memoria sin modificar el estado de instancia persistente (es decir, vuelta al último punto persistente).  
  
     **abandonAndSuspend**  
     Anula la instancia en memoria y actualiza la instancia persistente que se desea suspender.  
  
     **cancel**  
     Llama a los controladores de cancelaciones de la instancia y, a continuación, completa la instancia en memoria, de manera que también puede eliminarse del almacén de instancias.  
  
     **terminate**  
     Completa la instancia en memoria y la elimina del almacén de instancias.  
  
     Para obtener más información acerca de <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, consulte [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## <a name="see-also"></a>Vea también
- [Extensibilidad de host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
