---
ms.openlocfilehash: 83d3f24680531d1e447f047151a28c98ce0da04b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620671"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="5f7d9-101">Los controles de hospedaje de explorador administrado de .NET Framework 1.1 y 2.0 están bloqueados</span><span class="sxs-lookup"><span data-stu-id="5f7d9-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

#### <a name="details"></a><span data-ttu-id="5f7d9-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="5f7d9-102">Details</span></span>

<span data-ttu-id="5f7d9-103">El hospedaje de estos controles está bloqueado en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-103">Hosting these controls is blocked in Internet Explorer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5f7d9-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="5f7d9-104">Suggestion</span></span>

<span data-ttu-id="5f7d9-105">Internet Explorer no podrá iniciar una aplicación que use controles de hospedaje de explorador administrados.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="5f7d9-106">El comportamiento anterior se puede restaurar si se establece el valor EnableIEHosting de la subclave del Registro <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> en <code>1</code> para los sistemas x86 y para los procesos de 32 bits en sistemas x64, y el valor <code>EnableIEHosting</code> de la subclave del Registro <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> en <code>1</code> para los procesos de 64 bits en sistemas x64.</span><span class="sxs-lookup"><span data-stu-id="5f7d9-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>

| <span data-ttu-id="5f7d9-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="5f7d9-107">Name</span></span>    | <span data-ttu-id="5f7d9-108">Valor</span><span class="sxs-lookup"><span data-stu-id="5f7d9-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5f7d9-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="5f7d9-109">Scope</span></span>   |<span data-ttu-id="5f7d9-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="5f7d9-110">Minor</span></span>|
|<span data-ttu-id="5f7d9-111">Versión</span><span class="sxs-lookup"><span data-stu-id="5f7d9-111">Version</span></span>|<span data-ttu-id="5f7d9-112">4.5</span><span class="sxs-lookup"><span data-stu-id="5f7d9-112">4.5</span></span>|
|<span data-ttu-id="5f7d9-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="5f7d9-113">Type</span></span>|<span data-ttu-id="5f7d9-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="5f7d9-114">Runtime</span></span>|
