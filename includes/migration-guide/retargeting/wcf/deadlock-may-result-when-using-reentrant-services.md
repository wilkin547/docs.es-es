---
ms.openlocfilehash: dd7d3e445772e4b5ec148576ccd1374d56e251bd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614785"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a><span data-ttu-id="183e6-101">El uso de servicios reentrantes puede producir un interbloqueo</span><span class="sxs-lookup"><span data-stu-id="183e6-101">Deadlock may result when using Reentrant services</span></span>

#### <a name="details"></a><span data-ttu-id="183e6-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="183e6-102">Details</span></span>

<span data-ttu-id="183e6-103">Se puede producir un interbloqueo en un servicio reentrante, lo que restringe las instancias del servicio a un subproceso de ejecución a la vez.</span><span class="sxs-lookup"><span data-stu-id="183e6-103">A deadlock may result in a Reentrant service, which restricts instances of the service to one thread of execution at a time.</span></span> <span data-ttu-id="183e6-104">Los servicios propensos a sufrir este problema tendrán el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> siguiente en su código:</span><span class="sxs-lookup"><span data-stu-id="183e6-104">Services prone to encounter this problem will have the following <xref:System.ServiceModel.ServiceBehaviorAttribute> in their code:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a><span data-ttu-id="183e6-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="183e6-105">Suggestion</span></span>

<span data-ttu-id="183e6-106">Para solucionar este problema, puede seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="183e6-106">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="183e6-107">Establezca el modo de simultaneidad del servicio en <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> o &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;.</span><span class="sxs-lookup"><span data-stu-id="183e6-107">Set the service's concurrency mode to <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> or &lt;System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType&gt;.</span></span> <span data-ttu-id="183e6-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="183e6-108">For example:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- <span data-ttu-id="183e6-109">Instale la actualización más reciente de .NET Framework 4.6.2 o actualice a una versión posterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="183e6-109">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="183e6-110">Esto deshabilita el flujo de <xref:System.Threading.ExecutionContext> en <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="183e6-110">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>.</span></span> <span data-ttu-id="183e6-111">Este comportamiento se puede configurar; equivale a agregar la configuración de aplicación siguiente al archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="183e6-111">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

<span data-ttu-id="183e6-112">El valor de `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` nunca se debe establecer en `false` para los servicios reentrantes.</span><span class="sxs-lookup"><span data-stu-id="183e6-112">The value of `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` should never be set to `false` for Reentrant services.</span></span>

| <span data-ttu-id="183e6-113">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="183e6-113">Name</span></span>    | <span data-ttu-id="183e6-114">Valor</span><span class="sxs-lookup"><span data-stu-id="183e6-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="183e6-115">Ámbito</span><span class="sxs-lookup"><span data-stu-id="183e6-115">Scope</span></span>   | <span data-ttu-id="183e6-116">Secundaria</span><span class="sxs-lookup"><span data-stu-id="183e6-116">Minor</span></span>       |
| <span data-ttu-id="183e6-117">Versión</span><span class="sxs-lookup"><span data-stu-id="183e6-117">Version</span></span> | <span data-ttu-id="183e6-118">4.6.2</span><span class="sxs-lookup"><span data-stu-id="183e6-118">4.6.2</span></span>       |
| <span data-ttu-id="183e6-119">Tipo</span><span class="sxs-lookup"><span data-stu-id="183e6-119">Type</span></span>    | <span data-ttu-id="183e6-120">Redestinación</span><span class="sxs-lookup"><span data-stu-id="183e6-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="183e6-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="183e6-121">Affected APIs</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
