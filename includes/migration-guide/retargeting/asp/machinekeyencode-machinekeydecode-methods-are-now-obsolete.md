---
ms.openlocfilehash: e9d34465970287ed94c0f0373ee4ae94d55aa1ff
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617266"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a><span data-ttu-id="d62c6-101">Los métodos MachineKey.Encode y MachineKey.Decode ahora están obsoletos</span><span class="sxs-lookup"><span data-stu-id="d62c6-101">MachineKey.Encode and MachineKey.Decode methods are now obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="d62c6-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d62c6-102">Details</span></span>

<span data-ttu-id="d62c6-103">Estos métodos están obsoletos.</span><span class="sxs-lookup"><span data-stu-id="d62c6-103">These methods are now obsolete.</span></span> <span data-ttu-id="d62c6-104">La compilación del código que llama a estos métodos genera una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="d62c6-104">Compilation of code that calls these methods produces a compiler warning.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d62c6-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d62c6-105">Suggestion</span></span>

<span data-ttu-id="d62c6-106">Las alternativas recomendadas son <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> y <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span><span class="sxs-lookup"><span data-stu-id="d62c6-106">The recommended alternatives are <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> and <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>.</span></span> <span data-ttu-id="d62c6-107">Como alternativa, se pueden suprimir las advertencias de compilación o usar un compilador anterior para evitarlas.</span><span class="sxs-lookup"><span data-stu-id="d62c6-107">Alternatively, the build warnings can be suppressed, or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="d62c6-108">Las API siguen siendo compatibles.</span><span class="sxs-lookup"><span data-stu-id="d62c6-108">The APIs are still supported.</span></span>

| <span data-ttu-id="d62c6-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="d62c6-109">Name</span></span>    | <span data-ttu-id="d62c6-110">Valor</span><span class="sxs-lookup"><span data-stu-id="d62c6-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d62c6-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d62c6-111">Scope</span></span>   | <span data-ttu-id="d62c6-112">Secundaria</span><span class="sxs-lookup"><span data-stu-id="d62c6-112">Minor</span></span>       |
| <span data-ttu-id="d62c6-113">Versión</span><span class="sxs-lookup"><span data-stu-id="d62c6-113">Version</span></span> | <span data-ttu-id="d62c6-114">4.5</span><span class="sxs-lookup"><span data-stu-id="d62c6-114">4.5</span></span>         |
| <span data-ttu-id="d62c6-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="d62c6-115">Type</span></span>    | <span data-ttu-id="d62c6-116">Redestinación</span><span class="sxs-lookup"><span data-stu-id="d62c6-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d62c6-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d62c6-117">Affected APIs</span></span>

- <xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
- <xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType>
