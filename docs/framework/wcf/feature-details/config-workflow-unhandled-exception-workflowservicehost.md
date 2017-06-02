---
title: "C&#243;mo: Configurar el comportamiento de excepci&#243;n no controlada del flujo de trabajo con WorkflowServiceHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# C&#243;mo: Configurar el comportamiento de excepci&#243;n no controlada del flujo de trabajo con WorkflowServiceHost
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> es un comportamiento que le permite especificar la acción que se debe llevar a cabo si se produce una excepción no controlada en un flujo de trabajo hospedado en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.En este tema, se muestra cómo configurar este comportamiento en un archivo de configuración.  
  
### Para configurar WorkflowUnhandledExceptionBehavior  
  
1.  Agregue un elemento \<`workflowUnhandledException`\> en un elemento \<`behavior`\> dentro de un elemento \<`serviceBehaviors`\> mediante el atributo `action` para especificar la acción que se debe llevar a cabo cuando se produce una excepción no controlada en el siguiente ejemplo.  
  
    ```  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
    ```  
  
    > [!NOTE]
    >  En el ejemplo de configuración anterior, se usa la configuración simplificada.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     Este comportamiento se puede configurar en código, tal y como se muestra en el siguiente ejemplo.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
  
    ```  
  
     El atributo `action` del elemento \<`workflowUnhandledException`\> puede definirse con uno de los siguientes valores:  
  
     **abandon**  
     Anula la instancia en memoria sin modificar el estado de instancia persistente \(es decir, vuelta al último punto persistente\).  
  
     **abandonAndSuspend**  
     Anula la instancia en memoria y actualiza la instancia persistente que se desea suspender.  
  
     **cancel**  
     Llama a los controladores de cancelaciones de la instancia y, a continuación, completa la instancia en memoria, de manera que también puede eliminarse del almacén de instancias.  
  
     **terminate**  
     Completa la instancia en memoria y la elimina del almacén de instancias.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, vea [Extensibilidad de host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).  
  
## Vea también  
 [Extensibilidad de host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)   
 [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)