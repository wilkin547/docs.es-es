---
ms.openlocfilehash: 9500907c6a1ba5b27008dcad4c9b47aef9092106
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760684"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>El fondo de RibbonGroup se establece en transparente en las compilaciones localizadas

|   |   |
|---|---|
|Detalles|El fondo de <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> en las compilaciones localizadas siempre se pinta con el pincel transparente, lo que produce una experiencia de interfaz de usuario deficiente. Esto se corrigió en WPF en .NET Framework 4.7 mediante la actualización de los recursos localizados para <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> lo que, a su vez, garantiza que se seleccione el pincel correcto.|
|Sugerencia|Actualizar a .NET Framework 4.7|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución|

