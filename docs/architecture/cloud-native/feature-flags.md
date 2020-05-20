---
title: Marcas de característica
description: Implementar marcas de características en aplicaciones nativas en la nube que aprovechan App de Azure configuración
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 607bd14a415a25b382f550e697542cf749a21772
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614076"
---
# <a name="feature-flags"></a><span data-ttu-id="bb569-103">Marcas de característica</span><span class="sxs-lookup"><span data-stu-id="bb569-103">Feature flags</span></span>

<span data-ttu-id="bb569-104">En el capítulo 1, afirmamos que la nube nativa es mucho más rápida y ágil.</span><span class="sxs-lookup"><span data-stu-id="bb569-104">In chapter 1, we affirmed that cloud native is much about speed and agility.</span></span> <span data-ttu-id="bb569-105">Los usuarios esperan una capacidad de respuesta rápida, características innovadoras y sin tiempo de inactividad.</span><span class="sxs-lookup"><span data-stu-id="bb569-105">Users expect rapid responsiveness, innovative features, and zero downtime.</span></span> <span data-ttu-id="bb569-106">`Feature flags`son una técnica de implementación moderna que ayuda a aumentar la agilidad de las aplicaciones nativas en la nube.</span><span class="sxs-lookup"><span data-stu-id="bb569-106">`Feature flags` are a modern deployment technique that helps increase agility for cloud-native applications.</span></span> <span data-ttu-id="bb569-107">Permiten implementar nuevas características en un entorno de producción, pero restringen su disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="bb569-107">They enable you to deploy new features into a production environment, but restrict their availability.</span></span> <span data-ttu-id="bb569-108">Con el gesto de un conmutador, puede activar una nueva característica para usuarios específicos sin necesidad de reiniciar la aplicación ni implementar código nuevo.</span><span class="sxs-lookup"><span data-stu-id="bb569-108">With the flick of a switch, you can activate a new feature for specific users without restarting the app or deploying new code.</span></span> <span data-ttu-id="bb569-109">Separan la versión de las nuevas características de la implementación del código.</span><span class="sxs-lookup"><span data-stu-id="bb569-109">They separate the release of new features from their code deployment.</span></span>

<span data-ttu-id="bb569-110">Las marcas de características se basan en la lógica condicional que controla la visibilidad de la funcionalidad de los usuarios en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="bb569-110">Feature flags are built upon conditional logic that control visibility of functionality for users at runtime.</span></span> <span data-ttu-id="bb569-111">En los sistemas modernos nativos en la nube, es habitual implementar nuevas características en producción pronto, pero probarlas con un público limitado.</span><span class="sxs-lookup"><span data-stu-id="bb569-111">In modern cloud-native systems, it's common to deploy new features into production early, but test them with a limited audience.</span></span> <span data-ttu-id="bb569-112">A medida que aumenta la confianza, la característica se puede implementar incrementalmente en audiencias más amplias.</span><span class="sxs-lookup"><span data-stu-id="bb569-112">As confidence increases, the feature can be incrementally rolled out to wider audiences.</span></span>

<span data-ttu-id="bb569-113">Otros casos de uso de las marcas de características son:</span><span class="sxs-lookup"><span data-stu-id="bb569-113">Other use cases for feature flags include:</span></span>

- <span data-ttu-id="bb569-114">Restrinja la funcionalidad Premium a grupos de clientes específicos dispuestos a pagar mayores tarifas de suscripción.</span><span class="sxs-lookup"><span data-stu-id="bb569-114">Restrict premium functionality to specific customer groups willing to pay higher subscription fees.</span></span>
- <span data-ttu-id="bb569-115">Estabilice un sistema mediante la desactivación rápida de una característica problemática, evitando los riesgos de una reversión o de una revisión inmediata.</span><span class="sxs-lookup"><span data-stu-id="bb569-115">Stabilize a system by quickly deactivating a problem feature, avoiding the risks of a rollback or immediate hotfix.</span></span>
- <span data-ttu-id="bb569-116">Deshabilite una característica opcional con un alto consumo de recursos durante períodos de uso máximo.</span><span class="sxs-lookup"><span data-stu-id="bb569-116">Disable an optional feature with high resource consumption during peak usage periods.</span></span>
- <span data-ttu-id="bb569-117">Lleve `experimental feature releases` a los pequeños segmentos de usuario para validar la viabilidad y popularidad.</span><span class="sxs-lookup"><span data-stu-id="bb569-117">Conduct `experimental feature releases` to small user segments to validate feasibility and popularity.</span></span>

