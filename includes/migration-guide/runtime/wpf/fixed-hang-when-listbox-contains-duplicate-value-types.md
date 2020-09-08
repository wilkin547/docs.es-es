---
ms.openlocfilehash: 7637c2d96aef93b4cf8f2314c1dd1edba51d553c
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496581"
---
### <a name="fixed-a-hang-when-listbox-contains-duplicate-value-types"></a>Se ha corregido un bloqueo cuando ListBox contiene tipos de valores duplicados

#### <a name="details"></a>Detalles

Se ha corregido un problema por el que un elemento de virtualización<xref:System.Windows.Controls.ItemsControl> dejaba de responder durante el desplazamiento cuando la colección de elementos contenía objetos de tipo de valor duplicados.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Major|
|Versión|4.8|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
