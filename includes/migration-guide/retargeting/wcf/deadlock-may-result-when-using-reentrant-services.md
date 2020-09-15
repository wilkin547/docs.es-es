---
ms.openlocfilehash: f61cf21f9f30662cc8e383bb3aeb5c642f1665b8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496671"
---
### <a name="deadlock-may-result-when-using-reentrant-services"></a><span data-ttu-id="5c57f-101">El uso de servicios reentrantes puede producir un interbloqueo</span><span class="sxs-lookup"><span data-stu-id="5c57f-101">Deadlock may result when using Reentrant services</span></span>

#### <a name="details"></a><span data-ttu-id="5c57f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="5c57f-102">Details</span></span>

<span data-ttu-id="5c57f-103">Se puede producir un interbloqueo en un servicio reentrante, lo que restringe las instancias del servicio a un subproceso de ejecución a la vez.</span><span class="sxs-lookup"><span data-stu-id="5c57f-103">A deadlock may result in a Reentrant service, which restricts instances of the service to one thread of execution at a time.</span></span> <span data-ttu-id="5c57f-104">Los servicios propensos a sufrir este problema tendrán el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute> siguiente en su código:</span><span class="sxs-lookup"><span data-stu-id="5c57f-104">Services prone to encounter this problem will have the following <xref:System.ServiceModel.ServiceBehaviorAttribute> in their code:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

#### <a name="suggestion"></a><span data-ttu-id="5c57f-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="5c57f-105">Suggestion</span></span>

<span data-ttu-id="5c57f-106">Para solucionar este problema, puede seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5c57f-106">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="5c57f-107">Establezca el modo de simultaneidad del servicio en <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> o <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c57f-107">Set the service's concurrency mode to <xref:System.ServiceModel.ConcurrencyMode.Single?displayProperty=nameWithType> or <xref:System.ServiceModel.ConcurrencyMode.Multiple?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5c57f-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5c57f-108">For example:</span></span>

```csharp
[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Reentrant)]
```

- <span data-ttu-id="5c57f-109">Instale la actualización más reciente de .NET Framework 4.6.2 o actualice a una versión posterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5c57f-109">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="5c57f-110">Esto deshabilita el flujo de <xref:System.Threading.ExecutionContext> en <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5c57f-110">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5c57f-111">Este comportamiento se puede configurar; equivale a agregar la configuración de aplicación siguiente al archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="5c57f-111">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

```xml
<appSettings>
  <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
</appSettings>
```

<span data-ttu-id="5c57f-112">El valor de `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` nunca se debe establecer en `false` para los servicios reentrantes.</span><span class="sxs-lookup"><span data-stu-id="5c57f-112">The value of `Switch.System.ServiceModel.DisableOperationContextAsyncFlow` should never be set to `false` for Reentrant services.</span></span>

| <span data-ttu-id="5c57f-113">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="5c57f-113">Name</span></span>    | <span data-ttu-id="5c57f-114">Valor</span><span class="sxs-lookup"><span data-stu-id="5c57f-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5c57f-115">Ámbito</span><span class="sxs-lookup"><span data-stu-id="5c57f-115">Scope</span></span>   | <span data-ttu-id="5c57f-116">Secundaria</span><span class="sxs-lookup"><span data-stu-id="5c57f-116">Minor</span></span>       |
| <span data-ttu-id="5c57f-117">Versión</span><span class="sxs-lookup"><span data-stu-id="5c57f-117">Version</span></span> | <span data-ttu-id="5c57f-118">4.6.2</span><span class="sxs-lookup"><span data-stu-id="5c57f-118">4.6.2</span></span>       |
| <span data-ttu-id="5c57f-119">Tipo</span><span class="sxs-lookup"><span data-stu-id="5c57f-119">Type</span></span>    | <span data-ttu-id="5c57f-120">Redestinación</span><span class="sxs-lookup"><span data-stu-id="5c57f-120">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="5c57f-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5c57f-121">Affected APIs</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant?displayProperty=nameWithType>