<span data-ttu-id="bb569-118">Las marcas de características también fomentan el `trunk-based` desarrollo.</span><span class="sxs-lookup"><span data-stu-id="bb569-118">Feature flags also promote `trunk-based` development.</span></span> <span data-ttu-id="bb569-119">Es un modelo de bifurcación de control de código fuente en el que los desarrolladores colaboran en características de una sola rama.</span><span class="sxs-lookup"><span data-stu-id="bb569-119">It's a source-control branching model where developers collaborate on features in a single branch.</span></span> <span data-ttu-id="bb569-120">El enfoque minimiza el riesgo y la complejidad de combinar grandes cantidades de ramas de características de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="bb569-120">The approach minimizes the risk and complexity of merging large numbers of long-running feature branches.</span></span> <span data-ttu-id="bb569-121">Las características no estarán disponibles hasta que se activen.</span><span class="sxs-lookup"><span data-stu-id="bb569-121">Features are unavailable until activated.</span></span>

## <a name="implementing-feature-flags"></a><span data-ttu-id="bb569-122">Implementar marcas de características</span><span class="sxs-lookup"><span data-stu-id="bb569-122">Implementing feature flags</span></span>

<span data-ttu-id="bb569-123">En esencia, una marca de características es una referencia a un simple `decision object` .</span><span class="sxs-lookup"><span data-stu-id="bb569-123">At its core, a feature flag is a reference to a simple `decision object`.</span></span> <span data-ttu-id="bb569-124">Devuelve un estado booleano de `on` o `off` .</span><span class="sxs-lookup"><span data-stu-id="bb569-124">It returns a Boolean state of `on` or `off`.</span></span> <span data-ttu-id="bb569-125">Normalmente, la marca contiene un bloque de código que encapsula una funcionalidad de característica.</span><span class="sxs-lookup"><span data-stu-id="bb569-125">The flag typically wraps a block of code that encapsulates a feature capability.</span></span> <span data-ttu-id="bb569-126">El estado de la marca determina si ese bloque de código se ejecuta para un usuario determinado.</span><span class="sxs-lookup"><span data-stu-id="bb569-126">The state of the flag determines whether that code block executes for a given user.</span></span> <span data-ttu-id="bb569-127">En la figura 10-11 se muestra la implementación de.</span><span class="sxs-lookup"><span data-stu-id="bb569-127">Figure 10-11 shows the implementation.</span></span>

```c#
if (featureFlag) {
    // Run this code block if the featureFlag value is true
} else {
    // Run this code block if the featureFlag value is false
}
```

<span data-ttu-id="bb569-128">**Figura 10-11** : implementación de la marca de características simple.</span><span class="sxs-lookup"><span data-stu-id="bb569-128">**Figure 10-11** - Simple feature flag implementation.</span></span>

<span data-ttu-id="bb569-129">Observe cómo este enfoque separa la lógica de decisión del código de la característica.</span><span class="sxs-lookup"><span data-stu-id="bb569-129">Note how this approach separates the decision logic from the feature code.</span></span>

<span data-ttu-id="bb569-130">En el capítulo 1, analizamos el `Twelve-Factor App` .</span><span class="sxs-lookup"><span data-stu-id="bb569-130">In chapter 1, we discussed the `Twelve-Factor App`.</span></span> <span data-ttu-id="bb569-131">La guía recomienda mantener los valores de configuración externos del código ejecutable de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bb569-131">The guidance recommended keeping configuration settings external from application executable code.</span></span> <span data-ttu-id="bb569-132">Cuando sea necesario, la configuración se puede leer desde el origen externo.</span><span class="sxs-lookup"><span data-stu-id="bb569-132">When needed, settings can be read in from the external source.</span></span> <span data-ttu-id="bb569-133">Los valores de configuración de marcas de características también deben ser independientes de su código base.</span><span class="sxs-lookup"><span data-stu-id="bb569-133">Feature flag configuration values should also be independent from their codebase.</span></span> <span data-ttu-id="bb569-134">Al externalizar la configuración de marca en un repositorio independiente, puede cambiar el estado de la marca sin modificar y volver a implementar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bb569-134">By externalizing flag configuration in a separate repository, you can change flag state without modifying and redeploying the application.</span></span>

