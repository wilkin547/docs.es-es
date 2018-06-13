---
title: Adoptación de Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: bcd6543e6cd47dc723b308acebec6f492fa14fb1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489136"
---
# <a name="adopting-windows-communication-foundation"></a>Adoptación de Windows Communication Foundation
Puede usar Windows Communication Foundation (WCF) para el nuevo desarrollo, mientras sigue manteniendo las aplicaciones existentes desarrolladas mediante ASP.NET. Dado que WCF está diseñado para ser la opción más adecuada para facilitar la comunicación con aplicaciones creadas con .NET Framework en cualquier escenario, puede servir como una herramienta estándar para resolver una gran variedad de problemas de comunicaciones de software de forma que ASP.NET no se puede.  
  
 Nuevas aplicaciones de WCF pueden implementarse en los mismos equipos como servicios Web ASP.NET existentes. Si los servicios Web de ASP.NET existentes utilizan una versión de .NET Framework anteriores a la versión 2.0, puede usar la herramienta de registro de IIS de ASP.NET para implementar la versión 2.0 de .NET Framework a las aplicaciones de IIS en el que son nuevas aplicaciones de WCF se hospede de manera selectiva. Dicha herramienta se documenta en [herramienta de registro de IIS de ASP.NET (Aspnet_regiis.exe)](http://go.microsoft.com/fwlink/?LinkId=94687), y ha creado una interfaz de usuario en la consola de administración de IIS 6.0.  
  
 WCF se puede utilizar para agregar nuevas características a los servicios Web ASP.NET existentes agregando los servicios WCF configurados para ejecutarse en modo de compatibilidad ASP.NET para aplicaciones de servicio Web ASP.NET existentes en IIS. Debido al modo de compatibilidad ASP.NET, el código de los nuevos servicios WCF puede obtener acceso y actualizar la misma información de estado de aplicación que el código ASP.NET preexistente, mediante el uso de la <xref:System.Web.HttpContext> clase. Las aplicaciones también pueden compartir las mismas bibliotecas de clases.  
  
 Los clientes WCF pueden usar los servicios Web ASP.NET. Los servicios WCF que se configuran con el <xref:System.ServiceModel.BasicHttpBinding> puede utilizarse por clientes de servicios Web de ASP.NET. Los servicios Web ASP.NET pueden coexistir con aplicaciones WCF y WCF se puede utilizar incluso para agregar características a los servicios Web de ASP.NET existentes. Dadas todas estas maneras en que los servicios Web de ASP.NET y WCF se pueden utilizar conjuntamente, puede que desee migrar los servicios Web ASP.NET a WCF solo si necesita características que proporcionan servicios de WCF y no Web de ASP.NET.  
  
 Incluso en los pocos casos donde es necesario, considere cuidadosamente que migrar código de una tecnología a otra pocas veces es el enfoque correcto. El motivo para adoptar la nueva tecnología es el de cumplir nuevos requisitos que no se pueden cumplir con la tecnología anterior y, en ese caso, lo correcto sería diseñar una nueva solución que cumpla el nuevo y ampliado conjunto de requisitos. El nuevo diseño se beneficia de su experiencia con el sistema existente y de la sabiduría adquirida desde que se diseñó el sistema. El nuevo diseño también puede utilizar las funciones completas de las nuevas tecnologías en lugar de reproducir el diseño anterior en la nueva plataforma. Después de crear prototipos de elementos clave del nuevo diseño, se hace más fácil reutilizar código del sistema existente dentro del nuevo.  
  
 Para los pocos casos donde el traslado de los servicios Web ASP.NET a WCF es la solución correcta, la siguiente sección proporciona alguna orientación sobre cómo proceder. Hay consejos sobre cómo migrar servicios y cómo migrar clientes.  
  
 Para obtener un análisis completo sobre cómo migrar los servicios Web ASP.NET existentes a WCF vea [servicios Web ASP.NET y Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkID=71761). En esta sección se describe cómo implementar un servicio WCF conforme a partir de los metadatos para su servicio Web ASP.NET y cómo migrar código de cliente y del servicio Web de ASP.NET a WCF.  
  
## <a name="see-also"></a>Vea también  
 [Recuperación de los metadatos e implementación de un servicio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)  
 [Migración del código del servicio web ASP.NET a Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-to-wcf.md)  
 [Migración del código de cliente de servicio web ASP.NET a Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
