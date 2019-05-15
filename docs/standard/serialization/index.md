---
title: Serialización en .NET
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: 1f90a128ef6b29acbd315beae7aaaf1d1b78a62b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638846"
---
# <a name="serialization-in-net"></a>Serialización en .NET
La serialización es el proceso de convertir el estado de un objeto en un formato que se pueda almacenar o transportar. El complemento de serialización es deserialización, que convierte una secuencia en un objeto. Juntos, estos procesos permiten almacenar los datos y transferirlos con facilidad.  
  
.NET cuenta con dos tecnologías de serialización:  
  
- La serialización binaria conserva fidelidad de tipo, que es útil para conservar el estado de un objeto entre las invocaciones diferentes de una aplicación. Por ejemplo, puede compartir un objeto entre distintas aplicaciones si lo serializa en el Portapapeles. Puede serializar un objeto en una secuencia, un disco, la memoria, a través de la red, etc. La comunicación remota utiliza la serialización para pasar objetos "por valor" de un equipo o dominio de aplicación a otro.  
  
- La serialización XML serializa solo propiedades públicas y campos y no conserva la fidelidad de tipo. Esto es útil si se desea proporcionar o utilizar los datos sin restringir la aplicación que utiliza los datos. Dado que XML es un estándar abierto, es una opción atractiva para compartir los datos por el web. SOAP es igualmente un estándar abierto, que lo convierte en una opción atractiva.  
  
## <a name="in-this-section"></a>En esta sección  
[Temas "Cómo…" sobre serialización](../../../docs/standard/serialization/serialization-how-to-topics.md)  
Enumera vínculos a los temas "Cómo..." incluidos en esta sección.
  
[Serialización binaria](../../../docs/standard/serialization/binary-serialization.md)  
Describe el mecanismo de la serialización binaria que está incluido con Common Language Runtime.

[Serialización SOAP y XML](../../../docs/standard/serialization/xml-and-soap-serialization.md)  
Describe el mecanismo de la serialización XML y SOAP que está incluido con Common Language Runtime.

[Herramientas de serialización](../../../docs/standard/serialization/serialization-tools.md)  
Estas herramientas ayudan a desarrollar el código de serialización.

[Ejemplos de serialización](../../../docs/standard/serialization/serialization-samples.md)  
En los ejemplos se muestra cómo hacer la serialización.

## <a name="reference"></a>Referencia
<xref:System.Runtime.Serialization> Contiene clases que se pueden usar para serializar y deserializar objetos.
  
<xref:System.Xml.Serialization>  
Contiene clases que se pueden utilizar para serializar objetos en documentos o secuencias de formato XML.
