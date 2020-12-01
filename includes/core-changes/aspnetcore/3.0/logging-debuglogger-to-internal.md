---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032821"
---
### <a name="logging-debuglogger-class-made-internal"></a><span data-ttu-id="5698c-101">Registro: la clase DebugLogger se ha convertido en interna</span><span class="sxs-lookup"><span data-stu-id="5698c-101">Logging: DebugLogger class made internal</span></span>

<span data-ttu-id="5698c-102">Antes de ASP.NET Core 3.0, el modificador de acceso de `DebugLogger` era `public`.</span><span class="sxs-lookup"><span data-stu-id="5698c-102">Prior to ASP.NET Core 3.0, `DebugLogger`'s access modifier was `public`.</span></span> <span data-ttu-id="5698c-103">En ASP.NET Core 3.0, el modificador de acceso se ha cambiado a `internal`.</span><span class="sxs-lookup"><span data-stu-id="5698c-103">In ASP.NET Core 3.0, the access modifier changed to `internal`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5698c-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5698c-104">Version introduced</span></span>

<span data-ttu-id="5698c-105">3.0</span><span class="sxs-lookup"><span data-stu-id="5698c-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="5698c-106">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="5698c-106">Reason for change</span></span>

<span data-ttu-id="5698c-107">El cambio se realiza para:</span><span class="sxs-lookup"><span data-stu-id="5698c-107">The change is being made to:</span></span>

* <span data-ttu-id="5698c-108">Aplicar la coherencia con otras implementaciones de registrador como `ConsoleLogger`.</span><span class="sxs-lookup"><span data-stu-id="5698c-108">Enforce consistency with other logger implementations such as `ConsoleLogger`.</span></span>
* <span data-ttu-id="5698c-109">Reducir la superficie de la API.</span><span class="sxs-lookup"><span data-stu-id="5698c-109">Reduce the API surface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5698c-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="5698c-110">Recommended action</span></span>

<span data-ttu-id="5698c-111">Use el método de extensión <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> de `ILoggingBuilder` para habilitar el registro de depuración.</span><span class="sxs-lookup"><span data-stu-id="5698c-111">Use the <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> `ILoggingBuilder` extension method to enable debug logging.</span></span> <span data-ttu-id="5698c-112"><xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> también sigue siendo `public` en caso de que el servicio se tenga que registrar de forma manual.</span><span class="sxs-lookup"><span data-stu-id="5698c-112"><xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> is also still `public` in the event the service needs to be registered manually.</span></span>

#### <a name="category"></a><span data-ttu-id="5698c-113">Categoría</span><span class="sxs-lookup"><span data-stu-id="5698c-113">Category</span></span>

<span data-ttu-id="5698c-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5698c-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5698c-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5698c-115">Affected APIs</span></span>

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->
