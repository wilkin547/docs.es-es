---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59236093"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>El fondo de RibbonGroup se establece en transparente en las compilaciones localizadas

|   |   |
|---|---|
|Detalles|El fondo de <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> en las compilaciones localizadas siempre se pinta con el pincel transparente, lo que produce una experiencia de interfaz de usuario deficiente. Esto se corrigió en WPF en .NET Framework 4.7 mediante la actualización de los recursos localizados para <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> lo que, a su vez, garantiza que se seleccione el pincel correcto.|
|Sugerencia|Actualizar a .NET Framework 4.7|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución|
