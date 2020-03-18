---
ms.openlocfilehash: 8db115a46df3fcea103e8fa6896542d0116aa256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804683"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>VB.NET ya no admite la calificación de espacios de nombres parciales para las API de System.Windows

|   |   |
|---|---|
|Detalles|A partir de .NET Framework 4.5.2, los proyectos de VB.NET ya no pueden especificar API de System.Windows con espacios de nombres parciales. Por ejemplo, se producirá un error al hacer referencia a <code>Windows.Forms.DialogResult</code>. En su lugar, el código debe hacer referencia al nombre completo (<xref:System.Windows.Forms.DialogResult>) o importar el espacio de nombres específico y simplemente hacer referencia a <xref:System.Windows.Forms.DialogResult?displayProperty=name>.|
|Sugerencia|Debería actualizarse el código para hacer referencia a las API <code>System.Windows</code> con nombres simples (e importar el espacio de nombres correspondiente) o con nombres completos.|
|Ámbito|Secundaria|
|Versión|4.5.2|
|Tipo|Redestinación|
