---
ms.openlocfilehash: a20fad5f9c95e59c14ffd91f4921cf8bfab443cd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621374"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a>Ahora se admiten las categorías de la versión 8.0 del estándar Unicode

#### <a name="details"></a>Detalles

En .NET Framework 4.6.2, los datos Unicode se han actualizado de la versión 6.3 del estándar Unicode a la versión 8.0.  Al solicitar las categorías de caracteres Unicode en .NET Framework 4.6.2, es posible que algunos de los resultados no coincidan con los de versiones anteriores de .NET Framework.  Este cambio afecta principalmente a las sílabas cheroquis y a las marcas de tono y signos de vocal Nuevo Tai Lue.

#### <a name="suggestion"></a>Sugerencia

Revise el código y quite o cambie la lógica que depende de categorías de caracteres Unicode codificados de forma rígida.

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
