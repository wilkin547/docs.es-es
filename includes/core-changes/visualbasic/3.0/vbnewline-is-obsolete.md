---
ms.openlocfilehash: 535a73c6b748166a1e4a4661a6bab0671c653278
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721411"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine está obsoleto

La constante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> está marcada como [\[obsoleta\]](xref:System.ObsoleteAttribute) a partir de .NET Core 3.0 (versión preliminar 8).

#### <a name="version-introduced"></a>Versión introducida

3.0 (versión preliminar 8)

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET Core 3.0 (versión preliminar 8), se ha aplicado el atributo [Obsolete](xref:System.ObsoleteAttribute) a la constante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>. El uso de la constante genera una advertencia del compilador. En .NET Framework y versiones anteriores de .NET Core, no estaba marcada como obsoleta.

Este cambio se realizó para admitir Visual Basic como lenguaje para el desarrollo multiplataforma. La constante <xref:Microsoft.VisualBasic.Constants.vbNewLine> equivale a `\r\n`, la secuencia de caracteres de nueva línea en Windows. En los sistemas basados en Unix, el carácter de nueva línea es `\n`.

#### <a name="recommended-action"></a>Acción recomendada

El mensaje del atributo [Obsolete](xref:System.ObsoleteAttribute) para <xref:Microsoft.VisualBasic.Constants.vbNewLine> incluye la siguiente recomendación:

Para un retorno de carro y un avance de línea, use <xref:Microsoft.VisualBasic.Constants.vbCrLf>. Para la nueva línea de la plataforma actual, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.

#### <a name="category"></a>Categoría

Visual Basic

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

#### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
