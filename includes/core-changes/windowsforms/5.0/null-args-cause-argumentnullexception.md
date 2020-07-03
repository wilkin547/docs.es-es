---
ms.openlocfilehash: 00f89e6ae49982917fa7591c3283adec3947eed2
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365662"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="01ee5-101">Los métodos de WinForms inician ahora la excepción ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="01ee5-101">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="01ee5-102">Algunos métodos de Windows Forms inician ahora una <xref:System.ArgumentNullException> para los argumentos NULL, donde antes iniciaban una <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="01ee5-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="01ee5-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="01ee5-103">Change description</span></span>

<span data-ttu-id="01ee5-104">Anteriormente, algunos métodos de Windows Forms iniciaban una <xref:System.NullReferenceException> si se pasaba un argumento que era NULL.</span><span class="sxs-lookup"><span data-stu-id="01ee5-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="01ee5-105">A partir de .NET 5.0, estos métodos inician ahora en cambio una excepción <xref:System.ArgumentNullException> para los argumentos NULL.</span><span class="sxs-lookup"><span data-stu-id="01ee5-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments, instead.</span></span>

<span data-ttu-id="01ee5-106">El inicio de una <xref:System.ArgumentNullException> se ajusta al comportamiento del tiempo de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="01ee5-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="01ee5-107">También mejora la experiencia de depuración al comunicar claramente que un argumento es NULL y de qué argumento se trata.</span><span class="sxs-lookup"><span data-stu-id="01ee5-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="01ee5-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="01ee5-108">Version introduced</span></span>

<span data-ttu-id="01ee5-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="01ee5-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="01ee5-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="01ee5-110">Recommended action</span></span>

<span data-ttu-id="01ee5-111">Si llama a cualquiera de estos métodos y el código detecta actualmente una <xref:System.NullReferenceException> para los argumentos NULL, capture en su lugar una <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="01ee5-111">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="01ee5-112">Además, considere la posibilidad de actualizar el código para evitar pasar argumentos NULL a los métodos enumerados.</span><span class="sxs-lookup"><span data-stu-id="01ee5-112">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="01ee5-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="01ee5-113">Category</span></span>

<span data-ttu-id="01ee5-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="01ee5-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="01ee5-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="01ee5-115">Affected APIs</span></span>

<span data-ttu-id="01ee5-116">En la tabla siguiente se enumeran los métodos y parámetros afectados:</span><span class="sxs-lookup"><span data-stu-id="01ee5-116">The following table lists the affected methods and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="01ee5-117">Método</span><span class="sxs-lookup"><span data-stu-id="01ee5-117">Method</span></span> | <span data-ttu-id="01ee5-118">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="01ee5-118">Parameter name</span></span> | <span data-ttu-id="01ee5-119">Versión agregada</span><span class="sxs-lookup"><span data-stu-id="01ee5-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | <span data-ttu-id="01ee5-120">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="01ee5-120">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | <span data-ttu-id="01ee5-121">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="01ee5-121">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | <span data-ttu-id="01ee5-122">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="01ee5-122">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="01ee5-123">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="01ee5-123">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="01ee5-124">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="01ee5-124">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="01ee5-125">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="01ee5-125">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="01ee5-126">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="01ee5-126">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | <span data-ttu-id="01ee5-127">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="01ee5-127">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | <span data-ttu-id="01ee5-128">5.0 (versión preliminar 2)</span><span class="sxs-lookup"><span data-stu-id="01ee5-128">5.0 Preview 2</span></span> |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | <span data-ttu-id="01ee5-129">5.0 (versión preliminar 2)</span><span class="sxs-lookup"><span data-stu-id="01ee5-129">5.0 Preview 2</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="01ee5-130">5.0 (versión preliminar 5)</span><span class="sxs-lookup"><span data-stu-id="01ee5-130">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="01ee5-131">5.0 (versión preliminar 5)</span><span class="sxs-lookup"><span data-stu-id="01ee5-131">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | <span data-ttu-id="01ee5-132">5.0 (versión preliminar 5)</span><span class="sxs-lookup"><span data-stu-id="01ee5-132">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | <span data-ttu-id="01ee5-133">5.0 (versión preliminar 5)</span><span class="sxs-lookup"><span data-stu-id="01ee5-133">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="01ee5-134">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="01ee5-134">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])> | <span data-ttu-id="01ee5-135">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="01ee5-135">`owner`, `value`</span></span> | <span data-ttu-id="01ee5-136">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="01ee5-136">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)> | <span data-ttu-id="01ee5-137">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="01ee5-137">`owner`, `value`</span></span> | <span data-ttu-id="01ee5-138">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="01ee5-138">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])?displayProperty=nameWithType> | `items` | <span data-ttu-id="01ee5-139">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="01ee5-139">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)?displayProperty=nameWithType> | `value` | <span data-ttu-id="01ee5-140">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="01ee5-140">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="01ee5-141">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="01ee5-141">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="01ee5-142">`destination`q\`</span><span class="sxs-lookup"><span data-stu-id="01ee5-142">`destination`q\`</span></span> | <span data-ttu-id="01ee5-143">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="01ee5-143">5.0 Preview 6</span></span> |

<!-- 

#### Affected APIs

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
- `M:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`
- `M:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)`

-->
