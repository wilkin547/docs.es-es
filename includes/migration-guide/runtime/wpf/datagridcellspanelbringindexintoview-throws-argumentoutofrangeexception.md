---
ms.openlocfilehash: 961ca545560a53fc2c1d52722b68ae460de66877
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496247"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a><span data-ttu-id="c5e9b-101">DataGridCellsPanel.BringIndexIntoView inicia una excepción ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="c5e9b-101">DataGridCellsPanel.BringIndexIntoView throws ArgumentOutOfRangeException</span></span>

#### <a name="details"></a><span data-ttu-id="c5e9b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="c5e9b-102">Details</span></span>

<span data-ttu-id="c5e9b-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> funcionará de forma asíncrona cuando se habilite la virtualización de columnas pero el ancho de las columnas todavía no se haya determinado.</span><span class="sxs-lookup"><span data-stu-id="c5e9b-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> will work asynchronously when column virtualization is enabled but the column widths have not yet been determined.</span></span>  <span data-ttu-id="c5e9b-104">Si se quitan las columnas antes de que se complete la operación asíncrona, se puede iniciar una excepción <xref:System.ArgumentOutOfRangeException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="c5e9b-104">If columns are removed before the asynchronous work happens, an <xref:System.ArgumentOutOfRangeException?displayProperty=fullName> can occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c5e9b-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="c5e9b-105">Suggestion</span></span>

<span data-ttu-id="c5e9b-106">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c5e9b-106">Any one of the following:</span></span><ol><li><span data-ttu-id="c5e9b-107">Actualice a .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="c5e9b-107">Upgrade to .NET Framework 4.7.</span></span></li><li><span data-ttu-id="c5e9b-108">Instale la revisión de reparación más reciente para .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="c5e9b-108">Install the latest servicing patch for .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="c5e9b-109">Evite quitar las columnas hasta que se haya completado la respuesta asíncrona para <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</span><span class="sxs-lookup"><span data-stu-id="c5e9b-109">Avoid removing columns until the asynchronous response to <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> has completed.</span></span></li></ol>

| <span data-ttu-id="c5e9b-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="c5e9b-110">Name</span></span>    | <span data-ttu-id="c5e9b-111">Valor</span><span class="sxs-lookup"><span data-stu-id="c5e9b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c5e9b-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="c5e9b-112">Scope</span></span>   |<span data-ttu-id="c5e9b-113">Borde</span><span class="sxs-lookup"><span data-stu-id="c5e9b-113">Edge</span></span>|
|<span data-ttu-id="c5e9b-114">Versión</span><span class="sxs-lookup"><span data-stu-id="c5e9b-114">Version</span></span>|<span data-ttu-id="c5e9b-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="c5e9b-115">4.6.2</span></span>|
|<span data-ttu-id="c5e9b-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="c5e9b-116">Type</span></span>|<span data-ttu-id="c5e9b-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c5e9b-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c5e9b-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c5e9b-118">Affected APIs</span></span>

- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)`
- `M:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)`

-->
