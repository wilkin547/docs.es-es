---
title: Adoptación de Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: 53f51c6a93d4768d3aa158d44cb7d20f945393f5
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964260"
---
# <a name="adopting-windows-communication-foundation"></a>Adoptación de Windows Communication Foundation

Puede optar por usar Windows Communication Foundation (WCF) para el nuevo desarrollo, mientras continúa manteniendo las aplicaciones existentes desarrolladas mediante ASP.NET. Dado que WCF pretende ser la opción más adecuada para facilitar la comunicación con las aplicaciones compiladas con la .NET Framework en cualquier escenario, puede actuar como una herramienta estándar para resolver una gran variedad de problemas de comunicación de software de forma que ASP.NET pueda.

Las nuevas aplicaciones WCF se pueden implementar en los mismos equipos que los servicios Web de ASP.NET existentes. Si los servicios Web de ASP.NET existentes usan una versión de la .NET Framework anterior a la 2,0, puede usar la herramienta de registro de IIS de ASP.NET para implementar de forma selectiva el .NET Framework 2,0 en las aplicaciones de IIS en las que se van a hospedar nuevas aplicaciones WCF. Esa herramienta está documentada en [ASP.net IIS registration Tool (Aspnet_regiis. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/k6h9cz8h(v=vs.90))y tiene una interfaz de usuario integrada en la consola de administración de IIS 6,0.

WCF se puede usar para agregar nuevas características a los servicios Web de ASP.NET existentes agregando servicios WCF configurados para ejecutarse en el modo de compatibilidad de ASP.NET a las aplicaciones de servicio Web ASP.NET existentes en IIS. Debido al modo de compatibilidad de ASP.NET, el código de los nuevos servicios WCF puede obtener acceso y actualizar la misma información de estado de la aplicación que el código ASP.NET existente, mediante el uso de la clase <xref:System.Web.HttpContext>. Las aplicaciones también pueden compartir las mismas bibliotecas de clases.

Los clientes de WCF pueden usar los servicios Web de ASP.NET. Los clientes de servicios Web ASP.NET pueden usar los servicios WCF configurados con el <xref:System.ServiceModel.BasicHttpBinding>. Los servicios Web ASP.NET pueden coexistir con aplicaciones WCF y, incluso, se puede usar WCF para agregar características a los servicios Web ASP.NET existentes. Teniendo en cuenta todos estos métodos en los que se pueden usar juntos los servicios Web WCF y ASP.NET, puede que desee migrar los servicios Web de ASP.NET a WCF solo si necesita características proporcionadas por WCF y no servicios Web de ASP.NET.

Incluso en los pocos casos en los que es necesario, la migración de código de una tecnología a otra rara vez es el enfoque correcto. El motivo para adoptar la nueva tecnología es el de cumplir nuevos requisitos que no se pueden cumplir con la tecnología anterior y, en ese caso, lo correcto sería diseñar una nueva solución que cumpla el nuevo y ampliado conjunto de requisitos. El nuevo diseño se beneficia de su experiencia con el sistema existente y de la sabiduría adquirida desde que se diseñó el sistema. El nuevo diseño también puede utilizar las funciones completas de las nuevas tecnologías en lugar de reproducir el diseño anterior en la nueva plataforma. Después de crear prototipos de elementos clave del nuevo diseño, se hace más fácil reutilizar código del sistema existente dentro del nuevo.

## <a name="see-also"></a>Vea también

- [Recuperación de los metadatos e implementación de un servicio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
