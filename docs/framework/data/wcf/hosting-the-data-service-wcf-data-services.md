---
description: Más información acerca de cómo hospedar el servicio de datos (Servicios de datos de WCF)
title: Hospedar el servicio de datos (Data Services de WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, Windows Communication Foundation
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
ms.openlocfilehash: 519adde3a3e054d68ff9a1b7acf7ff06c0ca7532
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99765794"
---
# <a name="hosting-the-data-service-wcf-data-services"></a>Hospedar el servicio de datos (Data Services de WCF)

[!INCLUDE [wcf-deprecated](~/includes/wcf-deprecated.md)]

Mediante el uso de Servicios de datos de WCF, puede crear un servicio que exponga los datos como una fuente de Open Data Protocol (OData). Este servicio de datos se define como una clase que hereda de <xref:System.Data.Services.DataService%601>. Esta clase proporciona la funcionalidad necesaria para procesar mensajes de solicitud, realizar actualizaciones en el origen de datos y generar mensajes de respuesta, tal como requiere OData. Sin embargo, un servicio de datos no puede enlazar solicitudes HTTP de entrada ni escucharlas en un socket de red. Para esta funcionalidad necesaria, el servicio de datos se basa en un componente de hospedaje.

 El host del servicio de datos realiza las siguientes tareas en nombre del servicio de datos:

- Realiza escuchas de las solicitudes y las enruta al servicio de datos.

- Crea una instancia del servicio de datos para cada solicitud.

- Solicita al servicio de datos que procese la solicitud entrante.

- Envía la respuesta en nombre del servicio de datos.

 Para simplificar el hospedaje de un servicio de datos, Servicios de datos de WCF está diseñado para integrarse con Windows Communication Foundation (WCF). El servicio de datos proporciona una implementación de WCF predeterminada que actúa como host del servicio de datos en una aplicación ASP.NET. Por consiguiente, un servicio de datos se puede hospedar de una de las siguientes maneras:

- En una aplicación ASP.NET.

- En una aplicación administrada que admita servicios WCF autohospedados.

- En algún otro host del servicio de datos personalizado.

## <a name="hosting-a-data-service-in-an-aspnet-application"></a>Hospedar un servicio de datos en una aplicación ASP.NET

Cuando se usa el cuadro de diálogo **Agregar nuevo elemento** de Visual Studio 2015 para definir un servicio de datos en una aplicación ASP.net, la herramienta genera dos nuevos archivos en el proyecto. El primer archivo tiene una extensión `.svc` e indica al tiempo de ejecución de WCF cómo crear instancias del servicio de datos. A continuación se muestra un ejemplo de este archivo para el servicio de datos de ejemplo Northwind que se crea al completar la guía de [Inicio rápido](quickstart-wcf-data-services.md):

```aspx-csharp
<%@ ServiceHost Language="C#"
    Factory="System.Data.Services.DataServiceHostFactory,
            System.Data.Services, Version=4.0.0.0,
            Culture=neutral, PublicKeyToken=b77a5c561934e089"
    Service="NorthwindService.Northwind" %>
```

 Esta directiva indica a la aplicación que debe crear el host del servicio para la clase del servicio de datos con nombre utilizando la clase <xref:System.Data.Services.DataServiceHostFactory>.

 La página de codigos subyacente del archivo `.svc` contiene la clase que es la implementación del propio servicio de datos, el cual se define para el servicio de datos de ejemplo Northwind del siguiente modo:

 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_service/vb/northwind.svc.vb#servicedefinition)]

 Dado que un servicio de datos se comporta como un servicio WCF, el servicio de datos se integra con ASP.NET y sigue el modelo de programación web de WCF. Para obtener más información, vea [servicios WCF y ASP.net](../../wcf/feature-details/wcf-services-and-aspnet.md) y [modelo de programación web http de WCF](../../wcf/feature-details/wcf-web-http-programming-model.md).

## <a name="self-hosted-wcf-services"></a>Servicios WCF autohospedados

 Dado que incorpora una implementación de WCF, Servicios de datos de WCF admite el hospedaje automático de un servicio de datos como un servicio WCF. Un servicio se puede autohospedar en cualquier .NET Framework aplicación, como una aplicación de consola. La clase <xref:System.Data.Services.DataServiceHost>, que hereda de <xref:System.ServiceModel.Web.WebServiceHost>, se utiliza para crear instancias del servicio de datos en una dirección concreta.

 El autohospedaje se puede utilizar para el desarrollo y las pruebas porque facilita el despliegue y la solución de problemas del servicio. Sin embargo, este tipo de hospedaje no ofrece las características de administración y hospedaje avanzadas proporcionadas por ASP.NET o por Internet Information Services (IIS). Para obtener más información, consulte [hospedaje en una aplicación administrada](../../wcf/feature-details/hosting-in-a-managed-application.md).

## <a name="defining-a-custom-data-service-host"></a>Definir un host de servicio de datos personalizado

 Para los casos en los que la implementación de un host de WCF sea demasiado restrictiva, se puede definir también un host personalizado para un servicio de datos. Cualquier clase que implemente la interfaz <xref:System.Data.Services.IDataServiceHost> se puede utilizar como el host de red de un servicio de datos. Un host personalizado debe implementar la interfaz <xref:System.Data.Services.IDataServiceHost> y ser capaz de controlar las siguientes responsabilidades básicas del host del servicio de datos:

- Proporcionar la ruta de acceso raíz del servicio al servicio de datos.

- Procesar la información de encabezados de respuesta y solicitud en la implementación de miembro de <xref:System.Data.Services.IDataServiceHost> adecuada.

- Controlar las excepciones iniciadas por el servicio de datos.

- Validar parámetros en la cadena de consulta.

## <a name="see-also"></a>Vea también

- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
- [Exposición de los datos como servicio](exposing-your-data-as-a-service-wcf-data-services.md)
- [Configuración del servicio de datos](configuring-the-data-service-wcf-data-services.md)
