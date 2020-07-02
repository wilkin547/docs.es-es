---
ms.openlocfilehash: c3c3ed44cf53625c246dfe0408bb861750ecf336
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622124"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="a5e68-101">Las llamadas a DataGrid.CommitEdit desde un controlador CellEditEnding eliminan el foco</span><span class="sxs-lookup"><span data-stu-id="a5e68-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

#### <a name="details"></a><span data-ttu-id="a5e68-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a5e68-102">Details</span></span>

<span data-ttu-id="a5e68-103">Las llamadas a <xref:System.Windows.Controls.DataGrid.CommitEdit> desde uno de los controladores de eventos <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> de <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> provoca que <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> pierda el foco.</span><span class="sxs-lookup"><span data-stu-id="a5e68-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> to lose focus.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a5e68-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a5e68-104">Suggestion</span></span>

<span data-ttu-id="a5e68-105">Este error se corrigió en .NET Framework 4.5.2, por lo que se puede evitar actualizando a una versión posterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5e68-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="a5e68-106">Como alternativa, se puede evitar si se selecciona <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> de forma explícita después de llamar a <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="a5e68-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span></span>

| <span data-ttu-id="a5e68-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="a5e68-107">Name</span></span>    | <span data-ttu-id="a5e68-108">Valor</span><span class="sxs-lookup"><span data-stu-id="a5e68-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a5e68-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a5e68-109">Scope</span></span>   |<span data-ttu-id="a5e68-110">Borde</span><span class="sxs-lookup"><span data-stu-id="a5e68-110">Edge</span></span>|
|<span data-ttu-id="a5e68-111">Versión</span><span class="sxs-lookup"><span data-stu-id="a5e68-111">Version</span></span>|<span data-ttu-id="a5e68-112">4.5</span><span class="sxs-lookup"><span data-stu-id="a5e68-112">4.5</span></span>|
|<span data-ttu-id="a5e68-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="a5e68-113">Type</span></span>|<span data-ttu-id="a5e68-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a5e68-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a5e68-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a5e68-115">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
