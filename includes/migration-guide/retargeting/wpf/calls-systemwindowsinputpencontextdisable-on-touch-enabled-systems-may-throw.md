---
ms.openlocfilehash: 0778285ef1b5702bd79743038a1bd21ba04612d6
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761141"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="f4aa4-101">Las llamadas a System.Windows.Input.PenContext.Disable en sistemas táctiles pueden iniciar una excepción ArgumentException</span><span class="sxs-lookup"><span data-stu-id="f4aa4-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f4aa4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="f4aa4-102">Details</span></span>|<span data-ttu-id="f4aa4-103">En algunas circunstancias, las llamadas al método interno <strong>System.Windows.Intput.PenContext.Disable</strong> en sistemas táctiles pueden iniciar una excepción <code>T:System.ArgumentException</code> no controlada debido a la reentrada.</span><span class="sxs-lookup"><span data-stu-id="f4aa4-103">Under some circumstances, calls to the internal <strong>System.Windows.Intput.PenContext.Disable</strong> method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="f4aa4-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="f4aa4-104">Suggestion</span></span>|<span data-ttu-id="f4aa4-105">Este problema se ha corregido en .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="f4aa4-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="f4aa4-106">Para evitar la excepción, actualice a una versión de .NET Framework a partir de .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="f4aa4-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="f4aa4-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="f4aa4-107">Scope</span></span>|<span data-ttu-id="f4aa4-108">Borde</span><span class="sxs-lookup"><span data-stu-id="f4aa4-108">Edge</span></span>|
|<span data-ttu-id="f4aa4-109">Versión</span><span class="sxs-lookup"><span data-stu-id="f4aa4-109">Version</span></span>|<span data-ttu-id="f4aa4-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="f4aa4-110">4.6.1</span></span>|
|<span data-ttu-id="f4aa4-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="f4aa4-111">Type</span></span>|<span data-ttu-id="f4aa4-112">Redestinación</span><span class="sxs-lookup"><span data-stu-id="f4aa4-112">Retargeting</span></span>|

