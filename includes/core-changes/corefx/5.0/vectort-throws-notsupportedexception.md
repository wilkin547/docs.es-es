---
ms.openlocfilehash: 43ebb37124b8efe077b9f81fe5351bd7db2c72f7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302727"
---
### <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a><span data-ttu-id="5a899-101">Vector\<T> siempre inicia una excepción NotSupportedException en el caso de tipos no admitidos</span><span class="sxs-lookup"><span data-stu-id="5a899-101">Vector\<T> always throws NotSupportedException for unsupported types</span></span>

<span data-ttu-id="5a899-102"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> ahora inicia siempre una excepción <xref:System.NotSupportedException> para los parámetros de tipo no admitidos.</span><span class="sxs-lookup"><span data-stu-id="5a899-102"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> now always throws a <xref:System.NotSupportedException> for unsupported type parameters.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5a899-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="5a899-103">Change description</span></span>

<span data-ttu-id="5a899-104">Antes, los miembros de <xref:System.Numerics.Vector%601> no siempre iniciaban una excepción <xref:System.NotSupportedException> cuando `T` era un [tipo no admitido](#unsupported-types).</span><span class="sxs-lookup"><span data-stu-id="5a899-104">Previously, members of <xref:System.Numerics.Vector%601> would not always throw a <xref:System.NotSupportedException> when `T` was an [unsupported type](#unsupported-types).</span></span> <span data-ttu-id="5a899-105">La excepción no se iniciaba siempre debido a las rutas de acceso de código que permitían la aceleración de hardware.</span><span class="sxs-lookup"><span data-stu-id="5a899-105">The exception wasn't always thrown because of code paths that supported hardware acceleration.</span></span> <span data-ttu-id="5a899-106">Por ejemplo, `Vector<bool> + Vector<bool>` devolvía `default` en lugar de iniciar una excepción en plataformas que no tienen aceleración de hardware, como ARM32.</span><span class="sxs-lookup"><span data-stu-id="5a899-106">For example, `Vector<bool> + Vector<bool>` returned `default` instead of throwing an exception on platforms that have no hardware acceleration, such as ARM32.</span></span> <span data-ttu-id="5a899-107">En el caso de los tipos no admitidos, los miembros <xref:System.Numerics.Vector%601> exhibían un comportamiento incoherente en distintas plataformas y configuraciones de hardware.</span><span class="sxs-lookup"><span data-stu-id="5a899-107">For unsupported types, <xref:System.Numerics.Vector%601> members exhibited inconsistent behavior across different platforms and hardware configurations.</span></span>

<span data-ttu-id="5a899-108">A partir de .NET 5.0, los miembros <xref:System.Numerics.Vector%601> siempre inician una excepción <xref:System.NotSupportedException> en todas las configuraciones de hardware cuando `T` no es un tipo admitido.</span><span class="sxs-lookup"><span data-stu-id="5a899-108">Starting in .NET 5.0, <xref:System.Numerics.Vector%601> members always throw a <xref:System.NotSupportedException> on all hardware configurations when `T` is not a supported type.</span></span>

##### <a name="unsupported-types"></a><span data-ttu-id="5a899-109">Tipos no admitidos</span><span class="sxs-lookup"><span data-stu-id="5a899-109">Unsupported types</span></span>

<span data-ttu-id="5a899-110">Los tipos admitidos del parámetro de tipo de <xref:System.Numerics.Vector%601> son:</span><span class="sxs-lookup"><span data-stu-id="5a899-110">The supported types for the type parameter of <xref:System.Numerics.Vector%601> are:</span></span>

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

<span data-ttu-id="5a899-111">Los tipos admitidos no han cambiado, pero pueden cambiar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="5a899-111">The supported types have not changed, however, they may change in the future.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5a899-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5a899-112">Version introduced</span></span>

<span data-ttu-id="5a899-113">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="5a899-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5a899-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="5a899-114">Recommended action</span></span>

<span data-ttu-id="5a899-115">No utilice un tipo no admitido como parámetro de tipo de <xref:System.Numerics.Vector%601>.</span><span class="sxs-lookup"><span data-stu-id="5a899-115">Don't use an unsupported type for the type parameter of <xref:System.Numerics.Vector%601>.</span></span>

#### <a name="category"></a><span data-ttu-id="5a899-116">Categoría</span><span class="sxs-lookup"><span data-stu-id="5a899-116">Category</span></span>

<span data-ttu-id="5a899-117">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="5a899-117">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5a899-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5a899-118">Affected APIs</span></span>

- <span data-ttu-id="5a899-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> y todos sus miembros</span><span class="sxs-lookup"><span data-stu-id="5a899-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> and all its members</span></span>

<!--

#### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
