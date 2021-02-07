---
description: Más información acerca de la comparación de los servicios Web de ASP.NET con WCF basado en el propósito y los estándares usados
title: Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: debc20f3ab3e8e9f83641eaa7d3b52dabe82055c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743452"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas

Los servicios web ASP.NET desarrollados para crear aplicaciones que envían y reciben mensajes mediante el Protocolo simple de acceso a objetos (SOAP) sobre HTTP. La estructura de los mensajes se puede definir mediante un Esquema XML y una herramienta se proporciona para facilitar la serialización de los mensajes a y desde los objetos de .NET Framework. La tecnología puede generar automáticamente los metadatos para describir los servicio web en el Lenguaje de descripción de servicios Web (WSDL) y se proporciona una segunda herramienta para generar clientes para los servicios web desde WSDL.  
  
 WCF es para permitir que las aplicaciones .NET Framework intercambien mensajes con otras entidades de software. Se utiliza SOAP de forma predeterminada, pero los mensajes pueden estar en cualquier formato y se pueden transmitir con cualquier protocolo de transporte. La estructura de los mensajes se puede definir mediante un Esquema XML y hay varios opciones para serializar los mensajes a y desde objetos de .NET Framework. WCF puede generar automáticamente metadatos para describir las aplicaciones compiladas con la tecnología en WSDL, y también proporciona una herramienta para generar clientes para esas aplicaciones desde WSDL.  
  
 Los estándares admitidos por los servicios Web de ASP.NET están documentados en [ventajas de los servicios Web XML creados con ASP.net](/previous-versions/dotnet/netframework-4.0/0859ebft(v=vs.100)). La lista más amplia de estándares compatibles con WCF se enumeran en [protocolos de servicios Web compatibles con los enlaces de interoperabilidad de System-Provided](web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## <a name="see-also"></a>Vea también

- [Comparación de los servicios web ASP.NET con el WCF basado en desarrollo](comparing-aspnet-web-services-to-wcf-based-on-development.md)
