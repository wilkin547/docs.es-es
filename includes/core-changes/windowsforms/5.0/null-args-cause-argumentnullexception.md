---
ms.openlocfilehash: ab8d801f3cdcfbeb6de20146754b26e3713d7dd6
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702458"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="5f7b8-101">Los métodos de WinForms inician ahora la excepción ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="5f7b8-101">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="5f7b8-102">Algunos métodos de Windows Forms inician ahora una <xref:System.ArgumentNullException> para los argumentos NULL, donde antes iniciaban una <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="5f7b8-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5f7b8-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="5f7b8-103">Change description</span></span>

<span data-ttu-id="5f7b8-104">Anteriormente, algunos métodos de Windows Forms iniciaban una <xref:System.NullReferenceException> si se pasaba un argumento que era NULL.</span><span class="sxs-lookup"><span data-stu-id="5f7b8-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="5f7b8-105">A partir de .NET 5.0, estos métodos inician ahora en su lugar una <xref:System.ArgumentNullException> para los argumentos NULL.</span><span class="sxs-lookup"><span data-stu-id="5f7b8-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments instead.</span></span>

<span data-ttu-id="5f7b8-106">El inicio de una <xref:System.ArgumentNullException> se ajusta al comportamiento del tiempo de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="5f7b8-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="5f7b8-107">También mejora la experiencia de depuración al comunicar claramente que un argumento es NULL y de qué argumento se trata.</span><span class="sxs-lookup"><span data-stu-id="5f7b8-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5f7b8-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5f7b8-108">Version introduced</span></span>

<span data-ttu-id="5f7b8-109">.NET 5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="5f7b8-109">.NET 5.0 Preview 1</span></span>\
<span data-ttu-id="5f7b8-110">.NET 5.0 (versión preliminar 2)</span><span class="sxs-lookup"><span data-stu-id="5f7b8-110">.NET 5.0 Preview 2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5f7b8-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="5f7b8-111">Recommended action</span></span>

<span data-ttu-id="5f7b8-112">Si llama a cualquiera de estos métodos y el código detecta actualmente una <xref:System.NullReferenceException> para los argumentos NULL, capture en su lugar una <xref:System.ArgumentNullException>.</span><span class="sxs-lookup"><span data-stu-id="5f7b8-112">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="5f7b8-113">Además, considere la posibilidad de actualizar el código para evitar pasar argumentos NULL a los métodos enumerados.</span><span class="sxs-lookup"><span data-stu-id="5f7b8-113">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="5f7b8-114">Categoría</span><span class="sxs-lookup"><span data-stu-id="5f7b8-114">Category</span></span>

<span data-ttu-id="5f7b8-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5f7b8-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5f7b8-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5f7b8-116">Affected APIs</span></span>

<span data-ttu-id="5f7b8-117">A partir de .NET 5.0 (versión preliminar 1):</span><span class="sxs-lookup"><span data-stu-id="5f7b8-117">Starting in .NET 5.0 Preview 1:</span></span>

- <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)>
- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType>

<span data-ttu-id="5f7b8-118">A partir de .NET 5.0 (versión preliminar 2):</span><span class="sxs-lookup"><span data-stu-id="5f7b8-118">Starting in .NET 5.0 Preview 2:</span></span>

- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType>
- <span data-ttu-id="5f7b8-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (solo para el parámetro <xref:System.IO.Stream>)</span><span class="sxs-lookup"><span data-stu-id="5f7b8-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (for the <xref:System.IO.Stream> parameter only)</span></span>

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

-->
