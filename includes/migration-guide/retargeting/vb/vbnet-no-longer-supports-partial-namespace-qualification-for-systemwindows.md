---
ms.openlocfilehash: cef8096c971da8ae245ff974697022f350cb9195
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616072"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a>VB.NET ya no admite la calificación de espacios de nombres parciales para las API de System.Windows

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5.2, los proyectos de VB.NET ya no pueden especificar API de System.Windows con espacios de nombres parciales. Por ejemplo, se producirá un error al hacer referencia a `Windows.Forms.DialogResult`. En su lugar, el código debe hacer referencia al nombre completo (<xref:System.Windows.Forms.DialogResult>) o importar el espacio de nombres específico y simplemente hacer referencia a <xref:System.Windows.Forms.DialogResult?displayProperty=fullName>.

#### <a name="suggestion"></a>Sugerencia

Debería actualizarse el código para hacer referencia a las API `System.Windows` con nombres simples (e importar el espacio de nombres correspondiente) o con nombres completos.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   | Secundaria       |
| Versión | 4.5.2       |
| Tipo    | Redestinación |
