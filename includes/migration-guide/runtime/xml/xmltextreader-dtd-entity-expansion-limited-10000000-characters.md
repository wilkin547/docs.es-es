---
ms.openlocfilehash: e56d896f093d6cd28ed0d6640ba154e5d4593c6d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497265"
---
### <a name="xmltextreader-dtd-entity-expansion-is-limited-to-10000000-characters"></a><span data-ttu-id="83ddd-101">La expansión de entidades DTD de XmlTextReader está limitada a 10 000 000 caracteres</span><span class="sxs-lookup"><span data-stu-id="83ddd-101">XmlTextReader DTD entity expansion is limited to 10,000,000 characters</span></span>

#### <a name="details"></a><span data-ttu-id="83ddd-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="83ddd-102">Details</span></span>

<span data-ttu-id="83ddd-103">La expansión de entidades DTD ahora está limitada a 10 000 000 caracteres.</span><span class="sxs-lookup"><span data-stu-id="83ddd-103">DTD entity expansion is now limited to 10,000,000 characters.</span></span> <span data-ttu-id="83ddd-104">La carga de archivos XML sin expansión de entidades DTD o con expansión de entidades DTD limitada no se verá afectada.</span><span class="sxs-lookup"><span data-stu-id="83ddd-104">Loading XML files without DTD entity expansion or with limited DTD entity expansion is unaffected.</span></span> <span data-ttu-id="83ddd-105">Los archivos con entidades de DTD que se expanden a más de 10.000.000 caracteres no se podrán cargar y ahora iniciarán una excepción.</span><span class="sxs-lookup"><span data-stu-id="83ddd-105">Files with DTD entities that expand to more than 10,000,000 characters fail to load, and now throw an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="83ddd-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="83ddd-106">Suggestion</span></span>

<span data-ttu-id="83ddd-107">Si el límite de expansión de entidades DTD de 10 000 000 es demasiado bajo, el valor se puede anular con la propiedad <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities>.</span><span class="sxs-lookup"><span data-stu-id="83ddd-107">If the limit of DTD entity expansion is too low 10,000,000, the value can be overridden with the <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities> property.</span></span> <span data-ttu-id="83ddd-108">Se puede pasar un <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> con el valor <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> adecuado a <code>XmlReader.Create</code> que toma <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> (por ejemplo, <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>).</span><span class="sxs-lookup"><span data-stu-id="83ddd-108">An <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> with the proper <xref:System.Xml.XmlReaderSettings.MaxCharactersFromEntities?displayProperty=fullName> value can be passed to <code>XmlReader.Create</code> that takes <xref:System.Xml.XmlReaderSettings?displayProperty=fullName> (ie. <xref:System.Xml.XmlReader.Create(System.String,System.Xml.XmlReaderSettings)>)</span></span>

| <span data-ttu-id="83ddd-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="83ddd-109">Name</span></span>    | <span data-ttu-id="83ddd-110">Valor</span><span class="sxs-lookup"><span data-stu-id="83ddd-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="83ddd-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="83ddd-111">Scope</span></span>   |<span data-ttu-id="83ddd-112">Borde</span><span class="sxs-lookup"><span data-stu-id="83ddd-112">Edge</span></span>|
|<span data-ttu-id="83ddd-113">Versión</span><span class="sxs-lookup"><span data-stu-id="83ddd-113">Version</span></span>|<span data-ttu-id="83ddd-114">4.5</span><span class="sxs-lookup"><span data-stu-id="83ddd-114">4.5</span></span>|
|<span data-ttu-id="83ddd-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="83ddd-115">Type</span></span>|<span data-ttu-id="83ddd-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="83ddd-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="83ddd-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="83ddd-117">Affected APIs</span></span>

- <xref:System.Xml.XmlTextReader?displayProperty=nameWithType>
- <xref:System.Xml.XmlTextReader.%23ctor>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.IO.TextReader,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNameTable)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)>
- <xref:System.Xml.XmlTextReader.%23ctor(System.Xml.XmlNameTable)>

<!--

#### Affected APIs

- `T:System.Xml.XmlTextReader`
- `M:System.Xml.XmlTextReader.#ctor`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.Stream,System.Xml.XmlNodeType,System.Xml.XmlParserContext)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.TextReader)`
- `M:System.Xml.XmlTextReader.#ctor(System.IO.TextReader,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.Stream)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.Stream,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.TextReader)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.IO.TextReader,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.Xml.XmlNameTable)`
- `M:System.Xml.XmlTextReader.#ctor(System.String,System.Xml.XmlNodeType,System.Xml.XmlParserContext)`
- `M:System.Xml.XmlTextReader.#ctor(System.Xml.XmlNameTable)`

-->
