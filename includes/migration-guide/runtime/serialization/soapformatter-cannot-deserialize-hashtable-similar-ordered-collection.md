---
ms.openlocfilehash: 71cc7119710a2b381626dd9cf4ab66265eb3deba
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497057"
---
### <a name="soapformatter-cannot-deserialize-hashtable-and-similar-ordered-collection-objects"></a><span data-ttu-id="d2892-101">SoapFormatter no puede deserializar elementos Hashtable ni otros objetos de colecciones ordenados similares</span><span class="sxs-lookup"><span data-stu-id="d2892-101">SoapFormatter cannot deserialize Hashtable and similar ordered collection objects</span></span>

#### <a name="details"></a><span data-ttu-id="d2892-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="d2892-102">Details</span></span>

<span data-ttu-id="d2892-103"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> no garantiza que los objetos serializados en una versión de .NET Framework se deserialicen correctamente en otra versión.</span><span class="sxs-lookup"><span data-stu-id="d2892-103">The <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> does not guarantee that objects serialized under one .NET Framework version will successfully deserialize under a different version.</span></span> <span data-ttu-id="d2892-104">En concreto, en algunas colecciones ordenadas (como <xref:System.Collections.Hashtable?displayProperty=fullName>) se agregaron miembros entre las versiones 4.0 y 4.5, de modo que los objetos de estos tipos no se pueden deserializar con .NET Framework 4.0 si se serializaron con .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="d2892-104">Specifically, some ordered collections (like <xref:System.Collections.Hashtable?displayProperty=fullName>) added members between 4.0 and 4.5 such that objects of these types cannot deserialize with .NET Framework 4.0 if they were serialized with .NET Framework 4.5.</span></span> <span data-ttu-id="d2892-105">Si los datos se serializaron y deserializaron con la misma versión de .NET Framework, no ocurrirá ningún problema.</span><span class="sxs-lookup"><span data-stu-id="d2892-105">Note that if the serialized data is both serialized and deserialized with the same .NET Framework version, no issue will occur.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d2892-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="d2892-106">Suggestion</span></span>

<span data-ttu-id="d2892-107">La serialización de <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> se debe reemplazar por la de <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> o <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> para que sea resistente a los cambios de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d2892-107"><xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter?displayProperty=fullName> serialization should be replaced with <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> serialization or <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=fullName> to be resilient to .NET Framework changes.</span></span>

| <span data-ttu-id="d2892-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="d2892-108">Name</span></span>    | <span data-ttu-id="d2892-109">Valor</span><span class="sxs-lookup"><span data-stu-id="d2892-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d2892-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="d2892-110">Scope</span></span>   |<span data-ttu-id="d2892-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="d2892-111">Minor</span></span>|
|<span data-ttu-id="d2892-112">Versión</span><span class="sxs-lookup"><span data-stu-id="d2892-112">Version</span></span>|<span data-ttu-id="d2892-113">4.5</span><span class="sxs-lookup"><span data-stu-id="d2892-113">4.5</span></span>|
|<span data-ttu-id="d2892-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="d2892-114">Type</span></span>|<span data-ttu-id="d2892-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="d2892-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d2892-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d2892-116">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object)`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Serialize(System.IO.Stream,System.Object,System.Runtime.Remoting.Messaging.Header[])`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Soap.SoapFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
