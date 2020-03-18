---
ms.openlocfilehash: a51738fa75ba2dd4574549fce2570df8231c4cae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859236"
---
### <a name="path-colon-checks-are-stricter"></a>Las comprobaciones de dos puntos de ruta de acceso son más estrictas

|   |   |
|---|---|
|Detalles|En .NET Framework 4.6.2, se realizaron varios cambios para admitir las rutas de acceso que anteriormente no eran compatibles (tanto en longitud como en formato). Se aumentó la corrección de las comprobaciones de sintaxis adecuada del separador de unidad (dos puntos), que tenía el efecto secundario de bloquear algunas rutas de acceso de URI en algunas API de ruta concretas en las que antes se toleraban.|
|Sugerencia|Si se pasa un URI a las API afectadas, modifique la cadena para que primero sea una ruta de acceso válida.<ul><li>Quite manualmente el esquema de las direcciones URL (por ejemplo, quite <code>file://</code>).</li><li>Pase el URI a la clase <xref:System.Uri> y use <xref:System.Uri.LocalPath>.</li></ul>Como alternativa, puede rechazar la nueva normalización de la ruta de acceso si establece el conmutador <code>Switch.System.IO.UseLegacyPathHandling</code> de AppContext en true.|
|Ámbito|Borde|
|Versión|4.6.2|
|Tipo|Redestinación|
|API afectadas|<ul><li><xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType></li><li><xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType></li></ul>|
