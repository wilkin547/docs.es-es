---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805122"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="f9e3c-101">Los adaptadores de flujo de WinRT no llaman a FlushAsync de manera automática al cerrarse</span><span class="sxs-lookup"><span data-stu-id="f9e3c-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f9e3c-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="f9e3c-102">Details</span></span>|<span data-ttu-id="f9e3c-103">En las aplicaciones de Microsoft Store, los adaptadores de secuencia de Windows Runtime ya no llaman al método FlushAsync desde el método Dispose.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>|
|<span data-ttu-id="f9e3c-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="f9e3c-104">Suggestion</span></span>|<span data-ttu-id="f9e3c-105">Este cambio debe ser transparente.</span><span class="sxs-lookup"><span data-stu-id="f9e3c-105">This change should be transparent.</span></span> <span data-ttu-id="f9e3c-106">Los desarrolladores pueden restaurar el comportamiento anterior escribiendo código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9e3c-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|<span data-ttu-id="f9e3c-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="f9e3c-107">Scope</span></span>|<span data-ttu-id="f9e3c-108">Transparente</span><span class="sxs-lookup"><span data-stu-id="f9e3c-108">Transparent</span></span>|
|<span data-ttu-id="f9e3c-109">Versión</span><span class="sxs-lookup"><span data-stu-id="f9e3c-109">Version</span></span>|<span data-ttu-id="f9e3c-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="f9e3c-110">4.5.1</span></span>|
|<span data-ttu-id="f9e3c-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="f9e3c-111">Type</span></span>|<span data-ttu-id="f9e3c-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f9e3c-112">Runtime</span></span>|
