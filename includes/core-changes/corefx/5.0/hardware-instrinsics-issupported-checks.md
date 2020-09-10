---
ms.openlocfilehash: bba9659b92e5aabc276c585929c99898316036c5
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359145"
---
### <a name="hardware-intrinsic-issupported-checks-may-differ-for-nested-types"></a><span data-ttu-id="57e58-101">Las comprobaciones intrínsecas de IsSupported de hardware pueden diferir en los tipos anidados</span><span class="sxs-lookup"><span data-stu-id="57e58-101">Hardware intrinsic IsSupported checks may differ for nested types</span></span>

<span data-ttu-id="57e58-102">La comprobación de `<Isa>.X64.IsSupported`, donde `<Isa>` hace referencia a las clases del espacio de nombres <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType>, ahora puede generar un resultado diferente en versiones anteriores de .NET.</span><span class="sxs-lookup"><span data-stu-id="57e58-102">Checking `<Isa>.X64.IsSupported`, where `<Isa>` refers to the classes in the <xref:System.Runtime.Intrinsics.X86?displayProperty=nameWithType> namespace, may now produce a different result to previous versions of .NET.</span></span>

> [!TIP]
> <span data-ttu-id="57e58-103">*ISA* representa la arquitectura estándar del sector.</span><span class="sxs-lookup"><span data-stu-id="57e58-103">*ISA* stands for industry standard architecture.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="57e58-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="57e58-104">Version introduced</span></span>

<span data-ttu-id="57e58-105">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="57e58-105">5.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="57e58-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="57e58-106">Change description</span></span>

<span data-ttu-id="57e58-107">En versiones anteriores de .NET, algunos de los tipos intrínsecos de hardware de <xref:System.Runtime.Intrinsics.X86>, por ejemplo, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>, no exponían una clase anidada de `X64` .</span><span class="sxs-lookup"><span data-stu-id="57e58-107">In previous versions of .NET, some of the <xref:System.Runtime.Intrinsics.X86> hardware-intrinsic types, for example, <xref:System.Runtime.Intrinsics.X86.Aes?displayProperty=nameWithType>, didn't expose a nested `X64` class.</span></span> <span data-ttu-id="57e58-108">Para estos tipos, la llamada a `<Isa>.X64.IsSupported` se resolvía en una propiedad `IsSupported` en una clase `X64` anidada de una clase principal `<Isa>`.</span><span class="sxs-lookup"><span data-stu-id="57e58-108">For these types, calling `<Isa>.X64.IsSupported` resolved to an `IsSupported` property on a nested `X64` class of a parent class of `<Isa>`.</span></span> <span data-ttu-id="57e58-109">Esto significaba que la propiedad podía devolver `true` incluso cuando `<Isa>.IsSupported` devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="57e58-109">This meant that the property could return `true` even when `<Isa>.IsSupported` returns `false`.</span></span>

<span data-ttu-id="57e58-110">En .NET 5.0 y versiones posteriores, todos los tipos <xref:System.Runtime.Intrinsics.X86> exponen una clase `X64` anidada que notifica correctamente la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="57e58-110">In .NET 5.0 and later versions, all of the <xref:System.Runtime.Intrinsics.X86> types expose a nested `X64` class that appropriately reports support.</span></span> <span data-ttu-id="57e58-111">Esto garantiza que la jerarquía general siga siendo correcta y que si `<Isa>.X64.IsSupported` es `true`, también se puede suponer que `<Isa>.IsSupported` es `true`.</span><span class="sxs-lookup"><span data-stu-id="57e58-111">This ensures that the general hierarchy remains correct, and that if `<Isa>.X64.IsSupported` is `true`, then `<Isa>.IsSupported` can also be assumed to be `true`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="57e58-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="57e58-112">Reason for change</span></span>

<span data-ttu-id="57e58-113">Estaba previsto que, si `<Isa>.X64.IsSupported` es `true`, `<Isa>.IsSupported` debía ser `true`.</span><span class="sxs-lookup"><span data-stu-id="57e58-113">It was intended that if `<Isa>.X64.IsSupported` is `true`, `<Isa>.IsSupported` is also implied to be `true`.</span></span> <span data-ttu-id="57e58-114">Sin embargo, debido a cómo funciona la resolución de miembros en C#, las clases que no tenían una clase `X64` anidada exponían una situación en la que este no siempre era el caso y se generaban errores en el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="57e58-114">However, due to how member resolution works in C#, classes that didn't have a nested `X64` class exposed a situation where this wasn't always the case and led to bugs in user code.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="57e58-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="57e58-115">Recommended action</span></span>

<span data-ttu-id="57e58-116">Si es necesario, ajuste el código que comprueba `IsSupported` para buscar el ISA adecuado.</span><span class="sxs-lookup"><span data-stu-id="57e58-116">If necessary, adjust code that checks `IsSupported` to check for the appropriate ISA.</span></span>

#### <a name="category"></a><span data-ttu-id="57e58-117">Categoría</span><span class="sxs-lookup"><span data-stu-id="57e58-117">Category</span></span>

<span data-ttu-id="57e58-118">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="57e58-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="57e58-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="57e58-119">Affected APIs</span></span>

- <xref:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported?displayProperty=fullName>
- <xref:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.Intrinsics.X86.Aes.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Avx2.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Fma.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Pclmulqdq.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Sse3.X64.IsSupported`
- `P:System.Runtime.Intrinsics.X86.Ssse3.X64.IsSupported`

-->
