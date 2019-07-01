---
title: Hospedaje en Internet Information Services
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 3940d8436ba5441d4e884879213a7a782214cb05
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2019
ms.locfileid: "67486752"
---
# <a name="hosting-in-internet-information-services"></a>Hospedaje en Internet Information Services
Es una opción para hospedar servicios Windows Communication Foundation (WCF) dentro de una aplicación de Internet Information Services (IIS). Este modelo de hospedaje es similar al modelo utilizado por ASP.NET y servicios Web de ASP.NET Web services (ASMX).  
  
## <a name="versions-of-iis"></a>Versión de IIS  
 WCF puede hospedarse en las siguientes versiones de IIS en los sistemas operativos siguientes:  
  
- IIS 5.1 en [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)]. Este entorno es útil para el diseño y desarrollo de aplicaciones hospedadas por IIS que se implementarán más adelante en un sistema operativo de servidor como [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].  
  
- IIS 6.0 en [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. IIS 6.0 proporciona un modelo de proceso avanzado que ofrece una mejor escalabilidad, confiabilidad y aislamiento de la aplicación. Este entorno es adecuado para la implementación de producción de servicios WCF que utilizan comunicación HTTP de forma exclusiva.  
  
- IIS 7.0 en [!INCLUDE[wv](../../../../includes/wv-md.md)] y [!INCLUDE[lserver](../../../../includes/lserver-md.md)]. IIS 7.0 proporciona el mismo modelo de proceso avanzado que IIS 6.0, pero usa el servicio de activación de procesos de Windows (WAS) para permitir la activación y comunicación de red a través de protocolos que no sean HTTP. Este entorno es adecuado para el desarrollo de servicios WCF que se comunican a través de cualquier protocolo de red compatible con WCF (incluidos HTTP, net.tcp, net.pipe y net.msmq). Para obtener más información acerca de WAS, vea [hospedaje en Windows Process Activation Service](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md).  
  
- [Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=196496) funciona con IIS 7.0 y el servicio de activación de proceso de Windows (WAS) para proporcionar un entorno para servicios NET4 WCF y WF de hospedaje de aplicaciones enriquecido. Estas ventajas incluyen la administración del ciclo de vida de los procesos, el reciclaje de procesos, el hospedaje compartido, la protección rápida ante los errores, los procesos huérfanos, la activación a petición y la supervisión del estado de mantenimiento. Para obtener información detallada, consulte [AppFabric Hosting Features](https://go.microsoft.com/fwlink/?LinkId=196494) y [conceptos de hospedaje de AppFabric](https://go.microsoft.com/fwlink/?LinkId=196495).  
  
## <a name="benefits-of-iis-hosting"></a>Ventajas del hospedaje de IIS  
 Hospedaje de servicios WCF en IIS tiene varias ventajas:  
  
- Servicios WCF hospedados en IIS se implementan y administran como cualquier otro tipo de aplicación de IIS, incluidas las aplicaciones de ASP.NET y ASMX.  
  
- IIS proporciona activación de procesos, administración del estado y funciones de reciclaje para aumentar la confiabilidad de las aplicaciones hospedadas.  
  
- Como ASP.NET, servicios WCF hospedados en ASP.NET pueden aprovechar el modelo de hospedaje de ASP.NET compartido donde varias aplicaciones residen en un proceso de trabajo común para escalabilidad y densidad mejorada de los servidores.  
  
- Servicios WCF hospedados en IIS usan el mismo modelo de compilación dinámica como ASP.NET 2.0, lo que simplifica el desarrollo e implementación de servicios hospedados.  
  
 La hora de decidir hospedar los servicios de WCF en IIS, es importante recordar que IIS 5.1 e IIS 6.0 se limitan a la comunicación HTTP. Para obtener más información acerca de cómo elegir un entorno de hospedaje, vea [servicios de hospedaje](../../../../docs/framework/wcf/hosting-services.md).  
  
## <a name="deploying-an-iis-hosted-wcf-service"></a>Implementación de un servicio WCF hospedado por IIS  
 Desarrollar e implementar un servicio WCF hospedado por IIS consta de las siguientes tareas:  
  
- Asegúrese de que IIS, ASP.NET, WCF y el componente de activación HTTP de WCF están correctamente instalados y registrados.  
  
- Crear una nueva aplicación IIS o reutilice una aplicación ASP.NET existente.  
  
- Cree un archivo .svc para el servicio WCF.  
  
- Implemente la implementación de servicio en la aplicación IIS.  
  
- Configurar el servicio WCF.  
  
 Para obtener una explicación de cada una de estas tareas, consulte [implementación de un servicio de WCF Internet Information Services-Hosted](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md).  
  
## <a name="wcf-services-and-aspnet"></a>Servicios WCF y ASP.NET  
 Los servicios WCF pueden ser hospedado ya sea por en paralelo con ASP.NET o en modo de compatibilidad de ASP.NET en el que servicios pueden aprovechar al máximo las características proporcionadas por la plataforma de aplicación Web ASP.NET. Para obtener una explicación de estas características, consulte [servicios WCF y ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).  
  
## <a name="see-also"></a>Vea también

- [Extensión del hospedaje mediante ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)
- [Implementación de un servicio WFC hospedado en Internet Information Services](../../../../docs/framework/wcf/feature-details/deploying-an-internet-information-services-hosted-wcf-service.md)
- [Servicios WCF y ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [Procedimientos recomendados de hospedaje de Internet Information Services](../../../../docs/framework/wcf/feature-details/internet-information-services-hosting-best-practices.md)
- [Configuración de Internet Information Services 7.0 para Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/configuring-iis-for-wcf.md)
- [Características de hospedaje de Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkId=201276)
