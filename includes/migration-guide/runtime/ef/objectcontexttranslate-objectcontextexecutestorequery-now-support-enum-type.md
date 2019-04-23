---
ms.openlocfilehash: 1d2d6133683360b97569e49402e7c8c4d182b65d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805060"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>Los métodos ObjectContext.Translate y ObjectContext.ExecuteStoreQuery ahora admiten el tipo enum

|   |   |
|---|---|
|Detalles|En .NET Framework 4.0, el parámetro genérico <code>T</code> de los métodos <code>ObjectContext.Translate</code> y <code>ObjectContext.ExecuteStoreQuery</code> no podía ser una enumeración. Ahora se admite este escenario.|
|Sugerencia|Si se llamaba a Translate o ExecuteStoreQuery en un tipo de enumeración en .NET Framework 4.0, se devolvía "0". Si este era el comportamiento deseado, las llamadas deberían reemplazarse por una constante 0 (o su tipo enum equivalente).|
|Ámbito|Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
