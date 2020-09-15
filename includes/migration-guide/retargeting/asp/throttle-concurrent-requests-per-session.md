---
ms.openlocfilehash: b521f4163bf5bf4a369d0eec12dae503703a976e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614644"
---
### <a name="throttle-concurrent-requests-per-session"></a><span data-ttu-id="4df18-101">Límite de solicitudes simultáneas por sesión</span><span class="sxs-lookup"><span data-stu-id="4df18-101">Throttle concurrent requests per session</span></span>

#### <a name="details"></a><span data-ttu-id="4df18-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="4df18-102">Details</span></span>

<span data-ttu-id="4df18-103">En .NET Framework 4.6.2 y en versiones anteriores, ASP.NET ejecuta las solicitudes con el mismo Sessionid de manera secuencial y siempre emite el Sessionid mediante cookies de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4df18-103">In the .NET Framework 4.6.2 and earlier, ASP.NET executes requests with the same Sessionid sequentially, and ASP.NET always issues the Sessionid through cookies by default.</span></span> <span data-ttu-id="4df18-104">Si una página tarda mucho tiempo en responder, reducirá considerablemente el rendimiento del servidor simplemente presionando <kbd>F5</kbd> en el explorador.</span><span class="sxs-lookup"><span data-stu-id="4df18-104">If a page takes a long time to respond, it will significantly degrade server performance just by pressing <kbd>F5</kbd> on the browser.</span></span> <span data-ttu-id="4df18-105">En la corrección, se ha agregado un contador para realizar el seguimiento de las solicitudes en cola y finalizar las solicitudes cuando superen un límite especificado.</span><span class="sxs-lookup"><span data-stu-id="4df18-105">In the fix, we added a counter to track the queued requests and terminate the requests when they exceed a specified limit.</span></span> <span data-ttu-id="4df18-106">El valor predeterminado es 50.</span><span class="sxs-lookup"><span data-stu-id="4df18-106">The default value is 50.</span></span> <span data-ttu-id="4df18-107">Si se alcanza el límite, se registrará una advertencia en el registro de eventos y se podrá grabar una respuesta HTTP 500 en el registro de IIS.</span><span class="sxs-lookup"><span data-stu-id="4df18-107">If the limit is reached, a warning will be logged in the event log, and an HTTP 500 response may be recorded in the IIS log.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4df18-108">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="4df18-108">Suggestion</span></span>

<span data-ttu-id="4df18-109">Para restaurar el comportamiento anterior, puede agregar la siguiente configuración al archivo web.config para rechazar el nuevo comportamiento.</span><span class="sxs-lookup"><span data-stu-id="4df18-109">To restore the old behavior, you can add the following setting to your web.config file to opt out of the new behavior.</span></span>

```xml
<appSettings>
    <add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>
</appSettings>
```

| <span data-ttu-id="4df18-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="4df18-110">Name</span></span>    | <span data-ttu-id="4df18-111">Valor</span><span class="sxs-lookup"><span data-stu-id="4df18-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4df18-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="4df18-112">Scope</span></span>   | <span data-ttu-id="4df18-113">Borde</span><span class="sxs-lookup"><span data-stu-id="4df18-113">Edge</span></span>        |
| <span data-ttu-id="4df18-114">Versión</span><span class="sxs-lookup"><span data-stu-id="4df18-114">Version</span></span> | <span data-ttu-id="4df18-115">4.7</span><span class="sxs-lookup"><span data-stu-id="4df18-115">4.7</span></span>         |
| <span data-ttu-id="4df18-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="4df18-116">Type</span></span>    | <span data-ttu-id="4df18-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="4df18-117">Retargeting</span></span> |
