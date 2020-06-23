---
ms.openlocfilehash: aab7d8538c875e35c832acc2a6c64beb84d4fb47
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702456"
---
### <a name="winforms-methods-now-throw-argumentexception"></a>Los métodos de WinForms inician ahora la excepción ArgumentException

Algunos métodos de Windows Forms inician ahora una excepción <xref:System.ArgumentException> en los argumentos no válidos, donde antes no lo hacían.

#### <a name="change-description"></a>Descripción del cambio

Anteriormente, al pasar argumentos de un tipo inesperado o incorrecto a ciertos métodos de Windows Forms se originaba un estado indeterminado. A partir de .NET 5.0, estos métodos inician una excepción <xref:System.ArgumentException> cuando se pasan argumentos no válidos.

El inicio de una <xref:System.ArgumentException> se ajusta al comportamiento del tiempo de ejecución de .NET. También mejora la experiencia de depuración al comunicar claramente qué argumento no es válido.

En la tabla siguiente se enumeran los métodos y parámetros afectados:

| Método | Nombre de parámetro | Condición | Versión agregada |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | El argumento no es del tipo <xref:System.Windows.Forms.TabPage>. | 5.0 (versión preliminar 1) |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | El argumento es `null`, <xref:System.String.Empty?displayProperty=nameWithType> o un espacio en blanco. | 5.0 (versión preliminar 5) |

#### <a name="version-introduced"></a>Versión introducida

.NET 5.0

#### <a name="recommended-action"></a>Acción recomendada

- Actualice el código para evitar pasar argumentos no válidos.
- Si es necesario, controle una excepción <xref:System.ArgumentException> al llamar al método.

#### <a name="category"></a>Categoría

Windows Forms

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>
- <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`

-->
