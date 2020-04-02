---
title: Serialización de SOAP y XML
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: dcb2ed1703473be582a12f430d2e051d8a420230
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588374"
---
# <a name="xml-and-soap-serialization"></a>Serialización de XML y SOAP

La serialización XML convierte (serializa) los campos públicos y las propiedades de un objeto, así como los parámetros y valores devueltos de los métodos, en una secuencia XML que se ajusta a un documento de lenguaje de definición de esquemas XML (XSD) específico. La serialización XML produce clases fuertemente tipadas cuyas propiedades y campos se convierten en un formato en serie (en este caso, a XML) para almacenaje y transporte.

Dado que XML es un estándar abierto, cualquier aplicación, según sea necesario, puede procesar la secuencia XML sin tener en cuenta la plataforma. Por ejemplo, los servicios Web XML creados utilizando el ASP.NET utilizan la clase <xref:System.Xml.Serialization.XmlSerializer> para crear secuencias XML que pasan los datos entre las aplicaciones de servicio Web XML a lo largo de Internet o en intranets. A la inversa, la deserialización toma este tipo de secuencia XML y reconstruye el objeto.

La serialización XML también se puede usar para serializar objetos en secuencias XML que se ajustan a la especificación SOAP. SOAP es un protocolo basado en XML, diseñado específicamente para transportar llamadas a procedimiento utilizando XML.

Para serializar o deserializar objetos utilice la clase <xref:System.Xml.Serialization.XmlSerializer>. Para crear las clases que se van a serializar, utilice la herramienta XML Schema Definition.

## <a name="see-also"></a>Vea también

- [Serialización binaria](binary-serialization.md)
- [Servicios Web XML creados con clientes de ASP.NET y servicios Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))
