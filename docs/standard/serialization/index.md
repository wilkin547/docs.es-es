---
title: 'Serialización: .NET'
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: e6db24326c79ab6509b253c45c27f87a2aacd73c
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053348"
---
# <a name="serialization-in-net"></a>Serialización en .NET

La serialización es el proceso de convertir el estado de un objeto en un formato que se pueda almacenar o transportar. El complemento de serialización es deserialización, que convierte una secuencia en un objeto. Juntos, estos procesos permiten almacenar y transferir datos.  
  
.NET incluye las siguientes tecnologías de serialización:  
  
- La [serialización binaria](binary-serialization.md) conserva la fidelidad de tipos, lo que resulta útil para conservar el estado de un objeto entre las distintas invocaciones de una aplicación. Por ejemplo, puede compartir un objeto entre distintas aplicaciones si lo serializa en el Portapapeles. Puede serializar un objeto en una secuencia, un disco, la memoria, a través de la red, etc. La comunicación remota utiliza la serialización para pasar objetos "por valor" de un equipo o dominio de aplicación a otro.  
  
- La [serialización XML y SOAP](xml-and-soap-serialization.md) solo serializa propiedades y campos públicos y no conserva la fidelidad de tipos. Esto es útil si se desea proporcionar o utilizar los datos sin restringir la aplicación que utiliza los datos. Dado que XML es un estándar abierto, es una opción atractiva para compartir los datos por el web. SOAP es igualmente un estándar abierto, que lo convierte en una opción atractiva.  
  
- La [serialización de JSON](system-text-json-overview.md) solo serializa las propiedades públicas y no conserva la fidelidad de tipos. JSON es un estándar abierto que es una opción atractiva para compartir datos a través de Internet.

## <a name="reference"></a>Referencia

<xref:System.Runtime.Serialization>  
Contiene clases que se pueden usar para serializar y deserializar objetos.
  
<xref:System.Xml.Serialization>  
Contiene clases que se pueden utilizar para serializar objetos en documentos o secuencias de formato XML.

<xref:System.Text.Json>  
Contiene clases que se pueden usar para serializar objetos en documentos o secuencias de formato JSON.
