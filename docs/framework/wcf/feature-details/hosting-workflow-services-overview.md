---
title: "Hospedar informaci&#243;n general de servicios de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Hospedar informaci&#243;n general de servicios de flujo de trabajo
Los servicios de flujo de trabajo deben estar hospedados para ejecutarse.La clase <xref:System.ServiceModel.WorkflowServiceHost> es el host de flujo de trabajo que hospeda varias instancias, la configuración y la mensajería WCF \(aunque no es necesario que los flujos de trabajo usen la mensajería para ser hospedados\).También se integra con la persistencia, el seguimiento y el control de instancias a través de un conjunto de comportamientos de servicio.Al igual que el <xref:System.ServiceModel.ServiceHost> de WCF, el <xref:System.ServiceModel.WorkflowServiceHost> puede ser autohospedado por cualquier aplicación .NET administrada u hospedada en web \(como un archivo .xamlx\) en IIS o WAS.Los temas de esta sección describen cómo hospedar un servicio de flujo de trabajo.  
  
## En esta sección  
 [Hospedar servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 Describe los servicios de hospedaje de flujos de trabajo.  
  
 [Información interna de extensiones del host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 Describe cómo procesa la clase <xref:System.ServiceModel.WorkflowServiceHost> los mensajes entrantes.  
  
 [Extensibilidad de host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 Describe cómo ampliar la funcionalidad del host de servicio de flujo de trabajo.  
  
 [Extremo de control de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 Describe cómo definir un extremo que permite controlar instancias de flujo de trabajo.  
  
 [Cómo: Hospedar un flujo de trabajo no perteneciente al servicio en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
 Muestra cómo hospedar un flujo de trabajo que no es un servicio de flujo de trabajo en IIS.  
  
 [Cómo: Hospedar un servicio de flujo de trabajo con Windows Server App Fabric](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 Muestra cómo hospedar un servicio de flujo de trabajo existente en Windows Server App Fabric.  
  
 [Configurar WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 Describe cómo controlar la persistencia, el seguimiento, la inactividad y el comportamiento de las excepciones no controladas.  
  
## Referencia  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## Secciones relacionadas  
 [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)