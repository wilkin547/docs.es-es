---
description: 'Más información sobre: Introducción a los servicios de flujo de trabajo de hospedaje'
title: Hospedar información general de servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 19f3704f-06bf-4eeb-8724-5224e02d7ead
ms.openlocfilehash: e183dfd7428c11cf20e731ab4a9975a7388b6f98
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743088"
---
# <a name="hosting-workflow-services-overview"></a>Hospedar información general de servicios de flujo de trabajo

Los servicios de flujo de trabajo deben estar hospedados para ejecutarse. La clase <xref:System.ServiceModel.WorkflowServiceHost> es el host de flujo de trabajo que hospeda varias instancias, la configuración y la mensajería WCF (aunque no es necesario que los flujos de trabajo usen la mensajería para ser hospedados).  También se integra con la persistencia, el seguimiento y el control de instancias a través de un conjunto de comportamientos de servicio.  Al igual que el <xref:System.ServiceModel.ServiceHost> de WCF, el <xref:System.ServiceModel.WorkflowServiceHost> puede ser autohospedado por cualquier aplicación .NET administrada u hospedada en web (como un archivo .xamlx) en IIS o WAS.  Los temas de esta sección describen cómo hospedar un servicio de flujo de trabajo.  
  
## <a name="in-this-section"></a>En esta sección  

 [Hospedar servicios de flujo de trabajo](hosting-workflow-services.md)  
 Describe los servicios de hospedaje de flujos de trabajo.  
  
 [Información interna de extensiones del host de servicio de flujo de trabajo](workflow-service-host-internals.md)  
 Describe cómo procesa la clase <xref:System.ServiceModel.WorkflowServiceHost> los mensajes entrantes.  
  
 [Extensibilidad de host de servicio de flujo de trabajo](workflow-service-host-extensibility.md)  
 Describe cómo ampliar la funcionalidad del host de servicio de flujo de trabajo.  
  
 [Extremo de control de flujo de trabajo](workflow-control-endpoint.md)  
 Describe cómo definir un punto de conexión que permite controlar instancias de flujo de trabajo.
  
 [Procedimiento para hospedar un servicio de flujo de trabajo con Windows Server App Fabric](how-to-host-a-workflow-service-with-windows-server-app-fabric.md)  
 Muestra cómo hospedar un servicio de flujo de trabajo existente en Windows Server App Fabric.  
  
 [Configurar WorkflowServiceHost](configuring-workflowservicehost.md)  
 Describe cómo controlar la persistencia, el seguimiento, la inactividad y el comportamiento de las excepciones no controladas.  
  
## <a name="reference"></a>Referencia  

 <xref:System.ServiceModel.Activities.WorkflowServiceHost>  
  
 <xref:System.ServiceModel.Activities.WorkflowService>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>  
  
 <xref:System.ServiceModel.Activation.WorkflowServiceHostFactory>  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Servicios de flujo de trabajo](workflow-services.md)
