---
ms.openlocfilehash: 6af8e97423c04abca25feb8d77ea9ab6e198a4f0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620629"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>Los métodos ObjectContext.Translate y ObjectContext.ExecuteStoreQuery ahora admiten el tipo enum

#### <a name="details"></a>Detalles

En .NET Framework 4.0, el parámetro genérico <code>T</code> de los métodos <code>ObjectContext.Translate</code> y <code>ObjectContext.ExecuteStoreQuery</code> no podía ser una enumeración. Ahora se admite este escenario.

#### <a name="suggestion"></a>Sugerencia

Si se llamaba a Translate o ExecuteStoreQuery en un tipo de enumeración en .NET Framework 4.0, se devolvía "0". Si este era el comportamiento deseado, las llamadas deberían reemplazarse por una constante 0 (o su tipo enum equivalente).

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
