---
title: Hospedaje en Internet Information Services
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b933626c2f3f5ee7121d141d3704376efeb54ba5
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="hosting-in-internet-information-services"></a>Hospedaje en Internet Information Services
Una opción para hospedar servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se encuentra dentro de una aplicación de Internet Information Services (IIS). Este modelo de hospedaje es similar al modelo utilizado por [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y los servicios Web ASP.NET (ASMX).  
  
## <a name="versions-of-iis"></a>Versión de IIS  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se puede hospedar en las siguientes versiones de IIS en los sistemas operativos siguientes:  
  
-   IIS 5.1 en [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]. Este entorno es útil para el diseño y desarrollo de aplicaciones hospedadas por IIS que se implementarán más adelante en un sistema operativo de servidor como [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
-   [!INCLUDE[iis601](../../../../includes/iis601-md.md)] en [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. [!INCLUDE[iis601](../../../../includes/iis601-md.md)] proporciona un modelo de procesamiento avanzado que ofrece una mejor escalabilidad, confiabilidad y aislamiento de aplicaciones. Este entorno es adecuado para la implementación de la producción de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que utilizan exclusivamente la comunicación HTTP.  
  
-   IIS 7.0 en [!INCLUDE[wv](../../../../includes/wv-md.md)] y [!INCLUDE[lserver](../../../../includes/lserver-md.md)]. IIS 7.0 proporciona el mismo modelo de procesamiento avanzado que [!INCLUDE[iis601](../../../../includes/iis601-md.md)], pero utiliza Windows Process Activation Service (WAS) para permitir la activación y comunicación por red a través de protocolos que no sean HTTP. Este entorno es adecuado para el desarrollo de servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se comunican sobre cualquier protocolo de red admitido por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (incluidos HTTP, net.tcp, net.pipe y net.msmq). Para obtener más información acerca de WAS, consulte [hospedar en Windows Process Activation Service](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
-   [Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=196496) funciona con [!INCLUDE[iisver](../../../../includes/iisver-md.md)] y servicio de activación de procesos de Windows (WAS) para proporcionar un entorno de servicios NET4 WCF y WF de hospedaje de aplicaciones enriquecido. Estas ventajas incluyen la administración del ciclo de vida de los procesos, el reciclaje de procesos, el hospedaje compartido, la protección rápida ante los errores, los procesos huérfanos, la activación a petición y la supervisión del estado de mantenimiento. Para obtener información detallada, vea [características de hospedaje de AppFabric](http://go.microsoft.com/fwlink/?LinkId=196494) y [conceptos de hospedaje de AppFabric](http://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="benefits-of-iis-hosting"></a>Ventajas del hospedaje de IIS  
 Hospedar los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en IIS tiene varias ventajas:  
  
-   Los servicios [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en IIS se implementan y administran como cualquier otro tipo de aplicación IIS, incluidas las aplicaciones [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y ASMX.  
  
-   IIS proporciona activación de procesos, administración del estado y funciones de reciclaje para aumentar la confiabilidad de las aplicaciones hospedadas.  
  
-   Al igual que [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] pueden beneficiarse del modelo de hospedaje de uso compartido de de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] donde residen múltiples aplicaciones en un proceso de trabajo común para ofrecer una mayor escalabilidad y densidad de servidor.  
  
-   Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedados en IIS usan el mismo modelo de compilación dinámica que [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)], que simplifica el desarrollo e implementación de los servicios hospedados.  
  
 A la hora de decidir si hospedar los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en IIS, es importante recordar que IIS 5.1 e [!INCLUDE[iis601](../../../../includes/iis601-md.md)] están limitados a la comunicación HTTP únicamente. Para obtener más información acerca de cómo elegir un entorno de hospedaje, vea [servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>Implementación de un servicio WCF hospedado por IIS  
 El desarrollo y la implementación de un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] hospedado en IIS constan de las siguientes tareas:  
  
-   Asegurarse de que IIS, ASP.NET, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y el componente de activación HTTP de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se instalan y registran correctamente.  
  
-   Cree una nueva aplicación de IIS o reutilice una aplicación de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] existente.  
  
-   Cree un archivo .svc para el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
-   Implemente la implementación de servicio en la aplicación IIS.  
  
-   Configure el servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
 Para obtener una explicación de cada una de estas tareas, consulte [implementación de un servicio de WCF Internet Information Services-Hosted](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="wcf-services-and-aspnet"></a>Servicios WCF y ASP.NET  
 Los servicios de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueden hospedarse en paralelo con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] o en modo de compatibilidad de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], en el que los servicios pueden aprovechar al máximo las características proporcionadas por la plataforma de aplicaciones web de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. Para obtener una descripción de estas características, consulte [servicios WCF y ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
## <a name="see-also"></a>Vea también  
 [Extensión del hospedaje mediante ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 [Implementación de un servicio WFC hospedado en Internet Information Services](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)  
 [Servicios WCF y ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)  
 [Procedimientos recomendados de hospedaje de Internet Information Services](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)  
 [Configuración de Internet Information Services 7.0 para Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)  
 [Características de hospedaje de Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
