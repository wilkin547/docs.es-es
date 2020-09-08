---
ms.openlocfilehash: 2b4f35fe15f806897e5e4d85ee774b2e4572d974
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497206"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="d263d-101">Los adaptadores de flujo de WinRT no llaman a FlushAsync de manera automática al cerrarse</span><span class="sxs-lookup"><span data-stu-id="d263d-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

#### <a name="details"></a><span data-ttu-id="d263d-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d263d-102">Details</span></span>

<span data-ttu-id="d263d-103">En las aplicaciones de Microsoft Store, los adaptadores de secuencia de Windows Runtime ya no llaman al método FlushAsync desde el método Dispose.</span><span class="sxs-lookup"><span data-stu-id="d263d-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d263d-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d263d-104">Suggestion</span></span>

<span data-ttu-id="d263d-105">Este cambio debe ser transparente.</span><span class="sxs-lookup"><span data-stu-id="d263d-105">This change should be transparent.</span></span> <span data-ttu-id="d263d-106">Los desarrolladores pueden restaurar el comportamiento anterior escribiendo código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d263d-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="d263d-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="d263d-107">Name</span></span>    | <span data-ttu-id="d263d-108">Valor</span><span class="sxs-lookup"><span data-stu-id="d263d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d263d-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d263d-109">Scope</span></span>   |<span data-ttu-id="d263d-110">Transparente</span><span class="sxs-lookup"><span data-stu-id="d263d-110">Transparent</span></span>|
|<span data-ttu-id="d263d-111">Versión</span><span class="sxs-lookup"><span data-stu-id="d263d-111">Version</span></span>|<span data-ttu-id="d263d-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="d263d-112">4.5.1</span></span>|
|<span data-ttu-id="d263d-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="d263d-113">Type</span></span>|<span data-ttu-id="d263d-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d263d-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d263d-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d263d-115">Affected APIs</span></span>

<span data-ttu-id="d263d-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="d263d-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
