---
ms.openlocfilehash: 02c9305a36f47dfaf0b1fa8d19b07cd2d34badae
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032120"
---
### <a name="fieldinfosetvalue-throws-exception-for-static-init-only-fields"></a>FieldInfo.SetValue produce una excepción en los campos estáticos de solo inicialización

A partir de .NET Core 3.0, se produce una excepción si intenta establecer un valor en un campo <xref:System.Reflection.FieldAttributes.InitOnly> estático al llamar a <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.

#### <a name="change-description"></a>Descripción del cambio

En .NET Framework y en versiones de .NET Core anteriores a la 3.0, podía establecer el valor de un campo estático constante una vez inicializado ([readonly en C#](~/docs/csharp/language-reference/keywords/readonly.md)) mediante una llamada a <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>. Con todo, al establecer este tipo de campo de esta manera, se producía un comportamiento imprevisible en función de la plataforma de destino y la configuración de optimización.

En .NET Core 3.0 y versiones posteriores, al llamar a <xref:System.Reflection.FieldInfo.SetValue%2A> en un campo <xref:System.Reflection.FieldAttributes.InitOnly> estático, se produce una excepción <xref:System.FieldAccessException?displayProperty=nameWithType>.

> [!TIP]
> Un campo <xref:System.Reflection.FieldAttributes.InitOnly> es uno que solo se puede establecer en el momento en que se declara o en el constructor de la clase contenedora. En otras palabras, es constante después de inicializarse.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

Inicialice los campos <xref:System.Reflection.FieldAttributes.InitOnly> estáticos en un constructor estático. Esto se aplica a los tipos dinámicos y no dinámicos.

Como alternativa, puede quitar el atributo <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> del campo y después llamar a <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)?displayProperty=nameWithType>
- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)`
- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)`

-->
