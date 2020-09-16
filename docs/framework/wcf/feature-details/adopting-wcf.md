---
title: Adoptación de Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 49ba71e2-9468-4082-84c5-cf8daf95e34a
ms.openlocfilehash: 40a2eac1e282640f0df70a7eca16e3b2401c0764
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546013"
---
# <a name="adopt-windows-communication-foundation"></a>Adopción de Windows Communication Foundation

Puede optar por usar Windows Communication Foundation (WCF) para el nuevo desarrollo mientras continúa manteniendo las aplicaciones existentes desarrolladas mediante ASP.NET. Dado que WCF pretende ser la opción más adecuada para facilitar la comunicación con las aplicaciones compiladas con la .NET Framework en cualquier escenario, puede actuar como una herramienta estándar para resolver una gran variedad de problemas de comunicación de software de una forma que ASP.NET no pueda.

Las nuevas aplicaciones WCF se pueden implementar en los mismos equipos que los servicios Web de ASP.NET existentes. Si los servicios Web de ASP.NET existentes usan una versión de la .NET Framework anterior a la 2,0, puede usar la herramienta de registro de IIS de ASP.NET para implementar de forma selectiva el .NET Framework 2,0 en las aplicaciones de IIS en las que se van a hospedar nuevas aplicaciones WCF. Esa herramienta está documentada en [ASP.net IIS registration Tool (Aspnet_regiis.exe)](/previous-versions/dotnet/netframework-3.5/k6h9cz8h(v=vs.90))y tiene una interfaz de usuario integrada en la consola de administración de IIS 6,0.

WCF se puede usar para agregar nuevas características a los servicios Web de ASP.NET existentes agregando servicios WCF configurados para ejecutarse en el modo de compatibilidad de ASP.NET a las aplicaciones de servicio Web ASP.NET existentes en IIS. Debido al modo de compatibilidad de ASP.NET, el código de los nuevos servicios WCF puede obtener acceso y actualizar la misma información de estado de la aplicación que el código ASP.NET existente, mediante la <xref:System.Web.HttpContext> clase. Las aplicaciones también pueden compartir las mismas bibliotecas de clases.

Los clientes de WCF pueden usar los servicios Web de ASP.NET. Los servicios WCF que se configuran con <xref:System.ServiceModel.BasicHttpBinding> pueden ser usados por los clientes del servicio Web de ASP.net. Los servicios Web ASP.NET pueden coexistir con aplicaciones WCF y, incluso, se puede usar WCF para agregar características a los servicios Web ASP.NET existentes. Teniendo en cuenta todos estos métodos en los que se pueden usar juntos los servicios Web WCF y ASP.NET, puede que desee migrar los servicios Web de ASP.NET a WCF solo si necesita características proporcionadas por WCF y no servicios Web de ASP.NET.

Incluso en los pocos casos en los que es necesario, la migración de código de una tecnología a otra rara vez es el enfoque correcto. La razón para adoptar la nueva tecnología es cumplir los nuevos requisitos que no se pueden cumplir con la tecnología anterior y, en ese caso, lo correcto es diseñar una solución nueva para cumplir con el conjunto de requisitos recién expandido. El nuevo diseño se beneficia de su experiencia con el sistema existente y de la sabiduría adquirida desde que se diseñó el sistema. El nuevo diseño también puede utilizar las funciones completas de las nuevas tecnologías en lugar de reproducir el diseño anterior en la nueva plataforma. Después de crear prototipos de elementos clave del nuevo diseño, es más fácil reutilizar el código del sistema existente en el nuevo.

## <a name="see-also"></a>Vea también

- [Procedimiento para recuperar metadatos e implementar un servicio conforme](how-to-retrieve-metadata-and-implement-a-compliant-service.md)
