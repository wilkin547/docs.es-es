---
ms.openlocfilehash: 519de92ca4201d199941afe6382ddf9fc480fbbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614776"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a><span data-ttu-id="6cff6-101">ServiceBase no propaga las excepciones OnStart</span><span class="sxs-lookup"><span data-stu-id="6cff6-101">ServiceBase doesn't propagate OnStart exceptions</span></span>

#### <a name="details"></a><span data-ttu-id="6cff6-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="6cff6-102">Details</span></span>

<span data-ttu-id="6cff6-103">En .NET Framework 4.7 y versiones anteriores, las excepciones que se producen al inicio del servicio no se propagan al autor de la llamada de <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6cff6-103">In the .NET Framework 4.7 and earlier versions, exceptions thrown on service startup are not propagated to the caller of <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.</span></span><br/><span data-ttu-id="6cff6-104">A partir de las aplicaciones que tienen como destino .NET Framework 4.7.1, el tiempo de ejecución propaga las excepciones a <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> para los servicios que no se pueden iniciar.</span><span class="sxs-lookup"><span data-stu-id="6cff6-104">Starting with applications that target the .NET Framework 4.7.1, the runtime propagates exceptions to <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> for services that fail to start.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6cff6-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="6cff6-105">Suggestion</span></span>

<span data-ttu-id="6cff6-106">Durante el inicio del servicio, si hay una excepción, se propaga.</span><span class="sxs-lookup"><span data-stu-id="6cff6-106">On service start, if there is an exception, that exception will be propagated.</span></span> <span data-ttu-id="6cff6-107">Esto debería ayudar a diagnosticar los casos en los que no se pueden iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="6cff6-107">This should help diagnose cases where services fail to start.</span></span> <br/><span data-ttu-id="6cff6-108">Si no quiere este comportamiento, puede rechazarlo mediante la adición del elemento &lt;AppContextSwitchOverrides&gt; siguiente a la sección &lt;runtime&gt; del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="6cff6-108">If this behavior is undesirable, you can opt out of it by adding the following &lt;AppContextSwitchOverrides&gt; element to the &lt;runtime&gt; section of your application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true" />
```

<span data-ttu-id="6cff6-109">Si la aplicación está destinada a una versión anterior a 4.7.1 pero quiere tener este comportamiento, agregue el elemento &lt;AppContextSwitchOverrides&gt; siguiente a la sección &lt;runtime&gt; del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="6cff6-109">If your application targets an earlier version than 4.7.1 but you want to have this behavior, add the following &lt;AppContextSwitchOverrides&gt; element to the &lt;runtime&gt; section of your application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false" />
```

| <span data-ttu-id="6cff6-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="6cff6-110">Name</span></span>    | <span data-ttu-id="6cff6-111">Valor</span><span class="sxs-lookup"><span data-stu-id="6cff6-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6cff6-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="6cff6-112">Scope</span></span>   | <span data-ttu-id="6cff6-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="6cff6-113">Minor</span></span>       |
| <span data-ttu-id="6cff6-114">Versión</span><span class="sxs-lookup"><span data-stu-id="6cff6-114">Version</span></span> | <span data-ttu-id="6cff6-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="6cff6-115">4.7.1</span></span>       |
| <span data-ttu-id="6cff6-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="6cff6-116">Type</span></span>    | <span data-ttu-id="6cff6-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="6cff6-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6cff6-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6cff6-118">Affected APIs</span></span>

- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType>
- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType>
