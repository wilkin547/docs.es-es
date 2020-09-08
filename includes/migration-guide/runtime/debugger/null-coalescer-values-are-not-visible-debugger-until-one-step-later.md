---
ms.openlocfilehash: af8de731ee93d0bfb01042d894f5730570dcdd78
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496667"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="163bc-101">Los valores NULL de fusionador no son visibles en el depurador hasta un paso posterior</span><span class="sxs-lookup"><span data-stu-id="163bc-101">Null coalescer values are not visible in debugger until one step later</span></span>

#### <a name="details"></a><span data-ttu-id="163bc-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="163bc-102">Details</span></span>

<span data-ttu-id="163bc-103">Un error en .NET Framework 4.5 hace que los valores establecidos mediante una operación de fusión NULL no sean visibles en el depurador inmediatamente después de ejecutar la operación de asignación cuando se ejecuta en la versión de 64 bits de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="163bc-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="163bc-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="163bc-104">Suggestion</span></span>

<span data-ttu-id="163bc-105">Una ejecución paso a paso adicional en el depurador hará que el valor local o del campo se actualice correctamente.</span><span class="sxs-lookup"><span data-stu-id="163bc-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="163bc-106">Ademas, este problema se ha corregido en .NET Framework 4.6; la actualización a esa versión debería solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="163bc-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>

| <span data-ttu-id="163bc-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="163bc-107">Name</span></span>    | <span data-ttu-id="163bc-108">Valor</span><span class="sxs-lookup"><span data-stu-id="163bc-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="163bc-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="163bc-109">Scope</span></span>   |<span data-ttu-id="163bc-110">Borde</span><span class="sxs-lookup"><span data-stu-id="163bc-110">Edge</span></span>|
|<span data-ttu-id="163bc-111">Versión</span><span class="sxs-lookup"><span data-stu-id="163bc-111">Version</span></span>|<span data-ttu-id="163bc-112">4.5</span><span class="sxs-lookup"><span data-stu-id="163bc-112">4.5</span></span>|
|<span data-ttu-id="163bc-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="163bc-113">Type</span></span>|<span data-ttu-id="163bc-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="163bc-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="163bc-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="163bc-115">Affected APIs</span></span>

<span data-ttu-id="163bc-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="163bc-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
