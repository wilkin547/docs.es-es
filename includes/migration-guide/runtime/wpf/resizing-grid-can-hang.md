---
ms.openlocfilehash: 8dc1b4d94d01813a8124d1340b50fa78a9b157f8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497078"
---
### <a name="resizing-a-grid-can-hang"></a><span data-ttu-id="8dde0-101">El cambio de tamaño de una cuadrícula puede dejar de responder</span><span class="sxs-lookup"><span data-stu-id="8dde0-101">Resizing a Grid can hang</span></span>

#### <a name="details"></a><span data-ttu-id="8dde0-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8dde0-102">Details</span></span>

<span data-ttu-id="8dde0-103">Se puede producir un bucle infinito durante el diseño de un control <code>T:System.Windows.Controls.Grid</code> en las siguientes circunstancias:</span><span class="sxs-lookup"><span data-stu-id="8dde0-103">An infinite loop can occur during layout of a <code>T:System.Windows.Controls.Grid</code> under the following circumstances:</span></span><ul><li><span data-ttu-id="8dde0-104">Las definiciones de fila contienen dos filas \*, que declaran un valor MinHeight y un valor MaxHeight.</span><span class="sxs-lookup"><span data-stu-id="8dde0-104">Row definitions contain two \*-rows, both declaring a MinHeight and a MaxHeight.</span></span></li><li><span data-ttu-id="8dde0-105">El contenido de las filas \* no supera el valor MaxHeight correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8dde0-105">Content of the \*-rows doesn't exceed the corresponding MaxHeight</span></span></li><li><span data-ttu-id="8dde0-106">El alto disponible de la cuadrícula se supera con el primer valor MinHeight (más cualquier otra fila fija o automática).</span><span class="sxs-lookup"><span data-stu-id="8dde0-106">The Grid's available height is exceeded by the first MinHeight (plus any other fixed or Auto rows)</span></span></li><li><span data-ttu-id="8dde0-107">La aplicación tiene como destino .NET Framework 4.7 o admite el algoritmo de asignación de la versión 4.7 estableciendo <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code>.</span><span class="sxs-lookup"><span data-stu-id="8dde0-107">The app targets .NET Framework 4.7, or opts in to the 4.7 allocation algorithm by setting <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></span></span></li></ul><span data-ttu-id="8dde0-108">El bucle también se podría producir con más de dos filas o en el mismo caso para las columnas.</span><span class="sxs-lookup"><span data-stu-id="8dde0-108">The loop would also happen with more than two rows, or in the analogous case for columns.</span></span> <span data-ttu-id="8dde0-109">El problema se corrigió en .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="8dde0-109">The issue is fixed in .NET Framework 4.7.1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8dde0-110">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8dde0-110">Suggestion</span></span>

<span data-ttu-id="8dde0-111">Actualice a .NET Framework 4.7.1.</span><span class="sxs-lookup"><span data-stu-id="8dde0-111">Upgrade to .NET Framework 4.7.1.</span></span>  <span data-ttu-id="8dde0-112">Como alternativa, si ya no necesita el algoritmo de asignación de la versión 4.7, puede usar la opción de configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="8dde0-112">Alternatively, if you don't need the 4.7 allocation algorithm you can use the following configuration setting:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="8dde0-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="8dde0-113">Name</span></span>    | <span data-ttu-id="8dde0-114">Valor</span><span class="sxs-lookup"><span data-stu-id="8dde0-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8dde0-115">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8dde0-115">Scope</span></span>   |<span data-ttu-id="8dde0-116">Borde</span><span class="sxs-lookup"><span data-stu-id="8dde0-116">Edge</span></span>|
|<span data-ttu-id="8dde0-117">Versión</span><span class="sxs-lookup"><span data-stu-id="8dde0-117">Version</span></span>|<span data-ttu-id="8dde0-118">4.7</span><span class="sxs-lookup"><span data-stu-id="8dde0-118">4.7</span></span>|
|<span data-ttu-id="8dde0-119">Tipo</span><span class="sxs-lookup"><span data-stu-id="8dde0-119">Type</span></span>|<span data-ttu-id="8dde0-120">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8dde0-120">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8dde0-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8dde0-121">Affected APIs</span></span>

<span data-ttu-id="8dde0-122">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="8dde0-122">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
