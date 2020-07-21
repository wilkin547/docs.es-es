---
ms.openlocfilehash: 9f6703c77e17ac9376aee944b891f4635dc7632e
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309169"
---
### <a name="winforms-methods-now-throw-argumentexception"></a>Los métodos de WinForms inician ahora la excepción ArgumentException

Algunos métodos de Windows Forms inician ahora una excepción <xref:System.ArgumentException> en los argumentos no válidos, donde antes no lo hacían.

#### <a name="change-description"></a>Descripción del cambio

Anteriormente, al pasar argumentos de un tipo inesperado o incorrecto a ciertos métodos de Windows Forms se originaba un estado indeterminado. A partir de .NET 5.0, estos métodos inician una excepción <xref:System.ArgumentException> cuando se pasan argumentos no válidos.

El inicio de una <xref:System.ArgumentException> se ajusta al comportamiento del tiempo de ejecución de .NET. También mejora la experiencia de depuración al comunicar claramente qué argumento no es válido.

#### <a name="version-introduced"></a>Versión introducida

.NET 5.0

#### <a name="recommended-action"></a>Acción recomendada

- Actualice el código para evitar pasar argumentos no válidos.
- Si es necesario, controle una excepción <xref:System.ArgumentException> al llamar al método.

#### <a name="category"></a>Categoría

Windows Forms

#### <a name="affected-apis"></a>API afectadas

En la tabla siguiente se enumeran los métodos y parámetros afectados:

| Método | Nombre de parámetro | Condición | Versión agregada |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | El argumento no es del tipo <xref:System.Windows.Forms.TabPage>. | Versión preliminar 1 |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | El argumento es `null`, <xref:System.String.Empty?displayProperty=nameWithType> o un espacio en blanco. | Versión preliminar 5 |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | No se puede recuperar `InputLanguage` para la referencia cultural especificada. | Versión preliminar 7 |

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

-->
