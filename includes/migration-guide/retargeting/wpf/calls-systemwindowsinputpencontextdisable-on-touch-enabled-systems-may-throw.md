---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887840"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="3996e-101">Las llamadas a System.Windows.Input.PenContext.Disable en sistemas táctiles pueden iniciar una excepción ArgumentException</span><span class="sxs-lookup"><span data-stu-id="3996e-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3996e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="3996e-102">Details</span></span>|<span data-ttu-id="3996e-103">En algunas circunstancias, las llamadas al método interno **System.Windows.Intput.PenContext.Disable** en sistemas táctiles pueden iniciar una excepción <code>T:System.ArgumentException</code> no controlada debido a la reentrada.</span><span class="sxs-lookup"><span data-stu-id="3996e-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="3996e-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="3996e-104">Suggestion</span></span>|<span data-ttu-id="3996e-105">Este problema se ha corregido en .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="3996e-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="3996e-106">Para evitar la excepción, actualice a una versión de .NET Framework a partir de .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="3996e-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="3996e-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="3996e-107">Scope</span></span>|<span data-ttu-id="3996e-108">Borde</span><span class="sxs-lookup"><span data-stu-id="3996e-108">Edge</span></span>|
|<span data-ttu-id="3996e-109">Versión</span><span class="sxs-lookup"><span data-stu-id="3996e-109">Version</span></span>|<span data-ttu-id="3996e-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="3996e-110">4.6.1</span></span>|
|<span data-ttu-id="3996e-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="3996e-111">Type</span></span>|<span data-ttu-id="3996e-112">Redestinación</span><span class="sxs-lookup"><span data-stu-id="3996e-112">Retargeting</span></span>|
