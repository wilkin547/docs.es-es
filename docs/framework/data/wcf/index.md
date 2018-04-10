---
title: WCF Data Services 4.5
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Astoria
- WCF Data Services, getting started
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b5b27a51dcec17f72b86e77a7ee2ab773aec1dc3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="wcf-data-services-45"></a>WCF Data Services 4.5
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] (antes conocido como "ADO.NET Data Services") es un componente de .NET Framework que permite crear servicios que usan [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] para exponer y usar datos a través de la Web o de una intranet mediante la semántica de [transferencia de estado de representación (REST)](http://go.microsoft.com/fwlink/?LinkId=113919). [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] expone los datos como recursos direccionables a través de identificadores uniformes de recursos (URI). Para tener acceso a los datos y cambiarlos se utilizan los verbos HTTP estándar GET, PUT, POST y DELETE. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] usa las convenciones del modelo entidad-relación de [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md) para exponer los recursos como conjuntos de entidades que están relacionadas por medio de asociaciones.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] usa el protocolo de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] para direccionar y actualizar los recursos. De esta manera, puede tener acceso a estos servicios desde cualquier cliente que admita [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] le permite solicitar datos a los recursos y escribir en ellos mediante formatos de transferencia conocidos: Atom, un conjunto de estándares para intercambiar y actualizar datos como XML, y Notación de objetos JavaScript (JSON), un formato de intercambio de datos basado en texto muy usado en aplicaciones AJAX.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] puede exponer datos procedentes de varios orígenes como fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Las herramientas de Visual Studio facilitan la creación de un servicio basado en [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] mediante el uso de un modelo de datos de ADO.NET Entity Framework. También puede crear fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] basadas en clases de Common Language Runtime (CLR) e incluso en datos enlazados en tiempo de ejecución o datos sin tipo.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] también incluye dos conjuntos de bibliotecas de cliente, uno para las aplicaciones cliente de .NET Framework generales y otro específicamente para las aplicaciones basadas en Silverlight. Estas bibliotecas cliente proporcionan un modelo de programación basado en objetos cuando se tiene acceso a una fuente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] desde entornos como .NET Framework y Silverlight.  
  
## <a name="where-should-i-start"></a>¿Por dónde empiezo?  
 En función de sus intereses, puede comenzar con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] en uno de los siguientes temas.  
  
 Deseo comenzar de inmediato…  
 -   [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
  
-   [Inicio rápido de Silverlight](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [Inicio rápido de Silverlight para desarrollo de Windows Phone](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
 Deseo ver algo de código…  
 -   [Inicio rápido](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [Cómo: ejecutar consultas de servicios de datos](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
-   [Cómo: enlazar datos a elementos de Windows Presentation Foundation](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)  
  
 Deseo saber más sobre [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…  
 -   [Notas del producto: introducción a OData](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [Sitio web de Open Data Protocol](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
-   [OData: SDK](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
-   [OData: preguntas más frecuentes](http://go.microsoft.com/fwlink/?LinkId=185867)  
  
 Deseo ver algunos vídeos…  
 -   [Guía para principiantes de Servicios de datos de WCF](http://go.microsoft.com/fwlink/?LinkId=220864)  
  
-   [Vídeos para desarrolladores de Servicios de datos de WCF](http://go.microsoft.com/fwlink/?LinkId=220861)  
  
-   [OData: sitio web para desarrolladores](http://go.microsoft.com/fwlink/?LinkId=185866)  
  
 Deseo ver ejemplos completos  
 -   [Ejemplos de documentación de Servicios de datos de WCF en la galería de ejemplos de MSDN](http://go.microsoft.com/fwlink/?LinkID=220865)  
  
-   [Otros ejemplos de Servicios de datos de WCF en la galería de ejemplos de MSDN](http://go.microsoft.com/fwlink/?LinkId=220866)  
  
-   [OData: SDK](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
 ¿Cómo se integra con Visual Studio?  
 -   [Generar la biblioteca cliente del servicio de datos](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
  
-   [Creación del servicio de datos](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
  
-   [Proveedor de Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
  
 ¿Qué me permite hacer?  
 -   [Información general](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
  
-   [Notas del producto: introducción a OData](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [Escenarios de aplicación](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)  
  
 Deseo usar Silverlight…  
 -   [Inicio rápido de Silverlight](http://go.microsoft.com/fwlink/?LinkID=192782)  
  
-   [Servicios de datos de WCF (Silverlight)](http://go.microsoft.com/fwlink/?LinkID=143149)  
  
-   [Introducción a Silverlight](http://go.microsoft.com/fwlink/?LinkId=148366)  
  
 Deseo crear una aplicación Windows Phone…  
 -   [Inicio rápido de Silverlight para desarrollo de Windows Phone](http://go.microsoft.com/fwlink/?LinkID=214535)  
  
-   [Cliente de Open Data Protocol (OData) para Windows Phone](http://go.microsoft.com/fwlink/?LinkID=208749)  
  
 Deseo usar LINQ…  
 -   [Consultar el servicio de datos](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
  
-   [Consideraciones sobre LINQ](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
-   [Cómo: ejecutar consultas de servicios de datos](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 Necesito un poco más información…  
 -   [Blog del equipo de Servicios de datos de WCF](http://go.microsoft.com/fwlink/?LinkID=150511)  
  
-   [Recursos](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)  
  
-   [Centro para desarrolladores de Servicios de datos de WCF](http://go.microsoft.com/fwlink/?LinkId=220868)  
  
-   [Sitio web de Open Data Protocol](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
 Proporciona información general sobre las características y la funcionalidad disponibles en [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  
  
 [Novedades de Servicios de datos de WCF](http://msdn.microsoft.com/library/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 Describe nuevas funciones de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] y la compatibilidad con las nuevas características de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 [Introducción](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 Describe cómo exponer y consumir fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] mediante [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  
  
 [Definir Servicios de datos de WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 Describe cómo crear y configurar un servicio de datos que expone fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 [Biblioteca cliente de Servicios de datos de WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 Describe cómo usar las bibliotecas cliente para consumir fuentes de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] desde una aplicación cliente de .NET Framework.  
  
## <a name="see-also"></a>Vea también  
 [Transferencia de estado representacional (REST)](http://go.microsoft.com/fwlink/?LinkId=113919)
