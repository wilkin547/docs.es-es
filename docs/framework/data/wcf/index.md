---
title: WCF Data Services 4.5
description: Obtenga información sobre WCF Data Services, un componente de .NET Framework que admite servicios para exponer y consumir datos mediante la semántica de REST.
ms.date: 03/30/2017
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
ms.openlocfilehash: c36967236c40efbf432d554c3f551aea22cfb148
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90549684"
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5

WCF Data Services (anteriormente conocido como "ADO.NET Data Services") es un componente de la .NET Framework que le permite crear servicios que usan Open Data Protocol (OData) para exponer y consumir datos en Internet o en una intranet mediante la semántica de [transferencia de estado representacional (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm). OData expone los datos como recursos direccionables a través de identificadores uniformes de recursos (URI). Para tener acceso a los datos y cambiarlos se utilizan los verbos HTTP estándar GET, PUT, POST y DELETE. OData usa las convenciones de entidad-relación del [Entity Data Model](../adonet/entity-data-model.md) para exponer los recursos como conjuntos de entidades que se relacionan mediante asociaciones.

WCF Data Services usa el protocolo OData para direccionar y actualizar los recursos. De esta manera, puede tener acceso a estos servicios desde cualquier cliente que admita OData. OData le permite solicitar y escribir datos en los recursos mediante formatos de transferencia conocidos: Atom, un conjunto de estándares para intercambiar y actualizar datos como XML, y notación de objetos JavaScript (JSON), un formato de intercambio de datos basado en texto que se utiliza mucho en aplicaciones AJAX.

WCF Data Services pueden exponer datos procedentes de varios orígenes como fuentes de OData. Las herramientas de Visual Studio facilitan la creación de un servicio basado en OData mediante un modelo de datos de ADO.NET Entity Framework. También puede crear fuentes de OData basadas en clases de Common Language Runtime (CLR) e incluso datos enlazados en tiempo de ejecución o sin tipo.

WCF Data Services también incluye un conjunto de bibliotecas de cliente, uno para las aplicaciones cliente de .NET Framework general y otro específicamente para las aplicaciones basadas en Silverlight. Estas bibliotecas cliente proporcionan un modelo de programación basado en objetos cuando se tiene acceso a una fuente OData desde entornos como .NET Framework y Silverlight.

## <a name="where-should-i-start"></a>¿Por dónde empiezo?

En función de sus intereses, considere la posibilidad de empezar a trabajar con WCF Data Services en uno de los siguientes temas.

Quiero comenzar de inmediato…

- [Guía de inicio rápido](quickstart-wcf-data-services.md)

- [Introducción](getting-started-with-wcf-data-services.md)

Simplemente mostrarme parte del código...

- [Guía de inicio rápido](quickstart-wcf-data-services.md)

- [Procedimiento para ejecutar consultas de servicios de datos](how-to-execute-data-service-queries-wcf-data-services.md)

- [Procedimiento para enlazar datos a elementos de Windows Presentation Foundation](bind-data-to-wpf-elements-wcf-data-services.md)

Deseo obtener más información acerca de OData...

- [Notas del producto: Introducción a OData](https://download.microsoft.com/download/E/5/A/E5A59052-EE48-4D64-897B-5F7C608165B8/IntroducingOData.pdf)
- [Sitio web Open Data Protocol](https://www.odata.org/)
- [OData: SDK](https://www.odata.org/ecosystem/)

Deseo ver ejemplos de un extremo a otro...

- [Inicio rápido de WCF Data Services](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/WCF%20Data%20Services%20Quickstart%20(OData%20Service%20and%20WPF%20Client))
- [SDK de OData: código de ejemplo](https://www.odata.org/ecosystem/#sdk)

¿Cómo se integra con Visual Studio?

- [Generar la biblioteca cliente del servicio de datos](generating-the-data-service-client-library-wcf-data-services.md)

- [Creación del servicio de datos](creating-the-data-service.md)

- [Proveedor de Entity Framework](entity-framework-provider-wcf-data-services.md)

¿Qué se puede hacer con Privileged Identity Management (PIM)?

- [Información general](wcf-data-services-overview.md)

- [Escenarios de aplicación](application-scenarios-wcf-data-services.md)

Deseo usar LINQ...

- [Consultar el servicio de datos](querying-the-data-service-wcf-data-services.md)

- [Consideraciones sobre LINQ](linq-considerations-wcf-data-services.md)

- [Procedimiento para ejecutar consultas de servicios de datos](how-to-execute-data-service-queries-wcf-data-services.md)

Todavía necesito más información...

- [Blog del equipo de Servicios de datos de WCF](/archive/blogs/astoriateam/)

- [Recursos](wcf-data-services-resources.md)

## <a name="in-this-section"></a>En esta sección

[Información general](wcf-data-services-overview.md)

Proporciona información general sobre las características y la funcionalidad disponibles en WCF Data Services.

[Novedades de WCF Data Services 5,0](/previous-versions/dotnet/wcf-data-services/ee373845(v=vs.103))

Describe la nueva funcionalidad de WCF Data Services y la compatibilidad con las nuevas características de OData.

[Introducción](getting-started-with-wcf-data-services.md)

Describe cómo exponer y consumir fuentes de OData mediante WCF Data Services.

[Definir Servicios de datos de WCF](defining-wcf-data-services.md)

Describe cómo crear y configurar un servicio de datos que exponga fuentes de OData.

[Biblioteca cliente de Data Services de WCF](wcf-data-services-client-library.md)

Describe cómo usar las bibliotecas de cliente para consumir fuentes de OData desde una aplicación cliente de .NET Framework.

## <a name="see-also"></a>Vea también

- [Transferencia de estado representacional (REST)](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
