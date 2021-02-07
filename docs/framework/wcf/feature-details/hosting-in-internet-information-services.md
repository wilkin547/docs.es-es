---
description: 'Más información acerca de: hospedar en Internet Information Services'
title: Hospedaje en Internet Information Services
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF], IIS
ms.assetid: ddae14e8-143c-442d-b660-2046809b2d43
ms.openlocfilehash: 23c81bcfccba316500d333d277907d66e5d457c7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743140"
---
# <a name="host-in-internet-information-services"></a>Host en Internet Information Services

Una opción para hospedar servicios de Windows Communication Foundation (WCF) se encuentra dentro de una aplicación Internet Information Services (IIS). Este modelo de hospedaje es similar al modelo utilizado por los servicios Web de ASP.NET y ASP.NET Web Services (ASMX).

## <a name="versions-of-iis"></a>Versión de IIS

WCF se puede hospedar en las siguientes versiones de IIS en los sistemas operativos siguientes:

- IIS 5,1 en Windows XP SP2. Este entorno es útil para el diseño y desarrollo de aplicaciones hospedadas en IIS que se implementan posteriormente en un sistema operativo de servidor como Windows Server 2003.

- IIS 6.0 en Windows Server 2003. IIS 6.0 proporciona un modelo de proceso avanzado que ofrece mejor escalabilidad, confiabilidad y el aislamiento de aplicaciones. Este entorno es adecuado para la implementación de producción de servicios WCF que usan la comunicación HTTP exclusivamente.

- IIS 7.0 en Windows Vista y Windows Server 2008. IIS 7,0 proporciona el mismo modelo de proceso avanzado que IIS 6,0, pero utiliza el servicio de activación de procesos de Windows (WAS) para permitir la activación y la comunicación de red a través de protocolos distintos de HTTP. Este entorno es adecuado para el desarrollo de servicios WCF que se comunican a través de cualquier protocolo de red compatible con WCF (incluidos HTTP, net. TCP, net. Pipe y net. MSMQ). Para obtener más información acerca de WAS, consulte [hospedaje en el servicio de activación de procesos de Windows](hosting-in-windows-process-activation-service.md).

- [Windows Server AppFabric](/previous-versions/appfabric/ff384253(v=azure.10)) funciona con IIS 7,0 y el servicio de activación de procesos de Windows (was) para proporcionar un entorno de hospedaje de aplicaciones enriquecido para los servicios net4 WCF y WF. Estas ventajas incluyen la administración del ciclo de vida de los procesos, el reciclaje de procesos, el hospedaje compartido, la protección rápida ante los errores, los procesos huérfanos, la activación a petición y la supervisión del estado de mantenimiento. Para obtener información detallada, vea [características de hospedaje de AppFabric](/previous-versions/appfabric/ee677189(v=azure.10)) y conceptos de hospedaje de [AppFabric](/previous-versions/appfabric/ee677371(v=azure.10)).

## <a name="benefits-of-iis-hosting"></a>Ventajas del hospedaje de IIS

El hospedaje de servicios WCF en IIS tiene varias ventajas:

- Los servicios WCF hospedados en IIS se implementan y administran como cualquier otro tipo de aplicación IIS, incluidas las aplicaciones ASP.NET y ASMX.

- IIS proporciona activación de procesos, administración del estado y funciones de reciclaje para aumentar la confiabilidad de las aplicaciones hospedadas.

- Al igual que ASP.NET, los servicios WCF hospedados en ASP.NET pueden aprovechar el modelo de hospedaje compartido de ASP.NET en el que varias aplicaciones residen en un proceso de trabajo común para mejorar la densidad y escalabilidad del servidor.

- Los servicios WCF hospedados en IIS usan el mismo modelo de compilación dinámica que ASP.NET 2,0, que simplifica el desarrollo y la implementación de servicios hospedados.

Al decidir hospedar servicios WCF en IIS, es importante recordar que IIS 5,1 e IIS 6,0 están limitados únicamente a la comunicación HTTP. Para obtener más información acerca de cómo elegir un entorno de hospedaje, vea [servicios de hospedaje](../hosting-services.md).

## <a name="deploy-an-iis-hosted-wcf-service"></a>Implementar un servicio WCF hospedado en IIS

El desarrollo e implementación de un servicio WCF hospedado en IIS consta de las siguientes tareas:

- Asegúrese de que IIS, ASP.NET, WCF y el componente de activación HTTP de WCF se hayan instalado y registrado correctamente.

- Cree una nueva aplicación de IIS o reutilice una aplicación de ASP.NET existente.

- Cree un archivo. SVC para el servicio WCF.

- Implemente la implementación de servicio en la aplicación IIS.

- Configure el servicio WCF.

Para obtener una explicación de cada una de estas tareas, consulte [implementación de un servicio WCF de Internet Information Services-Hosted](deploying-an-internet-information-services-hosted-wcf-service.md).

## <a name="wcf-services-and-aspnet"></a>Servicios WCF y ASP.NET

Los servicios WCF se pueden hospedar en paralelo con ASP.NET o en el modo de compatibilidad ASP.NET, en el que los servicios pueden aprovechar al máximo las características proporcionadas por la plataforma de aplicaciones Web ASP.NET. Para obtener una descripción de estas características, vea [servicios WCF y ASP.net](wcf-services-and-aspnet.md).

## <a name="see-also"></a>Vea también

- [Extensión del hospedaje mediante ServiceHostFactory](../extending/extending-hosting-using-servicehostfactory.md)
- [Implementación de un servicio WFC hospedado en Internet Information Services](deploying-an-internet-information-services-hosted-wcf-service.md)
- [Servicios WCF y ASP.NET](wcf-services-and-aspnet.md)
- [Procedimientos recomendados de hospedaje de Internet Information Services](internet-information-services-hosting-best-practices.md)
- [Configuración de Internet Information Services 7.0 para Windows Communication Foundation](configuring-iis-for-wcf.md)
- [Características de hospedaje de Windows Server AppFabric](/previous-versions/appfabric/ee677189(v=azure.10))
