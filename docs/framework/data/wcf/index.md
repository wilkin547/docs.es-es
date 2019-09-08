---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 017fe2177cf824d461b4c51ea805f75b6ddbe064
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70779992"
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5

WCF Data Services (anteriormente conocido como "ADO.net Data Services") es un componente de la .NET Framework que le permite crear servicios que utilizan [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] para exponer y consumir datos en Internet o en una intranet mediante la semántica de estado de [representación. Transfer (REST)](https://go.microsoft.com/fwlink/?LinkId=113919). OData expone los datos como recursos direccionables a través de identificadores uniformes de recursos (URI). Para tener acceso a los datos y cambiarlos se utilizan los verbos HTTP estándar GET, PUT, POST y DELETE. OData usa las convenciones de entidad-relación del [Entity Data Model](../adonet/entity-data-model.md) para exponer los recursos como conjuntos de entidades que se relacionan mediante asociaciones.

WCF Data Services usa el protocolo OData para direccionar y actualizar los recursos. De esta manera, puede tener acceso a estos servicios desde cualquier cliente que admita OData. OData permite solicitar y escribir datos en los recursos mediante formatos de transferencia conocidos: Atom, un conjunto de estándares para intercambiar y actualizar datos como XML y notación de objetos JavaScript (JSON), un formato de intercambio de datos basado en texto que se usa en las aplicaciones AJAX.

WCF Data Services pueden exponer datos procedentes de varios orígenes como fuentes de OData. Las herramientas de Visual Studio facilitan la creación de un servicio basado en OData mediante un modelo de datos de ADO.NET Entity Framework. También puede crear fuentes de OData basadas en clases de Common Language Runtime (CLR) e incluso datos enlazados en tiempo de ejecución o sin tipo.

WCF Data Services también incluye un conjunto de bibliotecas de cliente, uno para las aplicaciones cliente de .NET Framework general y otro específicamente para las aplicaciones basadas en Silverlight. Estas bibliotecas de cliente proporcionan un modelo de programación basado en objetos cuando se tiene acceso a una fuente de OData desde entornos como el .NET Framework y Silverlight.

## <a name="where-should-i-start"></a>¿Por dónde empiezo?

En función de sus intereses, considere la posibilidad de empezar a trabajar con WCF Data Services en uno de los siguientes temas.

Quiero comenzar de inmediato…

- [Inicio rápido](quickstart-wcf-data-services.md)

- [Introducción](getting-started-with-wcf-data-services.md)

- [Inicio rápido de Silverlight](https://go.microsoft.com/fwlink/?LinkID=192782)

- [Inicio rápido de Silverlight para desarrollo de Windows Phone](https://go.microsoft.com/fwlink/?LinkID=214535)

Simplemente mostrarme parte del código...

- [Inicio rápido](quickstart-wcf-data-services.md)

- [Cómo: Ejecutar consultas de servicio de datos](how-to-execute-data-service-queries-wcf-data-services.md)

- [Cómo: Enlazar datos a elementos de Windows Presentation Foundation](bind-data-to-wpf-elements-wcf-data-services.md)

Deseo obtener más información acerca de OData...

- [Notas del producto Introducción a OData](https://go.microsoft.com/fwlink/?LinkId=220867)

- [Sitio web de Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=184554)

- [OData SKD](https://go.microsoft.com/fwlink/?LinkID=185248)

- [OData Preguntas más frecuentes](https://go.microsoft.com/fwlink/?LinkId=185867)

Quiero ver algunos vídeos...

- [Guía para principiantes de Servicios de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=220864)

- [Vídeos para desarrolladores de Servicios de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=220861)

- [OData Sitio web de desarrolladores](https://go.microsoft.com/fwlink/?LinkId=185866)

Deseo ver ejemplos de un extremo a otro...

- [Ejemplos de documentación de Servicios de datos de WCF en la galería de ejemplos de MSDN](https://go.microsoft.com/fwlink/?LinkID=220865)

- [Otros ejemplos de Servicios de datos de WCF en la galería de ejemplos de MSDN](https://go.microsoft.com/fwlink/?LinkId=220866)

- [OData SKD](https://go.microsoft.com/fwlink/?LinkID=185248)

¿Cómo se integra con Visual Studio?

- [Generar la biblioteca cliente del servicio de datos](generating-the-data-service-client-library-wcf-data-services.md)

- [Creación del servicio de datos](creating-the-data-service.md)

- [Proveedor de Entity Framework](entity-framework-provider-wcf-data-services.md)

¿Qué me permite hacer?

- [Información general](wcf-data-services-overview.md)

- [Notas del producto Introducción a OData](https://go.microsoft.com/fwlink/?LinkId=220867)

- [Escenarios de aplicación](application-scenarios-wcf-data-services.md)

Deseo usar Silverlight...

- [Inicio rápido de Silverlight](https://go.microsoft.com/fwlink/?LinkID=192782)

- [Servicios de datos de WCF (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149)

- [Introducción a Silverlight](https://go.microsoft.com/fwlink/?LinkId=148366)

Deseo usar LINQ...

- [Consultar el servicio de datos](querying-the-data-service-wcf-data-services.md)

- [Consideraciones sobre LINQ](linq-considerations-wcf-data-services.md)

- [Cómo: Ejecutar consultas de servicio de datos](how-to-execute-data-service-queries-wcf-data-services.md)

Todavía necesito más información...

- [Blog del equipo de Servicios de datos de WCF](https://go.microsoft.com/fwlink/?LinkID=150511)

- [Recursos](wcf-data-services-resources.md)

- [Centro para desarrolladores de Servicios de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=220868)

- [Sitio web de Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a>En esta sección

[Información general](wcf-data-services-overview.md)

Proporciona información general sobre las características y la funcionalidad disponibles en WCF Data Services.

[Novedades de WCF Data Services 5,0](https://docs.microsoft.com/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))

Describe la nueva funcionalidad de WCF Data Services y la compatibilidad con las nuevas características de OData.

[Introducción](getting-started-with-wcf-data-services.md)

Describe cómo exponer y consumir fuentes de OData mediante WCF Data Services.

[Definir Servicios de datos de WCF](defining-wcf-data-services.md)

Describe cómo crear y configurar un servicio de datos que exponga fuentes de OData.

[Biblioteca cliente de Servicios de datos de WCF](wcf-data-services-client-library.md)

Describe cómo usar las bibliotecas de cliente para consumir fuentes de OData desde una aplicación cliente de .NET Framework.

## <a name="see-also"></a>Vea también

- [Transferencia de estado representacional (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)
