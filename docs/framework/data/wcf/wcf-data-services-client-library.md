---
title: Biblioteca cliente de Data Services de WCF
description: Obtenga información acerca de cómo usar las bibliotecas de cliente de WCF Data Services para obtener acceso y cambiar los datos de una aplicación cliente de .NET Framework.
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: d1554dd149e3d447a67cd2ef41aef9042e14fd06
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204364"
---
# <a name="wcf-data-services-client-library"></a>Biblioteca cliente de Data Services de WCF

Cualquier aplicación puede interactuar con un servicio de datos basado en Open Data Protocol (OData) si puede enviar una solicitud HTTP y procesar la fuente de OData que devuelve un servicio de datos. Esta interoperabilidad le permite tener acceso a los servicios basados en OData desde una amplia gama de aplicaciones habilitadas para Web. WCF Data Services incluye bibliotecas de cliente que proporcionan una experiencia de programación más enriquecida cuando se usan fuentes de OData desde .NET Framework o aplicaciones basadas en Silverlight.  
  
 Las dos clases principales de la biblioteca cliente son <xref:System.Data.Services.Client.DataServiceContext> y <xref:System.Data.Services.Client.DataServiceQuery%601>. La clase <xref:System.Data.Services.Client.DataServiceContext> encapsula las operaciones admitidas en un servicio de datos determinado. Aunque los servicios de OData no tienen estado, el contexto no es. Por lo tanto, puede utilizar la <xref:System.Data.Services.Client.DataServiceContext> clase para mantener el estado en el cliente entre las interacciones con el servicio de datos con el fin de admitir características como la administración de cambios. Esta clase también administra las identidades y realiza el seguimiento de los cambios. La clase <xref:System.Data.Services.Client.DataServiceQuery%601> representa una consulta en un conjunto de entidades concreto.  
  
 En esta sección se describe cómo usar las bibliotecas de cliente para obtener acceso a los datos de una aplicación cliente de .NET Framework y para cambiarlos. Para obtener más información sobre cómo usar la biblioteca de cliente de WCF Data Services con una aplicación basada en Silverlight, vea [WCF Data Services (Silverlight)](/previous-versions/windows/silverlight/dotnet-windows-silverlight/cc838234(v=vs.95)). Hay disponibles otras bibliotecas de cliente que le permiten consumir una fuente de OData en otros tipos de aplicaciones. Para obtener más información sobre el SDK de OData, vea [el SDK de oData: código de ejemplo](https://www.odata.org/ecosystem/#sdk).
  
## <a name="in-this-section"></a>En esta sección  

 [Generar la biblioteca cliente del servicio de datos](generating-the-data-service-client-library-wcf-data-services.md)  
 Describe cómo generar una biblioteca de cliente y las clases de servicio de datos de cliente que se basan en fuentes de OData.  
  
 [Consultar el servicio de datos](querying-the-data-service-wcf-data-services.md)  
 Describe cómo consultar un servicio de datos desde una aplicación basada en .NET Framework usando bibliotecas de cliente.  
  
 [Carga de contenido diferido](loading-deferred-content-wcf-data-services.md)  
 Describe cómo cargar contenido adicional no incluido en la respuesta de la consulta inicial.  
  
 [Actualización del servicio de datos](updating-the-data-service-wcf-data-services.md)  
 Describe cómo crear, modificar y eliminar entidades y relaciones usando bibliotecas de cliente.  
  
 [Operaciones asincrónicas](asynchronous-operations-wcf-data-services.md)  
 Describe los medios proporcionados por las bibliotecas de cliente para trabajar con un servicio de datos de manera asincrónica.  
  
 [Procesamiento por lotes de operaciones](batching-operations-wcf-data-services.md)  
 Describe cómo enviar varias solicitudes al servicio de datos en un solo lote usando las bibliotecas de cliente.  
  
 [Enlazar datos a controles](binding-data-to-controls-wcf-data-services.md)  
 Describe cómo enlazar controles a una fuente de OData devuelta por un servicio de datos.  
  
 [Llamar a operaciones de servicio](calling-service-operations-wcf-data-services.md)  
 Describe cómo usar la biblioteca de cliente para llamar a operaciones de servicio.  
  
 [Administración del contexto del servicio de datos](managing-the-data-service-context-wcf-data-services.md)  
 Describe las opciones para administrar el comportamiento de la biblioteca cliente.  
  
 [Trabajar con datos binarios](working-with-binary-data-wcf-data-services.md)  
 Describe cómo obtener acceso y cambiar los datos binarios devueltos por el servicio de datos como un flujo de datos.  
  
## <a name="see-also"></a>Consulte también

- [Definir Servicios de datos de WCF](defining-wcf-data-services.md)
- [Introducción](getting-started-with-wcf-data-services.md)
