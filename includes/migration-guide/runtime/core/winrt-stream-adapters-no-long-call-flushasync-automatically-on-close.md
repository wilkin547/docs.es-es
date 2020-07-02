---
ms.openlocfilehash: 60937459b6f18e9abae87ad2dc97c3942325eedc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620596"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="50544-101">Los adaptadores de flujo de WinRT no llaman a FlushAsync de manera automática al cerrarse</span><span class="sxs-lookup"><span data-stu-id="50544-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

#### <a name="details"></a><span data-ttu-id="50544-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="50544-102">Details</span></span>

<span data-ttu-id="50544-103">En las aplicaciones de Microsoft Store, los adaptadores de secuencia de Windows Runtime ya no llaman al método FlushAsync desde el método Dispose.</span><span class="sxs-lookup"><span data-stu-id="50544-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="50544-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="50544-104">Suggestion</span></span>

<span data-ttu-id="50544-105">Este cambio debe ser transparente.</span><span class="sxs-lookup"><span data-stu-id="50544-105">This change should be transparent.</span></span> <span data-ttu-id="50544-106">Los desarrolladores pueden restaurar el comportamiento anterior escribiendo código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="50544-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="50544-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="50544-107">Name</span></span>    | <span data-ttu-id="50544-108">Valor</span><span class="sxs-lookup"><span data-stu-id="50544-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="50544-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="50544-109">Scope</span></span>   |<span data-ttu-id="50544-110">Transparente</span><span class="sxs-lookup"><span data-stu-id="50544-110">Transparent</span></span>|
|<span data-ttu-id="50544-111">Versión</span><span class="sxs-lookup"><span data-stu-id="50544-111">Version</span></span>|<span data-ttu-id="50544-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="50544-112">4.5.1</span></span>|
|<span data-ttu-id="50544-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="50544-113">Type</span></span>|<span data-ttu-id="50544-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="50544-114">Runtime</span></span>|
