---
title: 'Cambio importante: Los métodos de WinForms inician ahora la excepción ArgumentNullException'
description: Obtenga información sobre el cambio importante en .NET 5 por el que algunos métodos de Windows Forms ahora inician una excepción ArgumentNullException para los argumentos NULL.
ms.date: 09/18/2020
ms.openlocfilehash: 9d72f8e3320430396132de20c252cd5e8759dce3
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256105"
---
# <a name="winforms-methods-now-throw-argumentnullexception"></a>Los métodos de WinForms inician ahora la excepción ArgumentNullException

Algunos métodos de Windows Forms inician ahora una <xref:System.ArgumentNullException> para los argumentos NULL, donde antes iniciaban una <xref:System.NullReferenceException>.

## <a name="change-description"></a>Descripción del cambio

Anteriormente, algunos métodos de Windows Forms iniciaban una <xref:System.NullReferenceException> si se pasaba un argumento que era NULL. A partir de .NET 5, estos métodos inician ahora en cambio una excepción <xref:System.ArgumentNullException> para los argumentos NULL.

El inicio de una <xref:System.ArgumentNullException> se ajusta al comportamiento del tiempo de ejecución de .NET. También mejora la experiencia de depuración al comunicar claramente que un argumento es NULL y de qué argumento se trata.

## <a name="version-introduced"></a>Versión introducida

.NET 5.0

## <a name="recommended-action"></a>Acción recomendada

Si llama a cualquiera de estos métodos y el código detecta actualmente una <xref:System.NullReferenceException> para los argumentos NULL, capture en su lugar una <xref:System.ArgumentNullException>. Además, considere la posibilidad de actualizar el código para evitar pasar argumentos NULL a los métodos enumerados.

## <a name="affected-apis"></a>API afectadas

En la tabla siguiente se enumeran los métodos y parámetros afectados:

> [!div class="mx-tdBreakAll"]
> | Método | Nombre de parámetro | Versión agregada |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | Versión preliminar 1 |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | Versión preliminar 1 |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | Versión preliminar 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | Versión preliminar 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | Versión preliminar 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | Versión preliminar 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | Versión preliminar 1 |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | Versión preliminar 1 |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | Versión preliminar 2 |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | Versión preliminar 2 |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | Versión preliminar 5 |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | Versión preliminar 5 |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | Versión preliminar 5 |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | Versión preliminar 5 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | Versión preliminar 6 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])> | `owner`, `value` | Versión preliminar 6 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)> | `owner`, `value` | Versión preliminar 6 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])?displayProperty=nameWithType> | `items` | Versión preliminar 6 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)?displayProperty=nameWithType> | `value` | Versión preliminar 6 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)?displayProperty=nameWithType> | `destination` | Versión preliminar 6 |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | Versión preliminar 6 |
> | <xref:System.Windows.Forms.ListView.SelectedIndexCollection.%23ctor(System.Windows.Forms.ListView)> | `owner` | Versión preliminar 7 |
> | <xref:System.Windows.Forms.TreeNodeCollection.Find(System.String,System.Boolean)?displayProperty=nameWithType> | `key` es `null` o está vacío | Versión preliminar 8 |
> | <xref:System.Windows.Forms.ListView.ListViewItemCollection.Find(System.String,System.Boolean)?displayProperty=nameWithType> | `key` es `null` o está vacío | RC1 |
> | <xref:System.Windows.Forms.ScrollableControl.OnPaintBackground(System.Windows.Forms.PaintEventArgs)?displayProperty=nameWithType> | `e` | RC1 |

<!--

### Affected APIs

- `M:System.Windows.Forms.Control.ControlCollection.#ctor(System.Windows.Forms.Control)`
- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.TableLayoutControlCollection.#ctor(System.Windows.Forms.TableLayoutPanel)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)`
- `M:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)`
- `M:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)`
- `M:System.Windows.Forms.ListViewGroup.System#Runtime#Serialization#ISerializable#GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`
- `M:System.Windows.Forms.VisualStyles.VisualStyleRenderer.#ctor(System.String,System.Int32,System.Int32)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.#ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox,System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.System#Collections#ICollection#CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListView.SelectedIndexCollection.#ctor(System.Windows.Forms.ListView)`
- `M:System.Windows.Forms.TreeNodeCollection.Find(System.String,System.Boolean)`
- `M:System.Windows.Forms.ListView.ListViewItemCollection.Find(System.String,System.Boolean)`
- `M:System.Windows.Forms.ScrollableControl.OnPaintBackground(System.Windows.Forms.PaintEventArgs)`

### Category

Windows Forms

-->
