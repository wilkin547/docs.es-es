---
title: Procedimiento para configurar el comportamiento de excepción no controlada del flujo de trabajo con WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 3881d1af21dcc0c211c6738162360e522648d949
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593599"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>Procedimiento para configurar el comportamiento de excepción no controlada del flujo de trabajo con WorkflowServiceHost
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> es un comportamiento que le permite especificar la acción que se debe llevar a cabo si se produce una excepción no controlada en un flujo de trabajo hospedado en <xref:System.ServiceModel.Activities.WorkflowServiceHost>. En este tema, se muestra cómo configurar este comportamiento en un archivo de configuración.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>Para configurar WorkflowUnhandledExceptionBehavior  
  
1. Agregue un `workflowUnhandledException` elemento <> en un elemento de> de <`behavior` dentro de un `serviceBehaviors` elemento <>, utilizando el `action` atributo para especificar la acción que se llevará a cabo cuando se produzca una excepción no controlada, tal y como se muestra en el ejemplo siguiente.  
  
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
    > En el ejemplo de configuración anterior, se usa la configuración simplificada. Para obtener más información, vea [configuración simplificada](../simplified-configuration.md).  
  
     Este comportamiento se puede configurar en código, tal y como se muestra en el siguiente ejemplo.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     El `action` atributo del elemento <`workflowUnhandledException`> se puede establecer en uno de los siguientes valores:  
  
     **salir**  
     Anula la instancia en memoria sin modificar el estado de instancia persistente (es decir, vuelta al último punto persistente).  
  
     **abandonAndSuspend**  
     Anula la instancia en memoria y actualiza la instancia persistente que se desea suspender.  
  
     **cancel**  
     Llama a los controladores de cancelaciones de la instancia y, a continuación, completa la instancia en memoria, de manera que también puede eliminarse del almacén de instancias.  
  
     **cancela**  
     Completa la instancia en memoria y la elimina del almacén de instancias.  
  
     Para obtener más información acerca de <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> , consulte [extensibilidad de host de servicio de flujo de trabajo](workflow-service-host-extensibility.md).  
  
## <a name="see-also"></a>Vea también

- [Extensibilidad de host de servicio de flujo de trabajo](workflow-service-host-extensibility.md)
- [Servicios de flujo de trabajo](workflow-services.md)
