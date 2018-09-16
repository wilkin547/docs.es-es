---
title: Adoptación de Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: 5773d2687eb06cfc562dbe25fa9b94864b1b3a49
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45676605"
---
# <a name="adopting-windows-communication-foundation"></a>Adoptación de Windows Communication Foundation

Puede usar Windows Communication Foundation (WCF) para el nuevo desarrollo, mientras continúa manteniendo las aplicaciones existentes desarrolladas mediante ASP.NET. Como WCF está diseñada para ser la opción más adecuada para facilitar la comunicación con las aplicaciones compiladas con .NET Framework en cualquier escenario, puede actuar como una herramienta estándar para resolver una gran variedad de problemas de comunicaciones de software de manera que ASP.NET no se puede.

Nuevas aplicaciones de WCF se pueden implementar en las mismas máquinas como servicios Web ASP.NET existentes. Si los servicios Web ASP.NET existentes utilizan una versión de .NET Framework anteriores a la versión 2.0, puede usar la herramienta de registro de IIS de ASP.NET para implementar selectivamente la versión 2.0 de .NET Framework a las aplicaciones de IIS en el que nuevas aplicaciones de WCF son hospedarse. Esa herramienta se documenta en [herramienta de registro de IIS de ASP.NET (Aspnet_regiis.exe)](https://go.microsoft.com/fwlink/?LinkId=94687), y ha creado una interfaz de usuario en la consola de administración de IIS 6.0.

WCF se puede usar para agregar nuevas características a los servicios Web ASP.NET existentes agregando servicios WCF configurados para ejecutarse en modo de compatibilidad ASP.NET para aplicaciones de servicio Web ASP.NET existentes en IIS. Debido a modo de compatibilidad ASP.NET, el código para los nuevos servicios WCF puede tener acceso y actualizar la misma información de estado de aplicación que el código ASP.NET preexistente, mediante la <xref:System.Web.HttpContext> clase. Las aplicaciones también pueden compartir las mismas bibliotecas de clases.

Los clientes WCF pueden usar los servicios Web ASP.NET. Los servicios WCF que se configuran con el <xref:System.ServiceModel.BasicHttpBinding> puede usarse por los clientes de servicios Web de ASP.NET. Los servicios Web ASP.NET pueden coexistir con aplicaciones WCF y WCF incluso se puede usar para agregar características a los servicios Web de ASP.NET existentes. Dadas todas estas maneras en que se pueden usar conjuntamente servicios Web de ASP.NET y WCF, es posible que desee migrar los servicios Web ASP.NET a WCF solo si necesita características proporcionadas por WCF y servicios Web de ASP.NET no.

Incluso en los pocos casos donde es necesario, migrar código de una tecnología a otra rara vez es el enfoque correcto. El motivo para adoptar la nueva tecnología es el de cumplir nuevos requisitos que no se pueden cumplir con la tecnología anterior y, en ese caso, lo correcto sería diseñar una nueva solución que cumpla el nuevo y ampliado conjunto de requisitos. El nuevo diseño se beneficia de su experiencia con el sistema existente y de la sabiduría adquirida desde que se diseñó el sistema. El nuevo diseño también puede utilizar las funciones completas de las nuevas tecnologías en lugar de reproducir el diseño anterior en la nueva plataforma. Después de crear prototipos de elementos clave del nuevo diseño, se hace más fácil reutilizar código del sistema existente dentro del nuevo.

## <a name="see-also"></a>Vea también

- [Recuperación de los metadatos e implementación de un servicio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
