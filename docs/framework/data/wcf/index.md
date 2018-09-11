---
title: WCF Data Services 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: 9ece2fe051855d0fd39556f56a4343ead2c437bc
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44368090"
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5

WCF Data Services (anteriormente conocido como "ADO.NET Data Services") es un componente de .NET Framework que permite crear servicios que utilizan el [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] para exponer y consumir datos a través de Internet o una intranet mediante la semántica de [ transferencia de estado representacional (REST)](https://go.microsoft.com/fwlink/?LinkId=113919). OData expone los datos como recursos direccionables a través de identificadores uniformes de recursos (URI). Para tener acceso a los datos y cambiarlos se utilizan los verbos HTTP estándar GET, PUT, POST y DELETE. OData utiliza las convenciones de entidad-relación de la [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) para exponer los recursos como conjuntos de entidades que se relacionan mediante asociaciones.

WCF Data Services usa el Protocolo OData para direccionar y actualizar los recursos. De este modo, puede tener acceso a estos servicios desde cualquier cliente que es compatible con OData. OData le permite solicitar y escribir datos a los recursos mediante el uso de formatos de transferencia conocidos: Atom, un conjunto de estándares para intercambiar y actualizar datos como XML y JavaScript Object Notation (JSON), un formato de intercambio de datos basado en texto muy usado en AJAX aplicación.

WCF Data Services puede exponer datos procedentes de diversos orígenes como fuentes de OData. Herramientas de Visual Studio facilitan la creación de un servicio basado en OData mediante el uso de un modelo de datos de ADO.NET Entity Framework. También puede crear fuentes de OData basadas en clases de common language runtime (CLR) y los datos incluso en tiempo de ejecución o sin tipo.

WCF Data Services también incluye un conjunto de bibliotecas de cliente, uno para las aplicaciones cliente de .NET Framework generales y otro específicamente para las aplicaciones basadas en Silverlight. Estas bibliotecas cliente proporcionan un modelo de programación basado en objetos cuando tiene acceso a fuentes de OData desde entornos como .NET Framework y Silverlight.

## <a name="where-should-i-start"></a>¿Por dónde empiezo?

Dependiendo de sus intereses, considere la posibilidad de introducción a WCF Data Services en uno de los temas siguientes.

Quiero comenzar de inmediato…

-   [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

-   [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

-   [Inicio rápido de Silverlight](https://go.microsoft.com/fwlink/?LinkID=192782)

-   [Inicio rápido de Silverlight para desarrollo de Windows Phone](https://go.microsoft.com/fwlink/?LinkID=214535)

Deseo ver algo de código...

-   [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)

-   [Cómo: ejecutar consultas de servicios de datos](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

-   [Cómo: enlazar datos a elementos de Windows Presentation Foundation](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)

Quiero saber más sobre OData...

 -   [Notas del producto: introducción a OData](https://go.microsoft.com/fwlink/?LinkId=220867)

-   [Sitio web de Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=184554)

-   [OData: SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

-   [OData: preguntas más frecuentes](https://go.microsoft.com/fwlink/?LinkId=185867)

Deseo ver algunos vídeos …

-   [Guía para principiantes de Servicios de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=220864)

-   [Vídeos para desarrolladores de Servicios de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=220861)

-   [OData: sitio web para desarrolladores](https://go.microsoft.com/fwlink/?LinkId=185866)

Deseo ver ejemplos completos...

-   [Ejemplos de documentación de Servicios de datos de WCF en la galería de ejemplos de MSDN](https://go.microsoft.com/fwlink/?LinkID=220865)

-   [Otros ejemplos de Servicios de datos de WCF en la galería de ejemplos de MSDN](https://go.microsoft.com/fwlink/?LinkId=220866)

-   [OData: SDK](https://go.microsoft.com/fwlink/?LinkID=185248)

¿Cómo se integra con Visual Studio?

-   [Generar la biblioteca cliente del servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)

-   [Creación del servicio de datos](../../../../docs/framework/data/wcf/creating-the-data-service.md)

-   [Proveedor de Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)

¿Qué me permite hacer?

-   [Información general](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

-   [Notas del producto: introducción a OData](https://go.microsoft.com/fwlink/?LinkId=220867)

-   [Escenarios de aplicación](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)

Deseo usar Silverlight …

-   [Inicio rápido de Silverlight](https://go.microsoft.com/fwlink/?LinkID=192782)

-   [Servicios de datos de WCF (Silverlight)](https://go.microsoft.com/fwlink/?LinkID=143149)

-   [Introducción a Silverlight](https://go.microsoft.com/fwlink/?LinkId=148366)

Deseo usar LINQ …

-   [Consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)

-   [Consideraciones sobre LINQ](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)

-   [Cómo: ejecutar consultas de servicios de datos](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)

Sigo necesitando más información...

-   [Blog del equipo de Servicios de datos de WCF](https://go.microsoft.com/fwlink/?LinkID=150511)

-   [Recursos](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)

-   [Centro para desarrolladores de Servicios de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=220868)

-   [Sitio web de Open Data Protocol](https://go.microsoft.com/fwlink/?LinkID=184554)

## <a name="in-this-section"></a>En esta sección

 [Información general](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)

 Proporciona información general de las características y funciones disponibles en WCF Data Services.

 [Novedades de Servicios de datos de WCF](https://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)

 Describe la nueva funcionalidad en WCF Data Services y compatibilidad con nuevas características de OData.

 [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)

 Describe cómo exponer y consumir fuentes de OData mediante WCF Data Services.

 [Definir Servicios de datos de WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)

 Describe cómo crear y configurar un servicio de datos que expone fuentes de OData.

 [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

 Describe cómo usar las bibliotecas de cliente para consumir fuentes de OData desde una aplicación de cliente de .NET Framework.

## <a name="see-also"></a>Vea también

- [Transferencia de estado representacional (REST)](https://go.microsoft.com/fwlink/?LinkId=113919)
