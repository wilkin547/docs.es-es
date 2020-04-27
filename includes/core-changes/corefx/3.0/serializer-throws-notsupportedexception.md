---
ms.openlocfilehash: cc3251e3b31143bd95793b407e50cf76e0e30142
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021663"
---
### <a name="json-serializer-exception-type-changed-from-jsonexception-to-notsupportedexception"></a><span data-ttu-id="71924-101">Cambio del tipo de excepción del serializador de JSON de `JsonException` a `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="71924-101">Json serializer exception type changed from `JsonException` to `NotSupportedException`</span></span>

<span data-ttu-id="71924-102">De la versión preliminar 6 a la 8 de .NET Core 3.0, el serializador producirá una <xref:System.Text.Json.JsonException> cuando encuentre un tipo de colección derivada no compatible.</span><span class="sxs-lookup"><span data-stu-id="71924-102">In .NET Core 3.0 Preview 6 through 8, the serializer would throw a <xref:System.Text.Json.JsonException> when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="71924-103">A partir de la versión preliminar 9 de .NET Core 3.0, el serializador produce una <xref:System.NotSupportedException> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="71924-103">Starting in .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> instead.</span></span>

#### <a name="change-description"></a><span data-ttu-id="71924-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="71924-104">Change description</span></span>

<span data-ttu-id="71924-105">De la versión preliminar 6 a la versión preliminar 8 de .NET Core 3.0, el serializador producirá una <xref:System.Text.Json.JsonException> cuando encuentre un tipo de colección derivada no compatible.</span><span class="sxs-lookup"><span data-stu-id="71924-105">In .NET Core 3.0 Preview 6 through Preview 8, the serializer would throw a <xref:System.Text.Json.JsonException>  when it encountered an unsupported derived collection type.</span></span> <span data-ttu-id="71924-106">Un *tipo de colección derivada no compatible* es cualquier tipo de colección que no se puede asignar a uno de los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="71924-106">An *unsupported derived collection type* is any collection type that isn't assignable to one of the following types:</span></span>

- <xref:System.Collections.IList>
- <xref:System.Collections.Generic.ICollection%601>
- <xref:System.Collections.Generic.Stack%601>
- <xref:System.Collections.Generic.Queue%601>
- <xref:System.Collections.IDictionary>
- [<span data-ttu-id="71924-107">IDictionary\<Cadena,T></span><span class="sxs-lookup"><span data-stu-id="71924-107">IDictionary\<String,T></span></span>](xref:System.Collections.Generic.IDictionary%602)

<span data-ttu-id="71924-108">A partir de la versión preliminar 9 de .NET Core 3.0, el serializador produce una <xref:System.NotSupportedException> al encontrar un tipo de colección no compatible.</span><span class="sxs-lookup"><span data-stu-id="71924-108">Starting with .NET Core 3.0 Preview 9, the serializer throws a <xref:System.NotSupportedException> When encountering an unsupported collection type.</span></span> <span data-ttu-id="71924-109">El nuevo tipo de excepción refleja mejor por qué se produce un error en la operación de deserialización.</span><span class="sxs-lookup"><span data-stu-id="71924-109">The new exception type better reflects why the deserialization operation is failing.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="71924-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="71924-110">Version introduced</span></span>

<span data-ttu-id="71924-111">3.0 (versión preliminar 9)</span><span class="sxs-lookup"><span data-stu-id="71924-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="71924-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="71924-112">Recommended action</span></span>

<span data-ttu-id="71924-113">Si al deserializar detecta <xref:System.Text.Json.JsonException>, es posible que también quiera considerar la posibilidad de detectar <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="71924-113">If you're catching <xref:System.Text.Json.JsonException> when deserializing, you might want to consider also catching <xref:System.NotSupportedException>.</span></span>

#### <a name="category"></a><span data-ttu-id="71924-114">Categoría</span><span class="sxs-lookup"><span data-stu-id="71924-114">Category</span></span>

<span data-ttu-id="71924-115">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="71924-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="71924-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="71924-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
