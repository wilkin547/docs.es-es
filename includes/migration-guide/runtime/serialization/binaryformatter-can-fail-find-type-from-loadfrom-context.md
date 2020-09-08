---
ms.openlocfilehash: ccba3cf98a1ca9e199d9a48f00e254bf34b93f72
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497130"
---
### <a name="binaryformatter-can-fail-to-find-type-from-loadfrom-context"></a><span data-ttu-id="624ea-101">BinaryFormatter no puede encontrar el tipo en el contexto LoadFrom</span><span class="sxs-lookup"><span data-stu-id="624ea-101">BinaryFormatter can fail to find type from LoadFrom context</span></span>

#### <a name="details"></a><span data-ttu-id="624ea-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="624ea-102">Details</span></span>

<span data-ttu-id="624ea-103">A partir de .NET Framework 4.5, un número de cambios en <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> pueden provocar diferencias en la deserialización al usar <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> para deserializar los tipos que se han cargado en el contexto LoadFrom.</span><span class="sxs-lookup"><span data-stu-id="624ea-103">As of .NET Framework 4.5, a number of <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> changes may cause differences in deserialization when using <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> to deserialize types that had been loaded in the LoadFrom context.</span></span> <span data-ttu-id="624ea-104">Estos cambios se deben a las nuevas formas en las que <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> carga ahora un tipo que provoca otro comportamiento cuando un <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> intenta deserializar en ese tipo más adelante.</span><span class="sxs-lookup"><span data-stu-id="624ea-104">These changes are due to the new ways <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> now loads a type which causes different behavior when a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> attempts to deserialize to that type later on.</span></span> <span data-ttu-id="624ea-105">El enlazador de serialización predeterminado no busca automáticamente en el contexto LoadFrom, aunque es posible que haya funcionado en algunas circunstancias según el comportamiento anterior de XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="624ea-105">The default serialization binder does not automatically search the LoadFrom context, although it may have worked in some circumstances based on the old behavior of XmlSerializer.</span></span> <span data-ttu-id="624ea-106">Debido a los cambios, cuando se carga un tipo desde un ensamblado cargado en un otro contexto, se puede iniciar una excepción <xref:System.IO.FileNotFoundException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="624ea-106">Due to the changes, when a type is being loaded from an assembly loaded in a different context, a <xref:System.IO.FileNotFoundException?displayProperty=fullName> may be thrown.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="624ea-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="624ea-107">Suggestion</span></span>

<span data-ttu-id="624ea-108">Si esta excepción aparece, la propiedad <code>Binder</code> del <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> se puede establecer en un enlazador predeterminado que encontrará el tipo correcto.</span><span class="sxs-lookup"><span data-stu-id="624ea-108">If this exception is seen, the <code>Binder</code> property of the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> can be set to a custom binder that will find the correct type.</span></span><pre><code class="lang-csharp">var formatter = new BinaryFormatter { Binder = new TypeFinderBinder() }&#13;&#10;</code></pre><span data-ttu-id="624ea-109">Y, después, el enlazador predeterminado:</span><span class="sxs-lookup"><span data-stu-id="624ea-109">And then the custom binder:</span></span><pre><code class="lang-csharp">public class TypeFinderBinder : SerializationBinder&#13;&#10;{&#13;&#10;private static readonly string s_assemblyName = Assembly.GetExecutingAssembly().FullName;&#13;&#10;&#13;&#10;public override Type BindToType(string assemblyName, string typeName)&#13;&#10;{&#13;&#10;return Type.GetType(String.Format(CultureInfo.InvariantCulture, &quot;{0}, {1}&quot;, typeName, s_assemblyName));&#13;&#10;}&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="624ea-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="624ea-110">Name</span></span>    | <span data-ttu-id="624ea-111">Valor</span><span class="sxs-lookup"><span data-stu-id="624ea-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="624ea-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="624ea-112">Scope</span></span>   |<span data-ttu-id="624ea-113">Borde</span><span class="sxs-lookup"><span data-stu-id="624ea-113">Edge</span></span>|
|<span data-ttu-id="624ea-114">Versión</span><span class="sxs-lookup"><span data-stu-id="624ea-114">Version</span></span>|<span data-ttu-id="624ea-115">4.5</span><span class="sxs-lookup"><span data-stu-id="624ea-115">4.5</span></span>|
|<span data-ttu-id="624ea-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="624ea-116">Type</span></span>|<span data-ttu-id="624ea-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="624ea-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="624ea-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="624ea-118">Affected APIs</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream)`
- `M:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize(System.IO.Stream,System.Runtime.Remoting.Messaging.HeaderHandler)`

-->
