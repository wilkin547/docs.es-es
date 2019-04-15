---
ms.openlocfilehash: 74ce1bbc9a887aee3a33eaf05084e8c2000967c2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235956"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="0bbbf-101">El texto seleccionado de un cuadro de texto de WPF aparece en otro color cuando el cuadro de texto está inactivo</span><span class="sxs-lookup"><span data-stu-id="0bbbf-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0bbbf-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="0bbbf-102">Details</span></span>|<span data-ttu-id="0bbbf-103">En .NET Framework 4.5, cuando un control de cuadro de texto de WPF está inactivo (sin el foco), el texto seleccionado dentro del cuadro aparecerá en un color diferente al que lo haría con el control activo.</span><span class="sxs-lookup"><span data-stu-id="0bbbf-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>|
|<span data-ttu-id="0bbbf-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="0bbbf-104">Suggestion</span></span>|<span data-ttu-id="0bbbf-105">El comportamiento anterior (.NET Framework 4.0) se puede restaurar si se establece la propiedad <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> en <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="0bbbf-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>|
|<span data-ttu-id="0bbbf-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0bbbf-106">Scope</span></span>|<span data-ttu-id="0bbbf-107">Borde</span><span class="sxs-lookup"><span data-stu-id="0bbbf-107">Edge</span></span>|
|<span data-ttu-id="0bbbf-108">Versión</span><span class="sxs-lookup"><span data-stu-id="0bbbf-108">Version</span></span>|<span data-ttu-id="0bbbf-109">4.5</span><span class="sxs-lookup"><span data-stu-id="0bbbf-109">4.5</span></span>|
|<span data-ttu-id="0bbbf-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="0bbbf-110">Type</span></span>|<span data-ttu-id="0bbbf-111">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0bbbf-111">Runtime</span></span>|
|<span data-ttu-id="0bbbf-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0bbbf-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
