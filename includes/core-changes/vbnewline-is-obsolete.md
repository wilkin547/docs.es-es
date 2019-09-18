---
ms.openlocfilehash: 2a0ebcf61fd96df6d2235962c1f1e9cac3fb22e6
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988498"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine está obsoleto

La constante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> está marcada con el atributo [Obsolete](xref:System.ObsoleteAttribute) en .NET Framework, pero faltaba el atributo en la biblioteca de .NET Core 3.0.

#### <a name="version-introduced"></a>Versión introducida

.NET Core 3.0 (versión preliminar 8)

#### <a name="details"></a>Detalles

A partir de .NET Core 3.0 (versión preliminar 8), se ha aplicado el atributo [Obsolete](xref:System.ObsoleteAttribute) a la constante <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> para ajustarse a la constante `vbNewLine` en .NET Framework. El uso de la constante `vbNewLine` genera una advertencia del compilador. 

En versiones anteriores de .NET Core, `vbNewLine` no producía una advertencia del compilador.

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

-- >

