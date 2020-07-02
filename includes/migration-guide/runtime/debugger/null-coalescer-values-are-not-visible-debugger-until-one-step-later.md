---
ms.openlocfilehash: 907c4aa5573c392a68afad0a4d937eadcd556440
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620608"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="adce8-101">Los valores NULL de fusionador no son visibles en el depurador hasta un paso posterior</span><span class="sxs-lookup"><span data-stu-id="adce8-101">Null coalescer values are not visible in debugger until one step later</span></span>

#### <a name="details"></a><span data-ttu-id="adce8-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="adce8-102">Details</span></span>

<span data-ttu-id="adce8-103">Un error en .NET Framework 4.5 hace que los valores establecidos mediante una operación de fusión NULL no sean visibles en el depurador inmediatamente después de ejecutar la operación de asignación cuando se ejecuta en la versión de 64 bits de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="adce8-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="adce8-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="adce8-104">Suggestion</span></span>

<span data-ttu-id="adce8-105">Una ejecución paso a paso adicional en el depurador hará que el valor local o del campo se actualice correctamente.</span><span class="sxs-lookup"><span data-stu-id="adce8-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="adce8-106">Ademas, este problema se ha corregido en .NET Framework 4.6; la actualización a esa versión debería solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="adce8-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>

| <span data-ttu-id="adce8-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="adce8-107">Name</span></span>    | <span data-ttu-id="adce8-108">Valor</span><span class="sxs-lookup"><span data-stu-id="adce8-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="adce8-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="adce8-109">Scope</span></span>   |<span data-ttu-id="adce8-110">Borde</span><span class="sxs-lookup"><span data-stu-id="adce8-110">Edge</span></span>|
|<span data-ttu-id="adce8-111">Versión</span><span class="sxs-lookup"><span data-stu-id="adce8-111">Version</span></span>|<span data-ttu-id="adce8-112">4.5</span><span class="sxs-lookup"><span data-stu-id="adce8-112">4.5</span></span>|
|<span data-ttu-id="adce8-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="adce8-113">Type</span></span>|<span data-ttu-id="adce8-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="adce8-114">Runtime</span></span>|
