---
ms.openlocfilehash: 480cbdecd681408a7e1d6fa366e3f1a4b131ab42
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857506"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a>Ahora se admiten las categorías de la versión 8.0 del estándar Unicode

|   |   |
|---|---|
|Detalles|En .NET Framework 4.6.2, los datos Unicode se han actualizado de la versión 6.3 del estándar Unicode a la versión 8.0.  Al solicitar las categorías de caracteres Unicode en .NET Framework 4.6.2, es posible que algunos de los resultados no coincidan con los de versiones anteriores de .NET Framework.  Este cambio afecta principalmente a las sílabas cheroquis y a las marcas de tono y signos de vocal Nuevo Tai Lue.|
|Sugerencia|Revise el código y quite o cambie la lógica que depende de categorías de caracteres Unicode codificados de forma rígida.|
|Ámbito|Secundaria|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|

