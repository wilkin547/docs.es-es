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
# <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="74a10-103">Los métodos de WinForms inician ahora la excepción ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="74a10-103">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="74a10-104">Algunos métodos de Windows Forms inician ahora una <xref:System.ArgumentNullException> para los argumentos NULL, donde antes iniciaban una <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="74a10-104">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

## <a name="change-description"></a><span data-ttu-id="74a10-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="74a10-105">Change description</span></span>

<span data-ttu-id="74a10-106">Anteriormente, algunos métodos de Windows Forms iniciaban una <xref:System.NullReferenceException> si se pasaba un argumento que era NULL.</span><span class="sxs-lookup"><span data-stu-id="74a10-106">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="74a10-107">A partir de .NET 5, estos métodos inician ahora en cambio una excepción <xref:System.ArgumentNullException> para los argumentos NULL.</span><span class="sxs-lookup"><span data-stu-id="74a10-107">Starting in .NET 5, these methods now throw an <xref:System.ArgumentNullException> for null arguments, instead.</span></span>

<span data-ttu-id="74a10-108">El inicio de una <xref:System.ArgumentNullException> se ajusta al comportamiento del tiempo de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="74a10-108">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="74a10-109">También mejora la experiencia de depuración al comunicar claramente que un argumento es NULL y de qué argumento se trata.</span><span class="sxs-lookup"><span data-stu-id="74a10-109">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="74a10-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="74a10-110">Version introduced</span></span>

<span data-ttu-id="74a10-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="74a10-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="74a10-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="74a10-112">Recommended action</span></span>

<span data-ttu-id="74a10-113">Si llama a cualquiera de estos métodos y el código detecta actualmente una <xref:System.NullReferenceException> para los argumentos NULL, capture en su lugar una <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="74a10-113">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="74a10-114">Además, considere la posibilidad de actualizar el código para evitar pasar argumentos NULL a los métodos enumerados.</span><span class="sxs-lookup"><span data-stu-id="74a10-114">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="74a10-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="74a10-115">Affected APIs</span></span>

<span data-ttu-id="74a10-116">En la tabla siguiente se enumeran los métodos y parámetros afectados:</span><span class="sxs-lookup"><span data-stu-id="74a10-116">The following table lists the affected methods and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="74a10-117">Método</span><span class="sxs-lookup"><span data-stu-id="74a10-117">Method</span></span> | <span data-ttu-id="74a10-118">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="74a10-118">Parameter name</span></span> | <span data-ttu-id="74a10-119">Versión agregada</span><span class="sxs-lookup"><span data-stu-id="74a10-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | <span data-ttu-id="74a10-120">Versión preliminar 1</span><span class="sxs-lookup"><span data-stu-id="74a10-120">Preview 1</span></span> |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | <span data-ttu-id="74a10-121">Versión preliminar 1</span><span class="sxs-lookup"><span data-stu-id="74a10-121">Preview 1</span></span> |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | <span data-ttu-id="74a10-122">Versión preliminar 1</span><span class="sxs-lookup"><span data-stu-id="74a10-122">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="74a10-123">Versión preliminar 1</span><span class="sxs-lookup"><span data-stu-id="74a10-123">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="74a10-124">Versión preliminar 1</span><span class="sxs-lookup"><span data-stu-id="74a10-124">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="74a10-125">Versión preliminar 1</span><span class="sxs-lookup"><span data-stu-id="74a10-125">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="74a10-126">Versión preliminar 1</span><span class="sxs-lookup"><span data-stu-id="74a10-126">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | <span data-ttu-id="74a10-127">Versión preliminar 1</span><span class="sxs-lookup"><span data-stu-id="74a10-127">Preview 1</span></span> |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | <span data-ttu-id="74a10-128">Versión preliminar 2</span><span class="sxs-lookup"><span data-stu-id="74a10-128">Preview 2</span></span> |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | <span data-ttu-id="74a10-129">Versión preliminar 2</span><span class="sxs-lookup"><span data-stu-id="74a10-129">Preview 2</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="74a10-130">Versión preliminar 5</span><span class="sxs-lookup"><span data-stu-id="74a10-130">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="74a10-131">Versión preliminar 5</span><span class="sxs-lookup"><span data-stu-id="74a10-131">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | <span data-ttu-id="74a10-132">Versión preliminar 5</span><span class="sxs-lookup"><span data-stu-id="74a10-132">Preview 5</span></span> |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | <span data-ttu-id="74a10-133">Versión preliminar 5</span><span class="sxs-lookup"><span data-stu-id="74a10-133">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="74a10-134">Versión preliminar 6</span><span class="sxs-lookup"><span data-stu-id="74a10-134">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])> | <span data-ttu-id="74a10-135">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="74a10-135">`owner`, `value`</span></span> | <span data-ttu-id="74a10-136">Versión preliminar 6</span><span class="sxs-lookup"><span data-stu-id="74a10-136">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)> | <span data-ttu-id="74a10-137">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="74a10-137">`owner`, `value`</span></span> | <span data-ttu-id="74a10-138">Versión preliminar 6</span><span class="sxs-lookup"><span data-stu-id="74a10-138">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])?displayProperty=nameWithType> | `items` | <span data-ttu-id="74a10-139">Versión preliminar 6</span><span class="sxs-lookup"><span data-stu-id="74a10-139">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)?displayProperty=nameWithType> | `value` | <span data-ttu-id="74a10-140">Versión preliminar 6</span><span class="sxs-lookup"><span data-stu-id="74a10-140">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="74a10-141">Versión preliminar 6</span><span class="sxs-lookup"><span data-stu-id="74a10-141">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="74a10-142">Versión preliminar 6</span><span class="sxs-lookup"><span data-stu-id="74a10-142">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListView.SelectedIndexCollection.%23ctor(System.Windows.Forms.ListView)> | `owner` | <span data-ttu-id="74a10-143">Versión preliminar 7</span><span class="sxs-lookup"><span data-stu-id="74a10-143">Preview 7</span></span> |
> | <xref:System.Windows.Forms.TreeNodeCollection.Find(System.String,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="74a10-144">`key` es `null` o está vacío</span><span class="sxs-lookup"><span data-stu-id="74a10-144">`key` is `null` or empty</span></span> | <span data-ttu-id="74a10-145">Versión preliminar 8</span><span class="sxs-lookup"><span data-stu-id="74a10-145">Preview 8</span></span> |
> | <xref:System.Windows.Forms.ListView.ListViewItemCollection.Find(System.String,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="74a10-146">`key` es `null` o está vacío</span><span class="sxs-lookup"><span data-stu-id="74a10-146">`key` is `null` or empty</span></span> | <span data-ttu-id="74a10-147">RC1</span><span class="sxs-lookup"><span data-stu-id="74a10-147">RC1</span></span> |
> | <xref:System.Windows.Forms.ScrollableControl.OnPaintBackground(System.Windows.Forms.PaintEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="74a10-148">RC1</span><span class="sxs-lookup"><span data-stu-id="74a10-148">RC1</span></span> |

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
