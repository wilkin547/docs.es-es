---
title: Serialización de SOAP y XML
description: En esta introducción se describe la serialización XML, que también se puede usar para serializar objetos en secuencias XML que se ajustan a la especificación SOAP.
ms.date: 03/30/2017
helpviewer_keywords:
- SOAP, XML serialization
- XML serialization, SOAP
- serialization, SOAP
- serialization, about serialization
- XML serialization
- serialization
ms.assetid: 832ac524-21bc-419a-a27b-ca8bfc45840f
ms.openlocfilehash: f7ad7732f929ac3599942c5440b173ea226cca87
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544991"
---
# <a name="xml-and-soap-serialization"></a>Serialización de SOAP y XML

La serialización XML convierte (serializa) las propiedades y campos públicos de un objeto y los parámetros y valores devueltos de los métodos en una secuencia XML que se ajusta a un documento específico del lenguaje de definición de esquemas XML (XSD). La serialización XML produce clases fuertemente tipadas cuyas propiedades y campos se convierten en un formato en serie (en este caso, a XML) para almacenaje y transporte.

Dado que XML es un estándar abierto, cualquier aplicación, según sea necesario, puede procesar la secuencia XML sin tener en cuenta la plataforma. Por ejemplo, los servicios Web XML creados utilizando el ASP.NET utilizan la clase <xref:System.Xml.Serialization.XmlSerializer> para crear secuencias XML que pasan los datos entre las aplicaciones de servicio Web XML a lo largo de Internet o en intranets. A la inversa, la deserialización toma este tipo de secuencia XML y reconstruye el objeto.

La serialización XML también se puede usar para serializar objetos en secuencias XML que se ajustan a la especificación SOAP. SOAP es un protocolo basado en XML, diseñado específicamente para transportar llamadas a procedimiento utilizando XML.

Para serializar o deserializar objetos utilice la clase <xref:System.Xml.Serialization.XmlSerializer>. Para crear las clases que se van a serializar, utilice la herramienta XML Schema Definition.

## <a name="see-also"></a>Vea también

- [Serialización binaria](binary-serialization.md)
- [Servicios Web XML creados con ASP.NET y clientes de servicio Web XML](/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))
