---
title: 'Serialización: .NET'
description: En este artículo se proporciona información sobre las tecnologías de serialización de .NET, incluidas la serialización binaria, la serialización de SOAP y XML, y la serialización de JSON.
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: b3d76c14dc9180a5f19781122d1a42bcae603e76
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "85840343"
---
# <a name="serialization-in-net"></a>Serialización en .NET

La serialización es el proceso de convertir el estado de un objeto en un formato que se pueda almacenar o transportar. El complemento de serialización es deserialización, que convierte una secuencia en un objeto. Juntos, estos procesos permiten almacenar y transferir datos.  
  
.NET incluye las siguientes tecnologías de serialización:  
  
- La [serialización binaria](binary-serialization.md) preserva la fidelidad de tipo, lo que es útil para conservar el estado de un objeto entre distintas invocaciones de una aplicación. Por ejemplo, puede compartir un objeto entre distintas aplicaciones si lo serializa en el Portapapeles. Puede serializar un objeto en una secuencia, un disco, la memoria, a través de la red, etc. La comunicación remota utiliza la serialización para pasar objetos "por valor" de un equipo o dominio de aplicación a otro.  
  
- La [serialización de SOAP y XML](xml-and-soap-serialization.md) solo serializa propiedades y campos públicos y no preserva la fidelidad de tipo. Esto es útil si se desea proporcionar o utilizar los datos sin restringir la aplicación que utiliza los datos. Dado que XML es un estándar abierto, es una opción atractiva para compartir los datos por el web. SOAP es igualmente un estándar abierto, que lo convierte en una opción atractiva.  
  
- La [serialización de JSON](system-text-json-overview.md) solo serializa propiedades públicas y no preserva la fidelidad de tipo. JSON es un estándar abierto que constituye una opción atractiva para compartir datos en Internet.

## <a name="reference"></a>Referencia

<xref:System.Runtime.Serialization>  
Contiene clases que se pueden usar para serializar y deserializar objetos.
  
<xref:System.Xml.Serialization>  
Contiene clases que se pueden utilizar para serializar objetos en documentos o secuencias de formato XML.

<xref:System.Text.Json>  
Contiene clases que se pueden usar para serializar objetos en documentos o secuencias de formato JSON.
