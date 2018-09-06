---
title: Hospedar el servicio de datos (Data Services de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
ms.openlocfilehash: 89f9cc572a6613efba19a93c8d5e441c46a660ac
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43783903"
---
# <a name="hosting-the-data-service-wcf-data-services"></a>Hospedar el servicio de datos (Data Services de WCF)
Mediante el uso de WCF Data Services, puede crear un servicio que expone los datos como un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] fuentes de distribución. Este servicio de datos se define como una clase que hereda de <xref:System.Data.Services.DataService%601>. Esta clase proporciona la funcionalidad necesaria para procesar mensajes de solicitud, realizar actualizaciones en el origen de datos y generar mensajes de respuesta, tal como requiere OData. Sin embargo, no puede enlazar a un servicio de datos y se escuche en un socket de red para las solicitudes HTTP entrantes. Para esta funcionalidad necesaria, el servicio de datos se basa en un componente de hospedaje.

 El host del servicio de datos realiza las siguientes tareas en nombre del servicio de datos:

-   Realiza escuchas de las solicitudes y las enruta al servicio de datos.

-   Crea una instancia del servicio de datos para cada solicitud.

-   Solicita al servicio de datos que procese la solicitud entrante.

-   Envía la respuesta en nombre del servicio de datos.

 Para simplificar el hospedaje de un servicio de datos, WCF Data Services está diseñado para integrarse con Windows Communication Foundation (WCF). El servicio de datos proporciona una implementación WCF predeterminada que actúa como el host de servicio de datos en un [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] aplicación. Por consiguiente, un servicio de datos se puede hospedar de una de las siguientes maneras:

-   En una aplicación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].

-   En una aplicación administrada que admita servicios WCF autohospedados.

-   En algún otro host del servicio de datos personalizado.

## <a name="hosting-a-data-service-in-an-aspnet-application"></a>Hospedar un servicio de datos en una aplicación ASP.NET

Cuando se usa el **Agregar nuevo elemento** cuadro de diálogo de Visual Studio 2015 para definir un servicio de datos en una aplicación de ASP.NET, la herramienta genera dos nuevos archivos en el proyecto. El primer archivo tiene una extensión `.svc` e indica al tiempo de ejecución de WCF cómo crear instancias del servicio de datos. El siguiente es un ejemplo de este archivo para el servicio de datos de ejemplo Northwind creado cuando se completa la [quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):

```
<%@ ServiceHost Language="C#"
    Factory="System.Data.Services.DataServiceHostFactory,
            System.Data.Services, Version=4.0.0.0,
            Culture=neutral, PublicKeyToken=b77a5c561934e089"
    Service="NorthwindService.Northwind" %>
```

 Esta directiva indica a la aplicación que debe crear el host del servicio para la clase del servicio de datos con nombre utilizando la clase <xref:System.Data.Services.DataServiceHostFactory>.

 La página de codigos subyacente del archivo `.svc` contiene la clase que es la implementación del propio servicio de datos, el cual se define para el servicio de datos de ejemplo Northwind del siguiente modo:

 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]

 Dado que un servicio de datos se comporta como un servicio WCF, el servicio de datos se integra con [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y sigue el modelo de programación web de WCF. Para obtener más información, consulte [servicios WCF y ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) y [modelo de programación de WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).

## <a name="self-hosted-wcf-services"></a>Servicios WCF autohospedados
 Dado que incorpora una implementación WCF, WCF Data Services admiten autohospedaje de un servicio de datos como un servicio WCF. Un servicio puede hospedarse a sí mismo en cualquier aplicación [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], como una aplicación de consola. La clase <xref:System.Data.Services.DataServiceHost>, que hereda de <xref:System.ServiceModel.Web.WebServiceHost>, se utiliza para crear instancias del servicio de datos en una dirección concreta.

 El autohospedaje se puede utilizar para el desarrollo y las pruebas porque facilita el despliegue y la solución de problemas del servicio. Sin embargo, este tipo de hospedaje no ofrece las características de administración y hospedaje avanzadas que proporciona [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] o Internet Information Services (IIS). Para obtener más información, consulte [hospedaje en una aplicación administrada](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).

## <a name="defining-a-custom-data-service-host"></a>Definir un host de servicio de datos personalizado
 Para los casos en los que la implementación de un host de WCF sea demasiado restrictiva, se puede definir también un host personalizado para un servicio de datos. Cualquier clase que implemente la interfaz <xref:System.Data.Services.IDataServiceHost> se puede utilizar como el host de red de un servicio de datos. Un host personalizado debe implementar la interfaz <xref:System.Data.Services.IDataServiceHost> y ser capaz de controlar las siguientes responsabilidades básicas del host del servicio de datos:

-   Proporcionar la ruta de acceso raíz del servicio al servicio de datos.

-   Procesar la información de encabezados de respuesta y solicitud en la implementación de miembro de <xref:System.Data.Services.IDataServiceHost> adecuada.

-   Controlar las excepciones iniciadas por el servicio de datos.

-   Validar parámetros en la cadena de consulta.

## <a name="see-also"></a>Vea también

- [Definir Servicios de datos de WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [Exposición de los datos como servicio](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
- [Configuración del servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)
