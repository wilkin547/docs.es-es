---
ms.openlocfilehash: 61749f59f9379a6d18bb013b2612a07cb7822b3a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496628"
---
### <a name="new-enum-values-in-wpfs-pagerangeselection"></a><span data-ttu-id="1e590-101">Nuevos valores de enumeración en PageRangeSelection de WPF</span><span class="sxs-lookup"><span data-stu-id="1e590-101">New enum values in WPF's PageRangeSelection</span></span>

#### <a name="details"></a><span data-ttu-id="1e590-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="1e590-102">Details</span></span>

<span data-ttu-id="1e590-103">Se han agregado dos miembros nuevos (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> y <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) a la enumeración <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="1e590-103">Two new members (<xref:System.Windows.Controls.PageRangeSelection.CurrentPage?displayProperty=fullName> and <xref:System.Windows.Controls.PageRangeSelection.SelectedPages?displayProperty=fullName>) have been added to the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> enum.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1e590-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="1e590-104">Suggestion</span></span>

<span data-ttu-id="1e590-105">En la mayoría de los casos, estos cambios no afectan al código del usuario.</span><span class="sxs-lookup"><span data-stu-id="1e590-105">In most cases, these changes won't impact user code.</span></span> <span data-ttu-id="1e590-106">Pero se debe modificar el código que depende de un número concreto de elementos existentes en las llamadas a <xref:System.Enum.GetNames(System.Type)> o <xref:System.Enum.GetValues(System.Type)> del tipo <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="1e590-106">Code that depends on a particular number of elements existing in <xref:System.Enum.GetNames(System.Type)> or <xref:System.Enum.GetValues(System.Type)> calls on the <xref:System.Windows.Controls.PageRangeSelection?displayProperty=fullName> type should be modified, though.</span></span>

| <span data-ttu-id="1e590-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="1e590-107">Name</span></span>    | <span data-ttu-id="1e590-108">Valor</span><span class="sxs-lookup"><span data-stu-id="1e590-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1e590-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="1e590-109">Scope</span></span>   |<span data-ttu-id="1e590-110">Borde</span><span class="sxs-lookup"><span data-stu-id="1e590-110">Edge</span></span>|
|<span data-ttu-id="1e590-111">Versión</span><span class="sxs-lookup"><span data-stu-id="1e590-111">Version</span></span>|<span data-ttu-id="1e590-112">4.5</span><span class="sxs-lookup"><span data-stu-id="1e590-112">4.5</span></span>|
|<span data-ttu-id="1e590-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="1e590-113">Type</span></span>|<span data-ttu-id="1e590-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1e590-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1e590-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1e590-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.PageRangeSelection?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.PageRangeSelection`

-->
