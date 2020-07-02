---
ms.openlocfilehash: 5a3370e71488e4f9d8d933b504d1d771c78e0385
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620659"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a><span data-ttu-id="76236-101">SoapFormatter no puede deserializar elementos Hashtable ni otros objetos de colecciones ordenados similares</span><span class="sxs-lookup"><span data-stu-id="76236-101">SoapFormatter cannot deserialize Hashtable and similar ordered collection objects</span></span>

#### <a name="details"></a><span data-ttu-id="76236-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="76236-102">Details</span></span>

<span data-ttu-id="76236-103"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> no garantiza que los objetos serializados en una versión de .NET Framework se deserialicen correctamente en otra versión.</span><span class="sxs-lookup"><span data-stu-id="76236-103">The <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> does not guarantee that objects serialized under one .NET Framework version will successfully deserialize under a different version.</span></span> <span data-ttu-id="76236-104">En concreto, en algunas colecciones ordenadas (como <xref:System.Collections.Hashtable?displayProperty=fullName>) se agregaron miembros entre las versiones 4.0 y 4.5, de modo que los objetos de estos tipos no se pueden deserializar con .NET Framework 4.0 si se serializaron con .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="76236-104">Specifically, some ordered collections (like <xref:System.Collections.Hashtable?displayProperty=fullName>) added members between 4.0 and 4.5 such that objects of these types cannot deserialize with .NET Framework 4.0 if they were serialized with .NET Framework 4.5.</span></span> <span data-ttu-id="76236-105">Si los datos se serializaron y deserializaron con la misma versión de .NET Framework, no ocurrirá ningún problema.</span><span class="sxs-lookup"><span data-stu-id="76236-105">Note that if the serialized data is both serialized and deserialized with the same .NET Framework version, no issue will occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="76236-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="76236-106">Suggestion</span></span>

<span data-ttu-id="76236-107">La serialización de <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> se debe reemplazar por la de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> o <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> para que sea resistente a los cambios de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="76236-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> serialization should be replaced with <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serialization or <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> to be resilient to .NET Framework changes.</span></span>

| <span data-ttu-id="76236-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="76236-108">Name</span></span>    | <span data-ttu-id="76236-109">Valor</span><span class="sxs-lookup"><span data-stu-id="76236-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="76236-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="76236-110">Scope</span></span>   |<span data-ttu-id="76236-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="76236-111">Minor</span></span>|
|<span data-ttu-id="76236-112">Versión</span><span class="sxs-lookup"><span data-stu-id="76236-112">Version</span></span>|<span data-ttu-id="76236-113">4.5</span><span class="sxs-lookup"><span data-stu-id="76236-113">4.5</span></span>|
|<span data-ttu-id="76236-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="76236-114">Type</span></span>|<span data-ttu-id="76236-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="76236-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="76236-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="76236-116">Affected APIs</span></span>

-<xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li><li><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType></li></ul>|
