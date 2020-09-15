---
ms.openlocfilehash: a44458484ea09c566defeabc9b604bd55d994e93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617551"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="e0532-101">Las llamadas a System.Windows.Input.PenContext.Disable en sistemas táctiles pueden iniciar una excepción ArgumentException</span><span class="sxs-lookup"><span data-stu-id="e0532-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

#### <a name="details"></a><span data-ttu-id="e0532-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e0532-102">Details</span></span>

<span data-ttu-id="e0532-103">En algunas circunstancias, las llamadas al método interno **System.Windows.Intput.PenContext.Disable** en sistemas táctiles pueden iniciar una excepción `T:System.ArgumentException` no controlada debido a la reentrada.</span><span class="sxs-lookup"><span data-stu-id="e0532-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled `T:System.ArgumentException` because of reentrancy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e0532-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e0532-104">Suggestion</span></span>

<span data-ttu-id="e0532-105">Este problema se ha corregido en .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="e0532-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="e0532-106">Para evitar la excepción, actualice a una versión de .NET Framework a partir de .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="e0532-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>

| <span data-ttu-id="e0532-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e0532-107">Name</span></span>    | <span data-ttu-id="e0532-108">Valor</span><span class="sxs-lookup"><span data-stu-id="e0532-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e0532-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e0532-109">Scope</span></span>   | <span data-ttu-id="e0532-110">Borde</span><span class="sxs-lookup"><span data-stu-id="e0532-110">Edge</span></span>        |
| <span data-ttu-id="e0532-111">Versión</span><span class="sxs-lookup"><span data-stu-id="e0532-111">Version</span></span> | <span data-ttu-id="e0532-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="e0532-112">4.6.1</span></span>       |
| <span data-ttu-id="e0532-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="e0532-113">Type</span></span>    | <span data-ttu-id="e0532-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="e0532-114">Retargeting</span></span> |
