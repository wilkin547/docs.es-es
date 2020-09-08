---
ms.openlocfilehash: c3114277445daaae988b41782721c443c1e780d1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496453"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a><span data-ttu-id="90768-101">WPF genera un proceso de wisptis.exe que puede inmovilizar el mouse</span><span class="sxs-lookup"><span data-stu-id="90768-101">WPF spawns a wisptis.exe process which can freeze the mouse</span></span>

#### <a name="details"></a><span data-ttu-id="90768-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="90768-102">Details</span></span>

<span data-ttu-id="90768-103">En la versión 4.5.2 apareció un problema que hace que se genere <code>wisptis.exe</code> y que puede inmovilizar la entrada del mouse.</span><span class="sxs-lookup"><span data-stu-id="90768-103">An issue was introduced in 4.5.2 that causes <code>wisptis.exe</code> to be spawned that can freeze mouse input.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="90768-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="90768-104">Suggestion</span></span>

<span data-ttu-id="90768-105">Una corrección para este problema está disponible en una versión de servicio de .NET Framework 4.5.2 (paquete acumulativo de revisiones 3026376), o bien mediante la actualización a .NET Framework 4.6.</span><span class="sxs-lookup"><span data-stu-id="90768-105">A fix for this issue is available in a servicing release of the .NET Framework 4.5.2 (hotfix rollup 3026376), or by upgrading to the .NET Framework 4.6</span></span>

| <span data-ttu-id="90768-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="90768-106">Name</span></span>    | <span data-ttu-id="90768-107">Valor</span><span class="sxs-lookup"><span data-stu-id="90768-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="90768-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="90768-108">Scope</span></span>   |<span data-ttu-id="90768-109">Major</span><span class="sxs-lookup"><span data-stu-id="90768-109">Major</span></span>|
|<span data-ttu-id="90768-110">Versión</span><span class="sxs-lookup"><span data-stu-id="90768-110">Version</span></span>|<span data-ttu-id="90768-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="90768-111">4.5.2</span></span>|
|<span data-ttu-id="90768-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="90768-112">Type</span></span>|<span data-ttu-id="90768-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="90768-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="90768-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="90768-114">Affected APIs</span></span>

<span data-ttu-id="90768-115">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="90768-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
