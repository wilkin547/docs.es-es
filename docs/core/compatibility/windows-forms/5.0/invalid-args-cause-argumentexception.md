---
title: 'Cambio importante: Los métodos de WinForms inician ahora la excepción ArgumentException'
description: Obtenga información sobre el cambio importante en .NET 5.0 por el que algunos métodos de Windows Forms ahora inician una excepción ArgumentException para los argumentos no válidos.
ms.date: 07/18/2020
ms.openlocfilehash: 892f4d16b80f3e42187480a7fcfb24e81868d07c
ms.sourcegitcommit: f8cd3ef517ee177c99feed944824c27d208cc0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2021
ms.locfileid: "98570221"
---
# <a name="winforms-methods-now-throw-argumentexception"></a>Los métodos de WinForms inician ahora la excepción ArgumentException

Algunos métodos de Windows Forms inician ahora una excepción <xref:System.ArgumentException> en los argumentos no válidos, donde antes no lo hacían.

## <a name="change-description"></a>Descripción del cambio

Anteriormente, al pasar argumentos de un tipo inesperado o incorrecto a ciertos métodos de Windows Forms se originaba un estado indeterminado. A partir de .NET 5.0, estos métodos inician una excepción <xref:System.ArgumentException> cuando se pasan argumentos no válidos.

El inicio de una <xref:System.ArgumentException> se ajusta al comportamiento del tiempo de ejecución de .NET. También mejora la experiencia de depuración al comunicar claramente qué argumento no es válido.

## <a name="version-introduced"></a>Versión introducida

.NET 5.0

## <a name="recommended-action"></a>Acción recomendada

- Actualice el código para evitar pasar argumentos no válidos.
- Si es necesario, controle una excepción <xref:System.ArgumentException> al llamar al método.

## <a name="affected-apis"></a>API afectadas

En la tabla siguiente se enumeran los métodos y parámetros afectados:

| Método | Nombre de parámetro | Condición | Versión agregada |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | El argumento no es del tipo <xref:System.Windows.Forms.TabPage>. | Versión preliminar 1 |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | El argumento es `null`, <xref:System.String.Empty?displayProperty=nameWithType> o un espacio en blanco. | Versión preliminar 5 |
| <xref:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)> | `culture` | No se puede recuperar `InputLanguage` para la referencia cultural especificada. | Versión preliminar 7 |

<!--

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`
- `M:System.Windows.Forms.InputLanguageChangedEventArgs.%23ctor(System.Globalization.CultureInfo,System.Byte)`

### Category

Windows Forms

-->
