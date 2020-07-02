---
ms.openlocfilehash: 3e4a5936bbac4e77efc5f7e68b55ddf49bae5d43
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614716"
---
### <a name="path-colon-checks-are-stricter"></a>Las comprobaciones de dos puntos de ruta de acceso son más estrictas

#### <a name="details"></a>Detalles

En .NET Framework 4.6.2, se realizaron varios cambios para admitir las rutas de acceso que anteriormente no eran compatibles (tanto en longitud como en formato). Se aumentó la corrección de las comprobaciones de sintaxis adecuada del separador de unidad (dos puntos), que tenía el efecto secundario de bloquear algunas rutas de acceso de URI en algunas API de ruta concretas en las que antes se toleraban.

#### <a name="suggestion"></a>Sugerencia

Si se pasa un URI a las API afectadas, modifique la cadena para que primero sea una ruta de acceso válida.<ul><li>Quite manualmente el esquema de las direcciones URL (por ejemplo, quite `file://`).

- Pase el URI a la clase <xref:System.Uri> y use <xref:System.Uri.LocalPath>.

Como alternativa, puede rechazar la nueva normalización de la ruta de acceso si establece el conmutador `Switch.System.IO.UseLegacyPathHandling` de AppContext en true.

| Nombre    | Valor       |
|:--------|:------------|
| Ámbito   | Borde        |
| Versión | 4.6.2       |
| Tipo    | Redestinación |

#### <a name="affected-apis"></a>API afectadas

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
