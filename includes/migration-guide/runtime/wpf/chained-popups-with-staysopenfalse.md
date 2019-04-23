---
ms.openlocfilehash: 22c4b61b293ac2366cae1dc73e0f6805a4a5fb8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805108"
---
### <a name="chained-popups-with-staysopenfalse"></a>Menús emergentes encadenados con StaysOpen=False

|   |   |
|---|---|
|Detalles|Se supone que un menú emergente con StaysOpen=False se cierra al hacer clic fuera de la ventana emergente. Cuando se encadenaban dos o más de estos elementos Popup (es decir, uno contiene al otro), se producían muchos problemas, incluidos los siguientes:<ul><li>Se abren dos niveles, se hace clic fuera de P2 pero dentro de P1.  No sucede nada.</li><li>Se abren dos niveles, se hace clic fuera de P1.  Los dos menús emergentes se cierran.</li><li>Se abren y se cierran dos niveles.  Después, se intenta volver a abrir P2.  No sucede nada.</li><li>Se intenta abrir tres niveles.  No se puede.  (No sucede nada o se cierra el primero de los dos niveles, en función de dónde se hizo clic). Estos casos (y otras variantes) ahora funcionan según lo esperado.</li></ul>|
|Ámbito|Borde|
|Versión|4.7.1|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType></li></ul>|
