---
ms.openlocfilehash: cd59818fe674e10a206725bea8a74c4aceed99b1
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620707"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="fde44-101">El texto seleccionado de un cuadro de texto de WPF aparece en otro color cuando el cuadro de texto está inactivo</span><span class="sxs-lookup"><span data-stu-id="fde44-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

#### <a name="details"></a><span data-ttu-id="fde44-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="fde44-102">Details</span></span>

<span data-ttu-id="fde44-103">En .NET Framework 4.5, cuando un control de cuadro de texto de WPF está inactivo (sin el foco), el texto seleccionado dentro del cuadro aparecerá en un color diferente al que lo haría con el control activo.</span><span class="sxs-lookup"><span data-stu-id="fde44-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fde44-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="fde44-104">Suggestion</span></span>

<span data-ttu-id="fde44-105">El comportamiento anterior (.NET Framework 4.0) se puede restaurar si se establece la propiedad <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> en <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="fde44-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>

| <span data-ttu-id="fde44-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="fde44-106">Name</span></span>    | <span data-ttu-id="fde44-107">Valor</span><span class="sxs-lookup"><span data-stu-id="fde44-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fde44-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="fde44-108">Scope</span></span>   |<span data-ttu-id="fde44-109">Borde</span><span class="sxs-lookup"><span data-stu-id="fde44-109">Edge</span></span>|
|<span data-ttu-id="fde44-110">Versión</span><span class="sxs-lookup"><span data-stu-id="fde44-110">Version</span></span>|<span data-ttu-id="fde44-111">4.5</span><span class="sxs-lookup"><span data-stu-id="fde44-111">4.5</span></span>|
|<span data-ttu-id="fde44-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="fde44-112">Type</span></span>|<span data-ttu-id="fde44-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="fde44-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fde44-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="fde44-114">Affected APIs</span></span>

-<xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
