---
ms.openlocfilehash: 38c35f3f6f2262d06409690d2326d9b982e1ec86
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805024"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="569e1-101">Los controles de hospedaje de explorador administrado de .NET Framework 1.1 y 2.0 están bloqueados</span><span class="sxs-lookup"><span data-stu-id="569e1-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

|   |   |
|---|---|
|<span data-ttu-id="569e1-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="569e1-102">Details</span></span>|<span data-ttu-id="569e1-103">El hospedaje de estos controles está bloqueado en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="569e1-103">Hosting these controls is blocked in Internet Explorer.</span></span>|
|<span data-ttu-id="569e1-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="569e1-104">Suggestion</span></span>|<span data-ttu-id="569e1-105">Internet Explorer no podrá iniciar una aplicación que use controles de hospedaje de explorador administrados.</span><span class="sxs-lookup"><span data-stu-id="569e1-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="569e1-106">El comportamiento anterior se puede restaurar si se establece el valor EnableIEHosting de la subclave del Registro <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> en <code>1</code> para los sistemas x86 y para los procesos de 32 bits en sistemas x64, y el valor <code>EnableIEHosting</code> de la subclave del Registro <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> en <code>1</code> para los procesos de 64 bits en sistemas x64.</span><span class="sxs-lookup"><span data-stu-id="569e1-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>|
|<span data-ttu-id="569e1-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="569e1-107">Scope</span></span>|<span data-ttu-id="569e1-108">Secundaria</span><span class="sxs-lookup"><span data-stu-id="569e1-108">Minor</span></span>|
|<span data-ttu-id="569e1-109">Versión</span><span class="sxs-lookup"><span data-stu-id="569e1-109">Version</span></span>|<span data-ttu-id="569e1-110">4.5</span><span class="sxs-lookup"><span data-stu-id="569e1-110">4.5</span></span>|
|<span data-ttu-id="569e1-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="569e1-111">Type</span></span>|<span data-ttu-id="569e1-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="569e1-112">Runtime</span></span>|
