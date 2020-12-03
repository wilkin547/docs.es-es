---
title: 'Cambio importante: Ahora, las propiedades de WinForms producen ArgumentOutOfRangeException'
description: Obtenga información sobre el cambio importante en .NET 5.0 por el que algunas propiedades de Windows Forms ahora inician una excepción ArgumentOutOfRangeException para los argumentos no válidos.
ms.date: 06/18/2020
ms.openlocfilehash: 94593047d16304ce401b23993ad4ca173c10812b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760217"
---
# <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a>Ahora, las propiedades de WinForms producen ArgumentOutOfRangeException

Algunas propiedades de Windows Forms inician ahora una excepción <xref:System.ArgumentOutOfRangeException> en los argumentos no válidos, donde antes no lo hacían.

## <a name="change-description"></a>Descripción del cambio

Anteriormente, estas propiedades producían varias excepciones, como <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>o <xref:System.ArgumentException>, cuando se pasaban argumentos fuera del intervalo. A partir de .NET 5.0, estas propiedades producen ahora <xref:System.ArgumentOutOfRangeException> cuando se pasan argumentos que están fuera del intervalo.

El inicio de una <xref:System.ArgumentOutOfRangeException> se ajusta al comportamiento del tiempo de ejecución de .NET. También mejora la experiencia de depuración al comunicar claramente qué argumento no es válido.

## <a name="version-introduced"></a>Versión introducida

.NET 5.0

## <a name="recommended-action"></a>Acción recomendada

- Actualice el código para evitar pasar argumentos no válidos.
- Si es necesario, administre un elemento <xref:System.ArgumentOutOfRangeException> al establecer la propiedad.

## <a name="affected-apis"></a>API afectadas

En la tabla siguiente se enumeran las propiedades y los parámetros afectados:

> [!div class="mx-tdBreakAll"]
> | Propiedad. | Nombre de parámetro | Versión agregada |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | 5.0 (versión preliminar 5) |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | 5.0 (versión preliminar 6) |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | 5.0 (versión preliminar 6) |

<!--

### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

### Category

Windows Forms

-->
