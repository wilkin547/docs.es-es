---
ms.openlocfilehash: e476039ff9c8d33f54a2f7e4371dc09a3be557c7
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237458"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine está obsoleto

La constante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> está marcada con el atributo [Obsolete](xref:System.ObsoleteAttribute) a partir de .NET Core 3.0 (versión preliminar 8).

#### <a name="version-introduced"></a>Versión introducida

3.0 (versión preliminar 8)

#### <a name="change-description"></a>Descripción del cambio

A partir de .NET Core 3.0 (versión preliminar 8), se ha aplicado el atributo [Obsolete](xref:System.ObsoleteAttribute) a la constante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>. El uso de la constante genera una advertencia del compilador. En versiones anteriores de .NET Core y .NET Framework, no estaba marcada como “Obsolete”.

Este cambio se realizó para admitir Visual Basic como lenguaje para el desarrollo multiplataforma. La constante `vbNewLine` equivale a `\r\n`, la secuencia de caracteres de nueva línea en Windows. En los sistemas basados en Unix, el carácter de nueva línea es `\n`.
 
#### <a name="recommended-action"></a>Acción recomendada

El mensaje del atributo [Obsolete](xref:System.ObsoleteAttribute) para `vbNewLine` incluye la siguiente recomendación:

> Para un retorno de carro y un avance de línea, use [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf). Para la nueva línea de la plataforma actual, use <xref:System.Environment.NewLine?displayProperty=nameWithType>.

#### <a name="category"></a>Categoría

Visual Basic

#### <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
