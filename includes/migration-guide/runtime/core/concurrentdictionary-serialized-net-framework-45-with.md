---
ms.openlocfilehash: 450bfc56c99a3df9be71be2ef7df6e4e12d4ed76
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497903"
---
### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a><span data-ttu-id="0c40e-101">Un elemento ConcurrentDictionary serializado en .NET Framework 4.5 con NetDataContractSerializer no se puede deserializar en .NET Framework 4.5.1 ni 4.5.2</span><span class="sxs-lookup"><span data-stu-id="0c40e-101">A ConcurrentDictionary serialized in .NET Framework 4.5 with NetDataContractSerializer cannot be deserialized by .NET Framework 4.5.1 or 4.5.2</span></span>

#### <a name="details"></a><span data-ttu-id="0c40e-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="0c40e-102">Details</span></span>

<span data-ttu-id="0c40e-103">Debido a los cambios internos en el tipo, los objetos <xref:System.Collections.Concurrent.ConcurrentDictionary%602> que se serializaron con .NET Framework 4.5 mediante <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> no se pueden deserializar en .NET Framework 4.5.1 o 4.5.2. Tenga en cuenta que a la inversa sí funciona (la serialización con .NET Framework 4.5.x y la deserialización con .NET Framework 4.5).</span><span class="sxs-lookup"><span data-stu-id="0c40e-103">Due to internal changes to the type, <xref:System.Collections.Concurrent.ConcurrentDictionary%602> objects that are serialized with the .NET Framework 4.5 using the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> cannot be deserialized in the .NET Framework 4.5.1 or in the .NET Framework 4.5.2.Note that moving in the other direction (serializing with the .NET Framework 4.5.x and deserializing with the .NET Framework 4.5) works.</span></span> <span data-ttu-id="0c40e-104">Del mismo modo, la serialización entre todas las versiones 4.x funciona con .NET Framework 4.6. La serialización y deserialización con una única versión de .NET Framework no se ve afectada.</span><span class="sxs-lookup"><span data-stu-id="0c40e-104">Similarly, all 4.x cross-version serialization works with the .NET Framework 4.6.Serializing and deserializing with a single version of the .NET Framework is not affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0c40e-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="0c40e-105">Suggestion</span></span>

<span data-ttu-id="0c40e-106">Si es necesario serializar y deserializar <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> entre .NET Framework 4.5 y 4.5.1/4.5.2, se debe usar un serializador alternativo como <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> o <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> en lugar de <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>. Como alternativa, dado que este problema se corrige en .NET Framework 4.6, se podría resolver mediante la actualización a esa versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0c40e-106">If it is necessary to serialize and deserialize a <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> between the .NET Framework 4.5 and .NET Framework 4.5.1/4.5.2, an alternate serializer like the <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> or <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serializer should be used instead of the <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName>.Alternatively, because this issue is addressed in the .NET Framework 4.6, it may be solved by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="0c40e-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="0c40e-107">Name</span></span>    | <span data-ttu-id="0c40e-108">Valor</span><span class="sxs-lookup"><span data-stu-id="0c40e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0c40e-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0c40e-109">Scope</span></span>   |<span data-ttu-id="0c40e-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="0c40e-110">Minor</span></span>|
|<span data-ttu-id="0c40e-111">Versión</span><span class="sxs-lookup"><span data-stu-id="0c40e-111">Version</span></span>|<span data-ttu-id="0c40e-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="0c40e-112">4.5.1</span></span>|
|<span data-ttu-id="0c40e-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="0c40e-113">Type</span></span>|<span data-ttu-id="0c40e-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0c40e-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0c40e-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0c40e-115">Affected APIs</span></span>

<span data-ttu-id="0c40e-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="0c40e-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
