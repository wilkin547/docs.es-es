---
title: 'Cambio importante: Vector<T> inicia una excepción NotSupportedException'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET, donde Vector<T> siempre inicia una excepción para los parámetros de tipo no admitidos.
ms.date: 11/01/2020
ms.openlocfilehash: dccd39c01f4debd7d1432195e7f3cb14aeda5f65
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257016"
---
# <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a><span data-ttu-id="1fc3f-103">Vector\<T> siempre inicia una excepción NotSupportedException en el caso de tipos no admitidos</span><span class="sxs-lookup"><span data-stu-id="1fc3f-103">Vector\<T> always throws NotSupportedException for unsupported types</span></span>

<span data-ttu-id="1fc3f-104"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> ahora inicia siempre una excepción <xref:System.NotSupportedException> para los parámetros de tipo no admitidos.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-104"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> now always throws a <xref:System.NotSupportedException> for unsupported type parameters.</span></span>

## <a name="change-description"></a><span data-ttu-id="1fc3f-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="1fc3f-105">Change description</span></span>

<span data-ttu-id="1fc3f-106">Antes, los miembros de <xref:System.Numerics.Vector%601> no siempre iniciaban una excepción <xref:System.NotSupportedException> cuando `T` era un [tipo no admitido](#unsupported-types).</span><span class="sxs-lookup"><span data-stu-id="1fc3f-106">Previously, members of <xref:System.Numerics.Vector%601> would not always throw a <xref:System.NotSupportedException> when `T` was an [unsupported type](#unsupported-types).</span></span> <span data-ttu-id="1fc3f-107">La excepción no se iniciaba siempre debido a las rutas de acceso de código que permitían la aceleración de hardware.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-107">The exception wasn't always thrown because of code paths that supported hardware acceleration.</span></span> <span data-ttu-id="1fc3f-108">Por ejemplo, `Vector<bool> + Vector<bool>` devolvía `default` en lugar de iniciar una excepción en plataformas que no tienen aceleración de hardware, como ARM32.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-108">For example, `Vector<bool> + Vector<bool>` returned `default` instead of throwing an exception on platforms that have no hardware acceleration, such as ARM32.</span></span> <span data-ttu-id="1fc3f-109">En el caso de los tipos no admitidos, los miembros <xref:System.Numerics.Vector%601> exhibían un comportamiento incoherente en distintas plataformas y configuraciones de hardware.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-109">For unsupported types, <xref:System.Numerics.Vector%601> members exhibited inconsistent behavior across different platforms and hardware configurations.</span></span>

<span data-ttu-id="1fc3f-110">A partir de .NET 5, los miembros <xref:System.Numerics.Vector%601> siempre inician una excepción <xref:System.NotSupportedException> en todas las configuraciones de hardware cuando `T` no es un tipo admitido.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-110">Starting in .NET 5, <xref:System.Numerics.Vector%601> members always throw a <xref:System.NotSupportedException> on all hardware configurations when `T` is not a supported type.</span></span>

### <a name="unsupported-types"></a><span data-ttu-id="1fc3f-111">Tipos no admitidos</span><span class="sxs-lookup"><span data-stu-id="1fc3f-111">Unsupported types</span></span>

<span data-ttu-id="1fc3f-112">Los tipos admitidos del parámetro de tipo de <xref:System.Numerics.Vector%601> son:</span><span class="sxs-lookup"><span data-stu-id="1fc3f-112">The supported types for the type parameter of <xref:System.Numerics.Vector%601> are:</span></span>

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

<span data-ttu-id="1fc3f-113">Los tipos admitidos no han cambiado, pero pueden cambiar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-113">The supported types have not changed, however, they may change in the future.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="1fc3f-114">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1fc3f-114">Version introduced</span></span>

<span data-ttu-id="1fc3f-115">5.0</span><span class="sxs-lookup"><span data-stu-id="1fc3f-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="1fc3f-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="1fc3f-116">Recommended action</span></span>

<span data-ttu-id="1fc3f-117">No utilice un tipo no admitido como parámetro de tipo de <xref:System.Numerics.Vector%601>.</span><span class="sxs-lookup"><span data-stu-id="1fc3f-117">Don't use an unsupported type for the type parameter of <xref:System.Numerics.Vector%601>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="1fc3f-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1fc3f-118">Affected APIs</span></span>

- <span data-ttu-id="1fc3f-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> y todos sus miembros</span><span class="sxs-lookup"><span data-stu-id="1fc3f-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> and all its members</span></span>

<!--

#### Category

Core .NET libraries

### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
