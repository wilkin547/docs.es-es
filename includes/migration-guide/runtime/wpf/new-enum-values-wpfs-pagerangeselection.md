---
ms.openlocfilehash: bae6d7c0f8843211c721c68ce6f16000b35b4401
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620701"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="9702b-101">Nuevos valores de enumeración en PageRangeSelection de WPF</span><span class="sxs-lookup"><span data-stu-id="9702b-101">New enum values in WPF's PageRangeSelection</span></span>

#### <a name="details"></a><span data-ttu-id="9702b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="9702b-102">Details</span></span>

<span data-ttu-id="9702b-103">Se han agregado dos miembros nuevos (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> y <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) a la enumeración <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="9702b-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> enum.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="9702b-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="9702b-104">Suggestion</span></span>

<span data-ttu-id="9702b-105">En la mayoría de los casos, estos cambios no afectan al código del usuario.</span><span class="sxs-lookup"><span data-stu-id="9702b-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="9702b-106">Pero se debe modificar el código que depende de un número concreto de elementos existentes en las llamadas a <xref:System.Enum.GetNames(System.Type)> o <xref:System.Enum.GetValues(System.Type)> del tipo <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="9702b-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> type should be modified, though.</span></span>

| <span data-ttu-id="9702b-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="9702b-107">Name</span></span>    | <span data-ttu-id="9702b-108">Valor</span><span class="sxs-lookup"><span data-stu-id="9702b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="9702b-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="9702b-109">Scope</span></span>   |<span data-ttu-id="9702b-110">Borde</span><span class="sxs-lookup"><span data-stu-id="9702b-110">Edge</span></span>|
|<span data-ttu-id="9702b-111">Versión</span><span class="sxs-lookup"><span data-stu-id="9702b-111">Version</span></span>|<span data-ttu-id="9702b-112">4.5</span><span class="sxs-lookup"><span data-stu-id="9702b-112">4.5</span></span>|
|<span data-ttu-id="9702b-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="9702b-113">Type</span></span>|<span data-ttu-id="9702b-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="9702b-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9702b-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="9702b-115">Affected APIs</span></span>

-<xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType></li></ul>|
