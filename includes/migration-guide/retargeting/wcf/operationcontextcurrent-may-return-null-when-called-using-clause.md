---
ms.openlocfilehash: d25c14f93da5fe8acf06269554fed30ddc6bc95d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614752"
---
### <a name="operationcontextcurrent-may-return-null-when-called-in-a-using-clause"></a><span data-ttu-id="5812f-101">Es posible que OperationContext.Current devuelva NULL cuando se llama en una cláusula using.</span><span class="sxs-lookup"><span data-stu-id="5812f-101">OperationContext.Current may return null when called in a using clause</span></span>

#### <a name="details"></a><span data-ttu-id="5812f-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="5812f-102">Details</span></span>

<span data-ttu-id="5812f-103">Es posible que <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> devuelva `null` y que se inicie una excepción <xref:System.NullReferenceException> si todas las condiciones siguientes son verdaderas:</span><span class="sxs-lookup"><span data-stu-id="5812f-103"><xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> may return `null` and a <xref:System.NullReferenceException> may result if all of the following conditions are true:</span></span>

- <span data-ttu-id="5812f-104">Se recupera el valor de la propiedad <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> en un método que devuelve una <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="5812f-104">You retrieve the value of the <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> property in a method that returns a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span>
- <span data-ttu-id="5812f-105">Se crea una instancia del objeto <xref:System.ServiceModel.OperationContextScope> en una cláusula `using`.</span><span class="sxs-lookup"><span data-stu-id="5812f-105">You instantiate the <xref:System.ServiceModel.OperationContextScope> object in a `using` clause.</span></span>
- <span data-ttu-id="5812f-106">Se recupera el valor de la propiedad <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> dentro de `using statement`.</span><span class="sxs-lookup"><span data-stu-id="5812f-106">You retrieve the value of the <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> property within the `using statement`.</span></span> <span data-ttu-id="5812f-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5812f-107">For example:</span></span>

```csharp
using (new OperationContextScope(OperationContext.Current))
{
    // OperationContext.Current is null.
    OperationContext context = OperationContext.Current;

    // ...
}
```

#### <a name="suggestion"></a><span data-ttu-id="5812f-108">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="5812f-108">Suggestion</span></span>

<span data-ttu-id="5812f-109">Para solucionar este problema, puede seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="5812f-109">To address this issue, you can do the following:</span></span>

- <span data-ttu-id="5812f-110">Modifique el código como se indica aquí para crear una instancia de un nuevo objeto <xref:System.ServiceModel.OperationContext.Current%2A> que no sea `null`:</span><span class="sxs-lookup"><span data-stu-id="5812f-110">Modify your code as follows to instantiate a new non- `null` <xref:System.ServiceModel.OperationContext.Current%2A> object:</span></span>

    ```csharp
    OperationContext ocx = OperationContext.Current;
    using (new OperationContextScope(OperationContext.Current))
    {
        OperationContext.Current = new OperationContext(ocx.Channel);

        // ...
    }
    ```

- <span data-ttu-id="5812f-111">Instale la actualización más reciente de .NET Framework 4.6.2 o actualice a una versión posterior de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5812f-111">Install the latest update to the .NET Framework 4.6.2, or upgrade to a later version of the .NET Framework.</span></span> <span data-ttu-id="5812f-112">Esto deshabilita el flujo del <xref:System.Threading.ExecutionContext> en <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> y restaura el comportamiento de las aplicaciones de WCF de .NET Framework 4.6.1 y versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="5812f-112">This disables the flow of the <xref:System.Threading.ExecutionContext> in <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType> and restores the behavior of WCF applications in the .NET Framework 4.6.1 and earlier versions.</span></span> <span data-ttu-id="5812f-113">Este comportamiento se puede configurar; equivale a agregar la configuración de aplicación siguiente al archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="5812f-113">This behavior is configurable; it is equivalent to adding the following app setting to your configuration file:</span></span>

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="true" />
    </appSettings>
    ```

    <span data-ttu-id="5812f-114">Si no quiere este cambio y la aplicación depende del flujo del contexto de ejecución entre los contextos de operación, puede habilitar su flujo de esta manera:</span><span class="sxs-lookup"><span data-stu-id="5812f-114">If this change is undesirable and your application depends on execution context flowing between operation contexts, you can enable its flow as follows:</span></span>

    ```xml
    <appSettings>
      <add key="Switch.System.ServiceModel.DisableOperationContextAsyncFlow" value="false" />
    </appSettings>
    ```

| <span data-ttu-id="5812f-115">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="5812f-115">Name</span></span>    | <span data-ttu-id="5812f-116">Valor</span><span class="sxs-lookup"><span data-stu-id="5812f-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5812f-117">Ámbito</span><span class="sxs-lookup"><span data-stu-id="5812f-117">Scope</span></span>   | <span data-ttu-id="5812f-118">Borde</span><span class="sxs-lookup"><span data-stu-id="5812f-118">Edge</span></span>        |
| <span data-ttu-id="5812f-119">Versión</span><span class="sxs-lookup"><span data-stu-id="5812f-119">Version</span></span> | <span data-ttu-id="5812f-120">4.6.2</span><span class="sxs-lookup"><span data-stu-id="5812f-120">4.6.2</span></span>       |
| <span data-ttu-id="5812f-121">Tipo</span><span class="sxs-lookup"><span data-stu-id="5812f-121">Type</span></span>    | <span data-ttu-id="5812f-122">Redestinación</span><span class="sxs-lookup"><span data-stu-id="5812f-122">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="5812f-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5812f-123">Affected APIs</span></span>

- <xref:System.ServiceModel.OperationContext.Current?displayProperty=nameWithType>
