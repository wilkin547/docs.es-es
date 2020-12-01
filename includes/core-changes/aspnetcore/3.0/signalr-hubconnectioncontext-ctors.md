---
ms.openlocfilehash: 6be98e7ced6608ba0793c635adfe61c8b1a7e9d9
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032873"
---
### <a name="signalr-hubconnectioncontext-constructors-changed"></a><span data-ttu-id="74be0-101">SignalR: se han cambiado los constructores de HubConnectionContext</span><span class="sxs-lookup"><span data-stu-id="74be0-101">SignalR: HubConnectionContext constructors changed</span></span>

<span data-ttu-id="74be0-102">Los constructores de `HubConnectionContext` de SignalR han cambiado para aceptar un tipo de opciones, en lugar de varios parámetros, para agregar opciones con garantía de futuro.</span><span class="sxs-lookup"><span data-stu-id="74be0-102">SignalR's `HubConnectionContext` constructors changed to accept an options type, rather than multiple parameters, to future-proof adding options.</span></span> <span data-ttu-id="74be0-103">Este cambio reemplaza dos constructores por un único constructor que acepta un tipo de opciones.</span><span class="sxs-lookup"><span data-stu-id="74be0-103">This change replaces two constructors with a single constructor that accepts an options type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="74be0-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="74be0-104">Version introduced</span></span>

<span data-ttu-id="74be0-105">3.0</span><span class="sxs-lookup"><span data-stu-id="74be0-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="74be0-106">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="74be0-106">Old behavior</span></span>

<span data-ttu-id="74be0-107">`HubConnectionContext` tiene dos constructores:</span><span class="sxs-lookup"><span data-stu-id="74be0-107">`HubConnectionContext` has two constructors:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory);
public HubConnectionContext(ConnectionContext connectionContext, TimeSpan keepAliveInterval, ILoggerFactory loggerFactory, TimeSpan clientTimeoutInterval);
```

#### <a name="new-behavior"></a><span data-ttu-id="74be0-108">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="74be0-108">New behavior</span></span>

<span data-ttu-id="74be0-109">Los dos constructores se han quitado y se han reemplazado por uno:</span><span class="sxs-lookup"><span data-stu-id="74be0-109">The two constructors were removed and replaced with one constructor:</span></span>

```csharp
public HubConnectionContext(ConnectionContext connectionContext, HubConnectionContextOptions contextOptions, ILoggerFactory loggerFactory)
```

#### <a name="reason-for-change"></a><span data-ttu-id="74be0-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="74be0-110">Reason for change</span></span>

<span data-ttu-id="74be0-111">El nuevo constructor usa un nuevo objeto de opciones.</span><span class="sxs-lookup"><span data-stu-id="74be0-111">The new constructor uses a new options object.</span></span> <span data-ttu-id="74be0-112">Por tanto, las características de `HubConnectionContext` se pueden expandir en el futuro sin crear más constructores y cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="74be0-112">Consequently, the features of `HubConnectionContext` can be expanded in the future without making more constructors and breaking changes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="74be0-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="74be0-113">Recommended action</span></span>

<span data-ttu-id="74be0-114">En lugar de usar el constructor siguiente:</span><span class="sxs-lookup"><span data-stu-id="74be0-114">Instead of using the following constructor:</span></span>

```csharp
HubConnectionContext connectionContext = new HubConnectionContext(
    connectionContext,
    keepAliveInterval: TimeSpan.FromSeconds(15),
    loggerFactory,
    clientTimeoutInterval: TimeSpan.FromSeconds(15));
```

<span data-ttu-id="74be0-115">Use el constructor siguiente:</span><span class="sxs-lookup"><span data-stu-id="74be0-115">Use the following constructor:</span></span>

```csharp
HubConnectionContextOptions contextOptions = new HubConnectionContextOptions()
{
    KeepAliveInterval = TimeSpan.FromSeconds(15),
    ClientTimeoutInterval = TimeSpan.FromSeconds(15)
};
HubConnectionContext connectionContext = new HubConnectionContext(connectionContext, contextOptions, loggerFactory);
```

#### <a name="category"></a><span data-ttu-id="74be0-116">Categoría</span><span class="sxs-lookup"><span data-stu-id="74be0-116">Category</span></span>

<span data-ttu-id="74be0-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="74be0-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="74be0-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="74be0-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)>
- <xref:Microsoft.AspNetCore.SignalR.HubConnectionContext.%23ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory)`
- `M:Microsoft.AspNetCore.SignalR.HubConnectionContext.#ctor(Microsoft.AspNetCore.Connections.ConnectionContext,System.TimeSpan,Microsoft.Extensions.Logging.ILoggerFactory,System.TimeSpan)`

-->
