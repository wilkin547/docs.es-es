---
ms.openlocfilehash: eef5633ec8566f6d5216b7dca4387766cacb600d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620662"
---
### <a name="netdatacontractserializer-fails-to-deserialize-a-concurrentdictionary-serialized-with-a-different-net-version"></a>NetDataContractSerializer no puede deserializar un elemento ConcurrentDictionary serializado con otra versión de .NET

#### <a name="details"></a>Detalles

Por diseño, solo se puede usar <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> si los extremos de serialización y de deserialización comparten los mismos tipos CLR. Por tanto, no se garantiza que un objeto serializado con una versión de .NET Framework se pueda deserializar con otra versión. <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> es un tipo conocido por no deserializarse correctamente si se serializó con .NET Framework 4.5 o versiones anteriores, y se deserializó con .NET Framework 4.5.1 o versiones posteriores.

#### <a name="suggestion"></a>Sugerencia

Hay una serie de soluciones posibles para este problema:<ul><li>Actualice el equipo que realiza la serialización para usar .NET Framework 4.5.1 también.</li><li>Use <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> en lugar de <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> dado que no espera los mismos tipos CLR exactos en los extremos de serialización y deserialización.</li><li>Use <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> en lugar de <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> dado que no muestra esta interrupción determinada de 4.5-&gt;4.5.1.</li></ul>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5.1|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li></ul>|
