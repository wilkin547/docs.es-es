---
ms.openlocfilehash: c78122a2fe69c78625d6cb7fa9ddf41c49c2e737
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497694"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="000cd-101">Las llamadas a DataGrid.CommitEdit desde un controlador CellEditEnding eliminan el foco</span><span class="sxs-lookup"><span data-stu-id="000cd-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

#### <a name="details"></a><span data-ttu-id="000cd-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="000cd-102">Details</span></span>

<span data-ttu-id="000cd-103">Las llamadas a <xref:System.Windows.Controls.DataGrid.CommitEdit> desde uno de los controladores de eventos <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> de <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> provoca que <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> pierda el foco.</span><span class="sxs-lookup"><span data-stu-id="000cd-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=fullName> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> to lose focus.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="000cd-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="000cd-104">Suggestion</span></span>

<span data-ttu-id="000cd-105">Este error se corrigió en .NET Framework 4.5.2, por lo que se puede evitar actualizando a una versión posterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="000cd-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="000cd-106">Como alternativa, se puede evitar si se selecciona <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> de forma explícita después de llamar a <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="000cd-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=fullName> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=fullName>.</span></span>

| <span data-ttu-id="000cd-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="000cd-107">Name</span></span>    | <span data-ttu-id="000cd-108">Valor</span><span class="sxs-lookup"><span data-stu-id="000cd-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="000cd-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="000cd-109">Scope</span></span>   |<span data-ttu-id="000cd-110">Borde</span><span class="sxs-lookup"><span data-stu-id="000cd-110">Edge</span></span>|
|<span data-ttu-id="000cd-111">Versión</span><span class="sxs-lookup"><span data-stu-id="000cd-111">Version</span></span>|<span data-ttu-id="000cd-112">4.5</span><span class="sxs-lookup"><span data-stu-id="000cd-112">4.5</span></span>|
|<span data-ttu-id="000cd-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="000cd-113">Type</span></span>|<span data-ttu-id="000cd-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="000cd-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="000cd-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="000cd-115">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.CommitEdit`
- `M:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)`

-->
