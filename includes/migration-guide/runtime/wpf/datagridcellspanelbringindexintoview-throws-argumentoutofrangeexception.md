---
ms.openlocfilehash: d78d083b16ac034c6c393dbc0f6094ee4c6c63c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622383"
---
### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a><span data-ttu-id="531cd-101">DataGridCellsPanel.BringIndexIntoView inicia una excepción ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="531cd-101">DataGridCellsPanel.BringIndexIntoView throws ArgumentOutOfRangeException</span></span>

#### <a name="details"></a><span data-ttu-id="531cd-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="531cd-102">Details</span></span>

<span data-ttu-id="531cd-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> funcionará de forma asíncrona cuando se habilite la virtualización de columnas pero el ancho de las columnas todavía no se haya determinado.</span><span class="sxs-lookup"><span data-stu-id="531cd-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> will work asynchronously when column virtualization is enabled but the column widths have not yet been determined.</span></span>  <span data-ttu-id="531cd-104">Si se quitan las columnas antes de que se complete la operación asíncrona, se puede iniciar una excepción <xref:System.ArgumentOutOfRangeException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="531cd-104">If columns are removed before the asynchronous work happens, an <xref:System.ArgumentOutOfRangeException?displayProperty=fullName> can occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="531cd-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="531cd-105">Suggestion</span></span>

<span data-ttu-id="531cd-106">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="531cd-106">Any one of the following:</span></span><ol><li><span data-ttu-id="531cd-107">Actualice a .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="531cd-107">Upgrade to .NET Framework 4.7.</span></span></li><li><span data-ttu-id="531cd-108">Instale la revisión de reparación más reciente para .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="531cd-108">Install the latest servicing patch for .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="531cd-109">Evite quitar las columnas hasta que se haya completado la respuesta asíncrona para <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)>.</span><span class="sxs-lookup"><span data-stu-id="531cd-109">Avoid removing columns until the asynchronous response to <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> has completed.</span></span></li></ol>

| <span data-ttu-id="531cd-110">Nombre</span><span class="sxs-lookup"><span data-stu-id="531cd-110">Name</span></span>    | <span data-ttu-id="531cd-111">Valor</span><span class="sxs-lookup"><span data-stu-id="531cd-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="531cd-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="531cd-112">Scope</span></span>   |<span data-ttu-id="531cd-113">Borde</span><span class="sxs-lookup"><span data-stu-id="531cd-113">Edge</span></span>|
|<span data-ttu-id="531cd-114">Versión</span><span class="sxs-lookup"><span data-stu-id="531cd-114">Version</span></span>|<span data-ttu-id="531cd-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="531cd-115">4.6.2</span></span>|
|<span data-ttu-id="531cd-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="531cd-116">Type</span></span>|<span data-ttu-id="531cd-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="531cd-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="531cd-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="531cd-118">Affected APIs</span></span>

-<xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|
