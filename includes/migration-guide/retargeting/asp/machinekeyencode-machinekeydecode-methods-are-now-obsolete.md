---
ms.openlocfilehash: 77e04333ed2b9a5ca8b900c1355fb5b12957772d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774443"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="8cd70-101">Los métodos MachineKey.Encode y MachineKey.Decode ahora están obsoletos</span><span class="sxs-lookup"><span data-stu-id="8cd70-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8cd70-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8cd70-102">Details</span></span>|<span data-ttu-id="8cd70-103">Estos métodos están obsoletos.</span><span class="sxs-lookup"><span data-stu-id="8cd70-103">These methods are now obsolete.</span></span> <span data-ttu-id="8cd70-104">La compilación del código que llama a estos métodos genera una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="8cd70-104">Compilation of code that calls these methods produces a compiler warning.</span></span>|
|<span data-ttu-id="8cd70-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8cd70-105">Suggestion</span></span>|<span data-ttu-id="8cd70-106">Las alternativas recomendadas son <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> y <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span><span class="sxs-lookup"><span data-stu-id="8cd70-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="8cd70-107">Como alternativa, se pueden suprimir las advertencias de compilación o usar un compilador anterior para evitarlas.</span><span class="sxs-lookup"><span data-stu-id="8cd70-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="8cd70-108">Las API siguen siendo compatibles.</span><span class="sxs-lookup"><span data-stu-id="8cd70-108">The APIs are still supported.</span></span>|
|<span data-ttu-id="8cd70-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8cd70-109">Scope</span></span>|<span data-ttu-id="8cd70-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="8cd70-110">Minor</span></span>|
|<span data-ttu-id="8cd70-111">Versión</span><span class="sxs-lookup"><span data-stu-id="8cd70-111">Version</span></span>|<span data-ttu-id="8cd70-112">4.5</span><span class="sxs-lookup"><span data-stu-id="8cd70-112">4.5</span></span>|
|<span data-ttu-id="8cd70-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="8cd70-113">Type</span></span>|<span data-ttu-id="8cd70-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="8cd70-114">Retargeting</span></span>|
|<span data-ttu-id="8cd70-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8cd70-115">Affected APIs</span></span>|<ul><li><xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li><li><xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li></ul>|
