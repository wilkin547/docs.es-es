---
ms.openlocfilehash: d4f0095bc9fde98087dce528c8154d9c9ac6ddb7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621837"
---
### <a name="wpf-spell-checking-fails-in-unexpected-ways"></a><span data-ttu-id="b9ea9-101">Se produce un error inesperado en la revisión ortográfica de WPF</span><span class="sxs-lookup"><span data-stu-id="b9ea9-101">WPF Spell Checking fails in unexpected ways</span></span>

#### <a name="details"></a><span data-ttu-id="b9ea9-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b9ea9-102">Details</span></span>

<span data-ttu-id="b9ea9-103">Esto incluye una serie de problemas del corrector ortográfico de WPF:</span><span class="sxs-lookup"><span data-stu-id="b9ea9-103">This includes a number of WPF Spell Checker issues:</span></span><ul><li><span data-ttu-id="b9ea9-104">En ocasiones, el corrector ortográfico de WPF inicia una excepción <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="b9ea9-104">WPF Spell Checker sometimes throws <xref:System.Runtime.InteropServices.COMException?displayProperty=fullName></span></span></li><li><span data-ttu-id="b9ea9-105">Se produce un error en el corrector ortográfico de WPF con una excepción <xref:System.UnauthorizedAccessException> cuando las aplicaciones se inician mediante "Ejecutar como otro usuario".</span><span class="sxs-lookup"><span data-stu-id="b9ea9-105">WPF Spell Checker fails with <xref:System.UnauthorizedAccessException> when applications are launched using 'run as different user'</span></span></li><li><span data-ttu-id="b9ea9-106">El corrector ortográfico de WPF identifica incorrectamente errores ortográficos en palabras compuestas, como "Hausnummer" en alemán.</span><span class="sxs-lookup"><span data-stu-id="b9ea9-106">WPF Spell Checker incorrectly identifies spelling errors in compound words like 'Hausnummer' in German.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="b9ea9-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b9ea9-107">Suggestion</span></span>

<span data-ttu-id="b9ea9-108">Problema 1: esto se ha solucionado en .NET Framework 4.6.2. Problema 2: el corrector ortográfico de WPF ya no se admite cuando las aplicaciones se inician con la opción "Ejecutar como otro usuario".</span><span class="sxs-lookup"><span data-stu-id="b9ea9-108">Issue #1 - This has been fixed in .NET Framework 4.6.2 Issue #2 - WPF Spell Checker is no longer supported when applications are launched using 'run as different user'.</span></span> <span data-ttu-id="b9ea9-109">A partir de .NET Framework 4.6.2, las aplicaciones iniciadas de esta manera ya no se bloquean de forma inesperada; en su lugar, el corrector ortográfico se deshabilita en modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="b9ea9-109">Starting .NET Framework 4.6.2, applications launched in this manner will no longer crash unexpectedly - instead the Spell Checker will be silently disabled.</span></span> <span data-ttu-id="b9ea9-110">Problema 3: esto se ha solucionado en .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="b9ea9-110">Issue #3 - This has been fixed in .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="b9ea9-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b9ea9-111">Name</span></span>    | <span data-ttu-id="b9ea9-112">Valor</span><span class="sxs-lookup"><span data-stu-id="b9ea9-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b9ea9-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b9ea9-113">Scope</span></span>   |<span data-ttu-id="b9ea9-114">Borde</span><span class="sxs-lookup"><span data-stu-id="b9ea9-114">Edge</span></span>|
|<span data-ttu-id="b9ea9-115">Versión</span><span class="sxs-lookup"><span data-stu-id="b9ea9-115">Version</span></span>|<span data-ttu-id="b9ea9-116">4.6.1</span><span class="sxs-lookup"><span data-stu-id="b9ea9-116">4.6.1</span></span>|
|<span data-ttu-id="b9ea9-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="b9ea9-117">Type</span></span>|<span data-ttu-id="b9ea9-118">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b9ea9-118">Runtime</span></span>|
