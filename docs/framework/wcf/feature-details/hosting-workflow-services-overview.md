---
title: "Hospedar información general de servicios de flujo de trabajo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2c38cd352eb860982b9b1e3aa32daa7aeeee9ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-workflow-services-overview"></a>Hospedar información general de servicios de flujo de trabajo
Los servicios de flujo de trabajo deben estar hospedados para ejecutarse. La clase <xref:System.ServiceModel.WorkflowServiceHost> es el host de flujo de trabajo que hospeda varias instancias, la configuración y la mensajería WCF (aunque no es necesario que los flujos de trabajo usen la mensajería para ser hospedados).  También se integra con la persistencia, el seguimiento y el control de instancias a través de un conjunto de comportamientos de servicio.  Al igual que el <xref:System.ServiceModel.ServiceHost> de WCF, el <xref:System.ServiceModel.WorkflowServiceHost> puede ser autohospedado por cualquier aplicación .NET administrada u hospedada en web (como un archivo .xamlx) en IIS o WAS.  Los temas de esta sección describen cómo hospedar un servicio de flujo de trabajo.  
  
## <a name="in-this-section"></a>En esta sección  
 [Servicios de hospedaje de flujo de trabajo](../../../../docs/framework/wcf/feature-details/hosting-workflow-services.md)  
 Describe los servicios de hospedaje de flujos de trabajo.  
  
 [Funcionamiento interno de Host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-internals.md)  
 Describe cómo procesa la clase <xref:System.ServiceModel.WorkflowServiceHost> los mensajes entrantes.  
  
 [Extensibilidad de Host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 Describe cómo ampliar la funcionalidad del host de servicio de flujo de trabajo.  
  
 [Extremo de Control de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-control-endpoint.md)  
 Describe cómo definir un punto de conexión que permite controlar instancias de flujo de trabajo.  
  
 [Cómo: hospedar un flujo de trabajo no pertenecientes al servicio en IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-non-service-workflow-in-iis.md)  
 Muestra cómo hospedar un flujo de trabajo que no es un servicio de flujo de trabajo en IIS.  
  
 [Cómo: hospedar un servicio de flujo de trabajo con Windows Server App Fabric](../../../../docs/framework/wcf/feature-details/how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 Muestra cómo hospedar un servicio de flujo de trabajo existente en Windows Server App Fabric.  
  
 [Configurar WorkflowServiceHost](../../../../docs/framework/wcf/feature-details/configuring-workflowservicehost.md)  
 Describe cómo controlar la persistencia, el seguimiento, la inactividad y el comportamiento de las excepciones no controladas.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
