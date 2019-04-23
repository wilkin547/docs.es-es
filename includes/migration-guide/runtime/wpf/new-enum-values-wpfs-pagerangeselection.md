---
ms.openlocfilehash: edd194fef27d97976f1ff45daec1cd56382bbb55
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805086"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="7b2cf-101">Nuevos valores de enumeración en PageRangeSelection de WPF</span><span class="sxs-lookup"><span data-stu-id="7b2cf-101">New enum values in WPF's PageRangeSelection</span></span>

|   |   |
|---|---|
|<span data-ttu-id="7b2cf-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="7b2cf-102">Details</span></span>|<span data-ttu-id="7b2cf-103">Se han agregado dos miembros nuevos (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=name> y <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=name>) a la enumeración <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="7b2cf-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=name> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=name>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> enum.</span></span>|
|<span data-ttu-id="7b2cf-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="7b2cf-104">Suggestion</span></span>|<span data-ttu-id="7b2cf-105">En la mayoría de los casos, estos cambios no afectan al código del usuario.</span><span class="sxs-lookup"><span data-stu-id="7b2cf-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="7b2cf-106">Pero se debe modificar el código que depende de un número concreto de elementos existentes en las llamadas a <xref:System.Enum.GetNames(System.Type)> o <xref:System.Enum.GetValues(System.Type)> del tipo <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="7b2cf-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=name> type should be modified, though.</span></span>|
|<span data-ttu-id="7b2cf-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="7b2cf-107">Scope</span></span>|<span data-ttu-id="7b2cf-108">Borde</span><span class="sxs-lookup"><span data-stu-id="7b2cf-108">Edge</span></span>|
|<span data-ttu-id="7b2cf-109">Versión</span><span class="sxs-lookup"><span data-stu-id="7b2cf-109">Version</span></span>|<span data-ttu-id="7b2cf-110">4.5</span><span class="sxs-lookup"><span data-stu-id="7b2cf-110">4.5</span></span>|
|<span data-ttu-id="7b2cf-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="7b2cf-111">Type</span></span>|<span data-ttu-id="7b2cf-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7b2cf-112">Runtime</span></span>|
|<span data-ttu-id="7b2cf-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7b2cf-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
