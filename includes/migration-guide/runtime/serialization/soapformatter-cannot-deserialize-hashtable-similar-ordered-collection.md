---
ms.openlocfilehash: 6ed7438a7f6e7710fcce03c8260a1360143f8d93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235822"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>SoapFormatter no puede deserializar elementos Hashtable ni otros objetos de colecciones ordenados similares

|   |   |
|---|---|
|Detalles|<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> no garantiza que los objetos serializados en una versión de .NET Framework se deserialicen correctamente en otra versión. En concreto, en algunas colecciones ordenadas (como <xref:System.Collections.Hashtable?displayProperty=name>) se agregaron miembros entre las versiones 4.0 y 4.5, de modo que los objetos de estos tipos no se pueden deserializar con .NET Framework 4.0 si se serializaron con .NET Framework 4.5. Si los datos se serializaron y deserializaron con la misma versión de .NET Framework, no ocurrirá ningún problema.|
|Sugerencia|La serialización de <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=name> se debe reemplazar por la de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> o <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> para que sea resistente a los cambios de .NET Framework.|
|Ámbito|Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
