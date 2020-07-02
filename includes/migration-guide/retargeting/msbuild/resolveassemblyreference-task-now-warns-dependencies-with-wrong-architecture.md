---
ms.openlocfilehash: 4d410811095786b33580d25f6c6eab3ac2f27148
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616100"
---
### <a name="resolveassemblyreference-task-now-warns-of-dependencies-with-the-wrong-architecture"></a><span data-ttu-id="19c00-101">La tarea ResolveAssemblyReference ahora advierte sobre dependencias con la arquitectura incorrecta</span><span class="sxs-lookup"><span data-stu-id="19c00-101">ResolveAssemblyReference task now warns of dependencies with the wrong architecture</span></span>

#### <a name="details"></a><span data-ttu-id="19c00-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="19c00-102">Details</span></span>

<span data-ttu-id="19c00-103">La tarea emite una advertencia, MSB3270, que indica que una referencia o cualquiera de sus dependencias no coincide con la arquitectura de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19c00-103">The task emits a warning, MSB3270, which indicates that a reference or any of its dependencies does not match the app's architecture.</span></span> <span data-ttu-id="19c00-104">Por ejemplo, esto ocurre si una aplicación compilada con la opción `AnyCPU` incluye una referencia a x86.</span><span class="sxs-lookup"><span data-stu-id="19c00-104">For example, this occurs if an app that was compiled with the `AnyCPU` option includes an x86 reference.</span></span> <span data-ttu-id="19c00-105">Este tipo de escenario podría producir un error de la aplicación en tiempo de ejecución (en este caso, si la aplicación se implementa como un proceso x64).</span><span class="sxs-lookup"><span data-stu-id="19c00-105">Such a scenario could result in an app failure at run time (in this case, if the app is deployed as an x64 process).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="19c00-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="19c00-106">Suggestion</span></span>

<span data-ttu-id="19c00-107">Existen dos áreas de impacto:</span><span class="sxs-lookup"><span data-stu-id="19c00-107">There are two areas of impact:</span></span>

- <span data-ttu-id="19c00-108">Una nueva compilación genera advertencias que no aparecieron al compilar la aplicación con una versión anterior de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="19c00-108">Recompilation generates warnings that did not appear when the app was compiled under a previous version of MSBuild.</span></span> <span data-ttu-id="19c00-109">Sin embargo, dado que la advertencia identifica un posible origen de errores en el runtime, se debe investigar y solucionar.</span><span class="sxs-lookup"><span data-stu-id="19c00-109">However, because the warning identifies a possible source of runtime failure, it should be investigated and addressed.</span></span>
- <span data-ttu-id="19c00-110">Si las advertencias se tratan como errores, la aplicación no se compilará.</span><span class="sxs-lookup"><span data-stu-id="19c00-110">If warnings are treated as errors, the app will fail to compile.</span></span>

| <span data-ttu-id="19c00-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="19c00-111">Name</span></span>    | <span data-ttu-id="19c00-112">Valor</span><span class="sxs-lookup"><span data-stu-id="19c00-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="19c00-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="19c00-113">Scope</span></span>   | <span data-ttu-id="19c00-114">Secundaria</span><span class="sxs-lookup"><span data-stu-id="19c00-114">Minor</span></span>       |
| <span data-ttu-id="19c00-115">Versión</span><span class="sxs-lookup"><span data-stu-id="19c00-115">Version</span></span> | <span data-ttu-id="19c00-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="19c00-116">4.5.1</span></span>       |
| <span data-ttu-id="19c00-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="19c00-117">Type</span></span>    | <span data-ttu-id="19c00-118">Redestinación</span><span class="sxs-lookup"><span data-stu-id="19c00-118">Retargeting</span></span> |
