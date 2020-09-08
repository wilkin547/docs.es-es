---
ms.openlocfilehash: 6c120f155660863ce5ae3cf5bd81ea858a68ef8d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497013"
---
### <a name="netdatacontractserializer-fails-to-deserialize-a-concurrentdictionary-serialized-with-a-different-net-version"></a><span data-ttu-id="fd790-101">NetDataContractSerializer no puede deserializar un elemento ConcurrentDictionary serializado con otra versión de .NET</span><span class="sxs-lookup"><span data-stu-id="fd790-101">NetDataContractSerializer fails to deserialize a ConcurrentDictionary serialized with a different .NET version</span></span>

#### <a name="details"></a><span data-ttu-id="fd790-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="fd790-102">Details</span></span>

<span data-ttu-id="fd790-103">Por diseño, solo se puede usar <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> si los extremos de serialización y de deserialización comparten los mismos tipos CLR.</span><span class="sxs-lookup"><span data-stu-id="fd790-103">By design, the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="fd790-104">Por tanto, no se garantiza que un objeto serializado con una versión de .NET Framework se pueda deserializar con otra versión. <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fd790-104">Therefore, it is not guaranteed that an object serialized with one version of the .NET Framework can be deserialized by a different version.<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName></span></span> <span data-ttu-id="fd790-105">es un tipo conocido por no deserializarse correctamente si se serializó con .NET Framework 4.5 o versiones anteriores, y se deserializó con .NET Framework 4.5.1 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="fd790-105">is a type that is known to not to deserialize correctly if serialized with the .NET Framework 4.5 or earlier and deserialized with the .NET Framework 4.5.1 or later.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="fd790-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="fd790-106">Suggestion</span></span>

<span data-ttu-id="fd790-107">Hay una serie de soluciones posibles para este problema:</span><span class="sxs-lookup"><span data-stu-id="fd790-107">There are a number of possible work-arounds for this issue:</span></span><ul><li><span data-ttu-id="fd790-108">Actualice el equipo que realiza la serialización para usar .NET Framework 4.5.1 también.</span><span class="sxs-lookup"><span data-stu-id="fd790-108">Upgrade the serializing computer to use the .NET Framework 4.5.1, as well.</span></span></li><li><span data-ttu-id="fd790-109">Use <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> en lugar de <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> dado que no espera los mismos tipos CLR exactos en los extremos de serialización y deserialización.</span><span class="sxs-lookup"><span data-stu-id="fd790-109">Use <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> instead of <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> as this does not expect the exact same CLR types at both serializing and deserializing ends.</span></span></li><li><span data-ttu-id="fd790-110">Use <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> en lugar de <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> dado que no muestra esta interrupción determinada de 4.5-&gt;4.5.1.</span><span class="sxs-lookup"><span data-stu-id="fd790-110">Use <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> instead of <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> since it does not exhibit this particular 4.5-&gt;4.5.1 break.</span></span></li></ul>

| <span data-ttu-id="fd790-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="fd790-111">Name</span></span>    | <span data-ttu-id="fd790-112">Valor</span><span class="sxs-lookup"><span data-stu-id="fd790-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="fd790-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="fd790-113">Scope</span></span>   |<span data-ttu-id="fd790-114">Secundaria</span><span class="sxs-lookup"><span data-stu-id="fd790-114">Minor</span></span>|
|<span data-ttu-id="fd790-115">Versión</span><span class="sxs-lookup"><span data-stu-id="fd790-115">Version</span></span>|<span data-ttu-id="fd790-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="fd790-116">4.5.1</span></span>|
|<span data-ttu-id="fd790-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="fd790-117">Type</span></span>|<span data-ttu-id="fd790-118">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="fd790-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="fd790-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="fd790-119">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)`

-->
