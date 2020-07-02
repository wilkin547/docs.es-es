---
ms.openlocfilehash: 5a3370e71488e4f9d8d933b504d1d771c78e0385
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620659"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a>SoapFormatter no puede deserializar elementos Hashtable ni otros objetos de colecciones ordenados similares

#### <a name="details"></a>Detalles

<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> no garantiza que los objetos serializados en una versión de .NET Framework se deserialicen correctamente en otra versión. En concreto, en algunas colecciones ordenadas (como <xref:System.Collections.Hashtable?displayProperty=fullName>) se agregaron miembros entre las versiones 4.0 y 4.5, de modo que los objetos de estos tipos no se pueden deserializar con .NET Framework 4.0 si se serializaron con .NET Framework 4.5. Si los datos se serializaron y deserializaron con la misma versión de .NET Framework, no ocurrirá ningún problema.

#### <a name="suggestion"></a>Sugerencia

La serialización de <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> se debe reemplazar por la de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> o <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> para que sea resistente a los cambios de .NET Framework.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