<span data-ttu-id="bb569-135">[App de Azure configuración](https://docs.microsoft.com/azure/azure-app-configuration/overview) proporciona un repositorio centralizado para las marcas de características.</span><span class="sxs-lookup"><span data-stu-id="bb569-135">[Azure App Configuration](https://docs.microsoft.com/azure/azure-app-configuration/overview) provides a centralized repository for feature flags.</span></span> <span data-ttu-id="bb569-136">Con él, puede definir diferentes tipos de marcas de características y manipular sus Estados de forma rápida y confiable.</span><span class="sxs-lookup"><span data-stu-id="bb569-136">With it, you define different kinds of feature flags and manipulate their states quickly and confidently.</span></span> <span data-ttu-id="bb569-137">Agregue las bibliotecas de cliente de configuración de aplicaciones a la aplicación para habilitar la funcionalidad de marca de características.</span><span class="sxs-lookup"><span data-stu-id="bb569-137">You add the App Configuration client libraries to your application to enable feature flag functionality.</span></span> <span data-ttu-id="bb569-138">Se admiten varias plataformas de lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="bb569-138">Various programming language frameworks are supported.</span></span>

<span data-ttu-id="bb569-139">Las marcas de características se pueden implementar fácilmente en un [servicio de ASP.net Core](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="bb569-139">Feature flags can be easily implemented in an [ASP.NET Core service](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core).</span></span> <span data-ttu-id="bb569-140">La instalación de las bibliotecas de administración de características de .NET y el proveedor de configuración de aplicaciones permiten agregar mediante declaración marcas de características al código.</span><span class="sxs-lookup"><span data-stu-id="bb569-140">Installing the .NET Feature Management libraries and App Configuration provider enable you to declaratively add feature flags to your code.</span></span> <span data-ttu-id="bb569-141">Habilitan `FeatureGate` atributos para que no tenga que escribir instrucciones if manualmente en el código base.</span><span class="sxs-lookup"><span data-stu-id="bb569-141">They enable `FeatureGate` attributes so that you don't have to manually write if statements across your codebase.</span></span>

<span data-ttu-id="bb569-142">Una vez configurada en la clase startup, puede Agregar funcionalidad de marca de características en el nivel de controlador, acción o middleware.</span><span class="sxs-lookup"><span data-stu-id="bb569-142">Once configured in your Startup class, you can add feature flag functionality at the controller, action, or middleware level.</span></span> <span data-ttu-id="bb569-143">En la figura 10-12 se muestra la implementación de la acción y el controlador:</span><span class="sxs-lookup"><span data-stu-id="bb569-143">Figure 10-12 presents controller and action implementation:</span></span>

```c#
[FeatureGate(MyFeatureFlags.FeatureA)]
public class ProductController : Controller
{
    ...
}
```

```c#
[FeatureGate(MyFeatureFlags.FeatureA)]
public IActionResult UpdateProductStatus()
{
    return ObjectResult(ProductDto);
}
```

<span data-ttu-id="bb569-144">**Figura 10-12** : implementación de la marca de características en un controlador y una acción.</span><span class="sxs-lookup"><span data-stu-id="bb569-144">**Figure 10-12** - Feature flag implementation in a controller and action.</span></span>

<span data-ttu-id="bb569-145">Si una marca de características está deshabilitada, el usuario recibirá un código de estado 404 (no encontrado) sin cuerpo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="bb569-145">If a feature flag is disabled, the user will receive a 404 (Not Found) status code with no response body.</span></span>

<span data-ttu-id="bb569-146">Las marcas de características también se pueden insertar directamente en clases de C#.</span><span class="sxs-lookup"><span data-stu-id="bb569-146">Feature flags can also be injected directly into C# classes.</span></span> <span data-ttu-id="bb569-147">En la figura 10-13 se muestra la inyección de marcas de características:</span><span class="sxs-lookup"><span data-stu-id="bb569-147">Figure 10-13 shows feature flag injection:</span></span>

```c#
public class ProductController : Controller
{
    private readonly IFeatureManager _featureManager;

    public ProductController(IFeatureManager featureManager)
    {
        _featureManager = featureManager;
    }
}
```

<span data-ttu-id="bb569-148">**Figura 10-13** : inserción de la marca de características en una clase.</span><span class="sxs-lookup"><span data-stu-id="bb569-148">**Figure 10-13** - Feature flag injection into a class.</span></span>

<span data-ttu-id="bb569-149">Las bibliotecas de administración de características administran el ciclo de vida de las marcas de características en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="bb569-149">The Feature Management libraries manage the feature flag lifecycle behind the scenes.</span></span> <span data-ttu-id="bb569-150">Por ejemplo, para minimizar un número elevado de llamadas al almacén de configuración, la memoria caché de las bibliotecas indica el estado de una duración especificada.</span><span class="sxs-lookup"><span data-stu-id="bb569-150">For example, to minimize high numbers of calls to the configuration store, the libraries cache flag states for a specified duration.</span></span> <span data-ttu-id="bb569-151">Pueden garantizar la inmutabilidad de los Estados de marca durante una llamada de solicitud.</span><span class="sxs-lookup"><span data-stu-id="bb569-151">They can guarantee the immutability of flag states during a request call.</span></span> <span data-ttu-id="bb569-152">También ofrecen un `Point-in-time snapshot` .</span><span class="sxs-lookup"><span data-stu-id="bb569-152">They also offer a `Point-in-time snapshot`.</span></span> <span data-ttu-id="bb569-153">Puede reconstruir el historial de cualquier valor de clave y proporcionar su valor anterior en cualquier momento en los siete días anteriores.</span><span class="sxs-lookup"><span data-stu-id="bb569-153">You can reconstruct the history of any key-value and provide its past value at any moment within the previous seven days.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bb569-154">[Anterior](devops.md)
>[Siguiente](infrastructure-as-code.md)</span><span class="sxs-lookup"><span data-stu-id="bb569-154">[Previous](devops.md)
[Next](infrastructure-as-code.md)</span></span>
