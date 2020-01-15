---
title: Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: 1600a398ac250f015f2a1d9aa4ae2d808c593b95
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2020
ms.locfileid: "75963566"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas
Los servicios web ASP.NET desarrollados para crear aplicaciones que envían y reciben mensajes mediante el Protocolo simple de acceso a objetos (SOAP) sobre HTTP. La estructura de los mensajes se puede definir mediante un Esquema XML y una herramienta se proporciona para facilitar la serialización de los mensajes a y desde los objetos de .NET Framework. La tecnología puede generar automáticamente los metadatos para describir los servicio web en el Lenguaje de descripción de servicios Web (WSDL) y se proporciona una segunda herramienta para generar clientes para los servicios web desde WSDL.  
  
 WCF es para permitir que las aplicaciones .NET Framework intercambien mensajes con otras entidades de software. Se utiliza SOAP de forma predeterminada, pero los mensajes pueden estar en cualquier formato y se pueden transmitir con cualquier protocolo de transporte. La estructura de los mensajes se puede definir mediante un Esquema XML y hay varios opciones para serializar los mensajes a y desde objetos de .NET Framework. WCF puede generar automáticamente metadatos para describir las aplicaciones compiladas con la tecnología en WSDL, y también proporciona una herramienta para generar clientes para esas aplicaciones desde WSDL.  
  
 Los estándares admitidos por los servicios Web de ASP.NET están documentados en [ventajas de los servicios Web XML creados con ASP.net](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0859ebft(v=vs.100)). La lista más amplia de estándares admitidos por WCF se enumera en [protocolos de servicios Web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## <a name="see-also"></a>Vea también

- [Comparación de los servicios web ASP.NET con el WCF basado en desarrollo](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
