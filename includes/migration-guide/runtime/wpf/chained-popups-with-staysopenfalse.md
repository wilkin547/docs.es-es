---
ms.openlocfilehash: 7bf5f7e8a49acc2918dd0d68a1c54a5c277091b0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497392"
---
### <a name="chained-popups-with-staysopenfalse"></a>Menús emergentes encadenados con StaysOpen=False

#### <a name="details"></a>Detalles

Se supone que un menú emergente con StaysOpen=False se cierra al hacer clic fuera de la ventana emergente. Cuando se encadenaban dos o más de estos elementos Popup (es decir, uno contiene al otro), se producían muchos problemas, incluidos los siguientes:<ul><li>Se abren dos niveles, se hace clic fuera de P2 pero dentro de P1.  No sucede nada.</li><li>Se abren dos niveles, se hace clic fuera de P1.  Los dos menús emergentes se cierran.</li><li>Se abren y se cierran dos niveles.  Después, se intenta volver a abrir P2.  No sucede nada.</li><li>Se intenta abrir tres niveles.  No se puede.  (No sucede nada o se cierra el primero de los dos niveles, en función de dónde se hizo clic). Estos casos (y otras variantes) ahora funcionan según lo esperado.</li></ul>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.7.1|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.Popup.StaysOpen`

-->
