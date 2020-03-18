---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "72887840"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="e13eb-101">Las llamadas a System.Windows.Input.PenContext.Disable en sistemas táctiles pueden iniciar una excepción ArgumentException</span><span class="sxs-lookup"><span data-stu-id="e13eb-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e13eb-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e13eb-102">Details</span></span>|<span data-ttu-id="e13eb-103">En algunas circunstancias, las llamadas al método interno **System.Windows.Intput.PenContext.Disable** en sistemas táctiles pueden iniciar una excepción <code>T:System.ArgumentException</code> no controlada debido a la reentrada.</span><span class="sxs-lookup"><span data-stu-id="e13eb-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="e13eb-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e13eb-104">Suggestion</span></span>|<span data-ttu-id="e13eb-105">Este problema se ha corregido en .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="e13eb-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="e13eb-106">Para evitar la excepción, actualice a una versión de .NET Framework a partir de .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="e13eb-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="e13eb-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e13eb-107">Scope</span></span>|<span data-ttu-id="e13eb-108">Borde</span><span class="sxs-lookup"><span data-stu-id="e13eb-108">Edge</span></span>|
|<span data-ttu-id="e13eb-109">Versión</span><span class="sxs-lookup"><span data-stu-id="e13eb-109">Version</span></span>|<span data-ttu-id="e13eb-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="e13eb-110">4.6.1</span></span>|
|<span data-ttu-id="e13eb-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="e13eb-111">Type</span></span>|<span data-ttu-id="e13eb-112">Redestinación</span><span class="sxs-lookup"><span data-stu-id="e13eb-112">Retargeting</span></span>|
