---
ms.openlocfilehash: 26539011f0650c7a3bac9e1c41847561905fff58
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496514"
---
### <a name="managed-browser-hosting-controls-from-the-net-framework-11-and-20-are-blocked"></a><span data-ttu-id="a3e3e-101">Los controles de hospedaje de explorador administrado de .NET Framework 1.1 y 2.0 están bloqueados</span><span class="sxs-lookup"><span data-stu-id="a3e3e-101">Managed browser hosting controls from the .NET Framework 1.1 and 2.0 are blocked</span></span>

#### <a name="details"></a><span data-ttu-id="a3e3e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a3e3e-102">Details</span></span>

<span data-ttu-id="a3e3e-103">El hospedaje de estos controles está bloqueado en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-103">Hosting these controls is blocked in Internet Explorer.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a3e3e-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a3e3e-104">Suggestion</span></span>

<span data-ttu-id="a3e3e-105">Internet Explorer no podrá iniciar una aplicación que use controles de hospedaje de explorador administrados.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-105">Internet Explorer will fail to launch an application that uses managed browser hosting controls.</span></span> <span data-ttu-id="a3e3e-106">El comportamiento anterior se puede restaurar si se establece el valor EnableIEHosting de la subclave del Registro <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> en <code>1</code> para los sistemas x86 y para los procesos de 32 bits en sistemas x64, y el valor <code>EnableIEHosting</code> de la subclave del Registro <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> en <code>1</code> para los procesos de 64 bits en sistemas x64.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-106">The previous behavior can be restored by setting the EnableIEHosting value of the registry subkey <code>HKLM/SOFTWARE/MICROSOFT/.NETFramework</code> to <code>1</code> for x86 systems and for 32-bit processes on x64 systems, and by setting the <code>EnableIEHosting</code> value of the registry subkey <code>HKLM/SOFTWARE/Wow6432Node/Microsoft/.NETFramework</code> to <code>1</code> for 64-bit processes on x64 systems.</span></span>

| <span data-ttu-id="a3e3e-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="a3e3e-107">Name</span></span>    | <span data-ttu-id="a3e3e-108">Valor</span><span class="sxs-lookup"><span data-stu-id="a3e3e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a3e3e-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a3e3e-109">Scope</span></span>   |<span data-ttu-id="a3e3e-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="a3e3e-110">Minor</span></span>|
|<span data-ttu-id="a3e3e-111">Versión</span><span class="sxs-lookup"><span data-stu-id="a3e3e-111">Version</span></span>|<span data-ttu-id="a3e3e-112">4.5</span><span class="sxs-lookup"><span data-stu-id="a3e3e-112">4.5</span></span>|
|<span data-ttu-id="a3e3e-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="a3e3e-113">Type</span></span>|<span data-ttu-id="a3e3e-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a3e3e-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a3e3e-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a3e3e-115">Affected APIs</span></span>

<span data-ttu-id="a3e3e-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="a3e3e-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
