---
ms.openlocfilehash: 3692848a0cbd4bbbe3c7bb4d2c22a2b19de732e4
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050484"
---
### <a name="non-public-parameterless-constructors-not-used-for-deserialization"></a><span data-ttu-id="6fd2e-101">Constructores no públicos sin parámetros que no se usan para la deserialización</span><span class="sxs-lookup"><span data-stu-id="6fd2e-101">Non-public, parameterless constructors not used for deserialization</span></span>

<span data-ttu-id="6fd2e-102">Para mantener la coherencia entre todos los monikers de la plataforma de destino (TFM) admitidos, de forma predeterminada ya no se usan para la deserialización con <xref:System.Text.Json.JsonSerializer> los constructores no públicos y sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-102">For consistency across all supported target framework monikers (TFMs), non-public, parameterless constructors are no longer used for deserialization with <xref:System.Text.Json.JsonSerializer>, by default.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6fd2e-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="6fd2e-103">Change description</span></span>

<span data-ttu-id="6fd2e-104">Los [paquetes NuGet System.Text.Json](https://www.nuget.org/packages/System.Text.Json/) independientes que admiten .NET Standard 2.0 y versiones posteriores, es decir, las versiones 4.6.0-4.7.2, se comportan de manera incoherente con el comportamiento integrado en .NET Core 3.0 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-104">The standalone [System.Text.Json NuGet packages](https://www.nuget.org/packages/System.Text.Json/) that support .NET Standard 2.0 and higher, that is, versions 4.6.0-4.7.2, behave inconsistently with the built-in behavior on .NET Core 3.0 and 3.1.</span></span> <span data-ttu-id="6fd2e-105">En .NET Core 3.x, se pueden usar constructores internos y privados para la deserialización.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-105">On .NET Core 3.x, internal and private constructors can be used for deserialization.</span></span> <span data-ttu-id="6fd2e-106">En los paquetes independientes, no se permiten constructores no públicos y se inicia una excepción <xref:System.MissingMethodException> si no se define ningún constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-106">In the standalone packages, non-public constructors are not allowed, and a <xref:System.MissingMethodException> is thrown if no public, parameterless constructor is defined.</span></span>

<span data-ttu-id="6fd2e-107">A partir de .NET 5.0 y del paquete NuGet System.Text.Json 5.0.0, el comportamiento es coherente entre el paquete NuGet y las API integradas.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-107">Starting with .NET 5.0 and System.Text.Json NuGet package 5.0.0, the behavior is consistent between the NuGet package and the built-in APIs.</span></span> <span data-ttu-id="6fd2e-108">El serializador omite de forma predeterminada los constructores no públicos, incluidos los que no tienen parámetros.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-108">Non-public constructors, including parameterless constructors, are ignored by the serializer by default.</span></span> <span data-ttu-id="6fd2e-109">El serializador usa uno de los constructores siguientes para la deserialización:</span><span class="sxs-lookup"><span data-stu-id="6fd2e-109">The serializer uses one of the following constructors for deserialization:</span></span>

- <span data-ttu-id="6fd2e-110">Constructor público anotado con <xref:System.Text.Json.Serialization.JsonConstructorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-110">Public constructor annotated with <xref:System.Text.Json.Serialization.JsonConstructorAttribute>.</span></span>
- <span data-ttu-id="6fd2e-111">Constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-111">Public parameterless constructor.</span></span>
- <span data-ttu-id="6fd2e-112">Constructor público con parámetros (si es el único constructor público presente).</span><span class="sxs-lookup"><span data-stu-id="6fd2e-112">Public parameterized constructor (if it's the only public constructor present).</span></span>

<span data-ttu-id="6fd2e-113">Si ninguno de estos constructores está disponible, se inicia una excepción <xref:System.NotSupportedException> si intenta deserializar el tipo.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-113">If none of these constructors are available, a <xref:System.NotSupportedException> is thrown if you attempt to deserialize the type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6fd2e-114">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="6fd2e-114">Version introduced</span></span>

<span data-ttu-id="6fd2e-115">5.0</span><span class="sxs-lookup"><span data-stu-id="6fd2e-115">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6fd2e-116">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="6fd2e-116">Reason for change</span></span>

- <span data-ttu-id="6fd2e-117">Aplicar un comportamiento coherente entre todos los monikers de la plataforma de destino (TFM) para los que se compila <xref:System.Text.Json?displayProperty=fullName> (.NET Core 3.0 y versiones posteriores, y .NET Standard 2.0)</span><span class="sxs-lookup"><span data-stu-id="6fd2e-117">To enforce consistent behavior between all target framework monikers (TFMs) that <xref:System.Text.Json?displayProperty=fullName> builds for (.NET Core 3.0 and later versions and .NET Standard 2.0)</span></span>
- <span data-ttu-id="6fd2e-118"><xref:System.Text.Json.JsonSerializer> no debe llamar al área expuesta no pública de un tipo, ya sea un constructor, una propiedad o un campo.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-118">Because <xref:System.Text.Json.JsonSerializer> shouldn't call the non-public surface area of a type, whether that's a constructor, a property, or a field.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6fd2e-119">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="6fd2e-119">Recommended action</span></span>

- <span data-ttu-id="6fd2e-120">Si es el propietario del tipo y es factible, convierta en público el constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-120">If you own the type and it's feasible, make the parameterless constructor public.</span></span>
- <span data-ttu-id="6fd2e-121">De lo contrario, implemente un elemento `JsonConverter<T>` para el tipo y controle el comportamiento de la deserialización.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-121">Otherwise, implement a `JsonConverter<T>` for the type and control the deserialization behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="6fd2e-122">Categoría</span><span class="sxs-lookup"><span data-stu-id="6fd2e-122">Category</span></span>

<span data-ttu-id="6fd2e-123">Serialización</span><span class="sxs-lookup"><span data-stu-id="6fd2e-123">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6fd2e-124">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6fd2e-124">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
