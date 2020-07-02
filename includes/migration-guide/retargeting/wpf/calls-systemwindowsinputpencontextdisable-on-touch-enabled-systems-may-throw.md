---
ms.openlocfilehash: a44458484ea09c566defeabc9b604bd55d994e93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617551"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="ebf53-101">Las llamadas a System.Windows.Input.PenContext.Disable en sistemas táctiles pueden iniciar una excepción ArgumentException</span><span class="sxs-lookup"><span data-stu-id="ebf53-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

#### <a name="details"></a><span data-ttu-id="ebf53-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="ebf53-102">Details</span></span>

<span data-ttu-id="ebf53-103">En algunas circunstancias, las llamadas al método interno **System.Windows.Intput.PenContext.Disable** en sistemas táctiles pueden iniciar una excepción `T:System.ArgumentException` no controlada debido a la reentrada.</span><span class="sxs-lookup"><span data-stu-id="ebf53-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled `T:System.ArgumentException` because of reentrancy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ebf53-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="ebf53-104">Suggestion</span></span>

<span data-ttu-id="ebf53-105">Este problema se ha corregido en .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="ebf53-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="ebf53-106">Para evitar la excepción, actualice a una versión de .NET Framework a partir de .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="ebf53-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>

| <span data-ttu-id="ebf53-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="ebf53-107">Name</span></span>    | <span data-ttu-id="ebf53-108">Valor</span><span class="sxs-lookup"><span data-stu-id="ebf53-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ebf53-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="ebf53-109">Scope</span></span>   | <span data-ttu-id="ebf53-110">Borde</span><span class="sxs-lookup"><span data-stu-id="ebf53-110">Edge</span></span>        |
| <span data-ttu-id="ebf53-111">Versión</span><span class="sxs-lookup"><span data-stu-id="ebf53-111">Version</span></span> | <span data-ttu-id="ebf53-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="ebf53-112">4.6.1</span></span>       |
| <span data-ttu-id="ebf53-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="ebf53-113">Type</span></span>    | <span data-ttu-id="ebf53-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="ebf53-114">Retargeting</span></span> |
