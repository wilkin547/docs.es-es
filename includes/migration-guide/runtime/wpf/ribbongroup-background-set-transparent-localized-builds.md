---
ms.openlocfilehash: 9500907c6a1ba5b27008dcad4c9b47aef9092106
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802458"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>El fondo de RibbonGroup se establece en transparente en las compilaciones localizadas

|   |   |
|---|---|
|Detalles|El fondo de <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> en las compilaciones localizadas siempre se pinta con el pincel transparente, lo que produce una experiencia de interfaz de usuario deficiente. Esto se corrigió en WPF en .NET Framework 4.7 mediante la actualización de los recursos localizados para <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> lo que, a su vez, garantiza que se seleccione el pincel correcto.|
|Sugerencia|Actualizar a .NET Framework 4.7|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Tiempo de ejecución|

