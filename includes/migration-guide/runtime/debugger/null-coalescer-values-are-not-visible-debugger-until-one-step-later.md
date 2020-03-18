---
ms.openlocfilehash: 22f8e3bb1ba72379b3f5fc87a077e5fe57f89bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858599"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="897dc-101">Los valores NULL de fusionador no son visibles en el depurador hasta un paso posterior</span><span class="sxs-lookup"><span data-stu-id="897dc-101">Null coalescer values are not visible in debugger until one step later</span></span>

|   |   |
|---|---|
|<span data-ttu-id="897dc-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="897dc-102">Details</span></span>|<span data-ttu-id="897dc-103">Un error en .NET Framework 4.5 hace que los valores establecidos mediante una operación de fusión NULL no sean visibles en el depurador inmediatamente después de ejecutar la operación de asignación cuando se ejecuta en la versión de 64 bits de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="897dc-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>|
|<span data-ttu-id="897dc-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="897dc-104">Suggestion</span></span>|<span data-ttu-id="897dc-105">Una ejecución paso a paso adicional en el depurador hará que el valor local o del campo se actualice correctamente.</span><span class="sxs-lookup"><span data-stu-id="897dc-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="897dc-106">Ademas, este problema se ha corregido en .NET Framework 4.6; la actualización a esa versión debería solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="897dc-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>|
|<span data-ttu-id="897dc-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="897dc-107">Scope</span></span>|<span data-ttu-id="897dc-108">Borde</span><span class="sxs-lookup"><span data-stu-id="897dc-108">Edge</span></span>|
|<span data-ttu-id="897dc-109">Versión</span><span class="sxs-lookup"><span data-stu-id="897dc-109">Version</span></span>|<span data-ttu-id="897dc-110">4.5</span><span class="sxs-lookup"><span data-stu-id="897dc-110">4.5</span></span>|
|<span data-ttu-id="897dc-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="897dc-111">Type</span></span>|<span data-ttu-id="897dc-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="897dc-112">Runtime</span></span>|
