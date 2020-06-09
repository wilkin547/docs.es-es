---
title: Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: b27f3516868ec70319ce37fbbd774a29347b0bc8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597584"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas
Los servicios web ASP.NET desarrollados para crear aplicaciones que envían y reciben mensajes mediante el Protocolo simple de acceso a objetos (SOAP) sobre HTTP. La estructura de los mensajes se puede definir mediante un Esquema XML y una herramienta se proporciona para facilitar la serialización de los mensajes a y desde los objetos de .NET Framework. La tecnología puede generar automáticamente los metadatos para describir los servicio web en el Lenguaje de descripción de servicios Web (WSDL) y se proporciona una segunda herramienta para generar clientes para los servicios web desde WSDL.  
  
 WCF es para permitir que las aplicaciones .NET Framework intercambien mensajes con otras entidades de software. Se utiliza SOAP de forma predeterminada, pero los mensajes pueden estar en cualquier formato y se pueden transmitir con cualquier protocolo de transporte. La estructura de los mensajes se puede definir mediante un Esquema XML y hay varios opciones para serializar los mensajes a y desde objetos de .NET Framework. WCF puede generar automáticamente metadatos para describir las aplicaciones compiladas con la tecnología en WSDL, y también proporciona una herramienta para generar clientes para esas aplicaciones desde WSDL.  
  
 Los estándares admitidos por los servicios Web de ASP.NET están documentados en [ventajas de los servicios Web XML creados con ASP.net](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0859ebft(v=vs.100)). La lista más amplia de estándares admitidos por WCF se enumera en [protocolos de servicios Web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## <a name="see-also"></a>Vea también

- [Comparación de los servicios web ASP.NET con el WCF basado en desarrollo](comparing-aspnet-web-services-to-wcf-based-on-development.md)
