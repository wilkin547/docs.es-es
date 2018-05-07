---
title: Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: 60f2e9ccbfd5dbf205f3ed570ece1d4169f21e3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>Comparación de los servicios web ASP.NET con WCF basado en el propósito y las normas utilizadas
Los servicios web ASP.NET desarrollados para crear aplicaciones que envían y reciben mensajes mediante el Protocolo simple de acceso a objetos (SOAP) sobre HTTP. La estructura de los mensajes se puede definir mediante un Esquema XML y una herramienta se proporciona para facilitar la serialización de los mensajes a y desde los objetos de .NET Framework. La tecnología puede generar automáticamente los metadatos para describir los servicio web en el Lenguaje de descripción de servicios Web (WSDL) y se proporciona una segunda herramienta para generar clientes para los servicios web desde WSDL.  
  
 WCF es para permitir que las aplicaciones de .NET Framework intercambiar mensajes con otras entidades de software. Se utiliza SOAP de forma predeterminada, pero los mensajes pueden estar en cualquier formato y se pueden transmitir con cualquier protocolo de transporte. La estructura de los mensajes se puede definir mediante un Esquema XML y hay varios opciones para serializar los mensajes a y desde objetos de .NET Framework. WCF puede generar automáticamente metadatos para describir aplicaciones compiladas con tecnología de WSDL, y también proporciona una herramienta para generar clientes para esas aplicaciones desde WSDL.  
  
 Los estándares admitidos por los servicios Web ASP.NET se documentan en [servicios Web XML creados con ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94872). La lista más amplia de estándares admitidos por WCF se enumeran en [protocolos de servicios Web admitidos por los enlaces de interoperabilidad proporcionados](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## <a name="see-also"></a>Vea también  
 [Comparación de los servicios web ASP.NET con el WCF basado en desarrollo](../../../../docs/framework/wcf/feature-details/comparing-aspnet-web-services-to-wcf-based-on-development.md)
