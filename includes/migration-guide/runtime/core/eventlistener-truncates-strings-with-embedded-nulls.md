---
ms.openlocfilehash: e47a24239872e3fe86ff6902f66b38daaa106598
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497588"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a><span data-ttu-id="a6a32-101">EventListener trunca las cadenas con valores NULL insertados</span><span class="sxs-lookup"><span data-stu-id="a6a32-101">EventListener truncates strings with embedded nulls</span></span>

#### <a name="details"></a><span data-ttu-id="a6a32-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a6a32-102">Details</span></span>

<span data-ttu-id="a6a32-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> trunca las cadenas con valores NULL incrustados.</span><span class="sxs-lookup"><span data-stu-id="a6a32-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> truncates strings with embedded nulls.</span></span> <span data-ttu-id="a6a32-104">Los caracteres NULL no son compatibles con la clase <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="a6a32-104">Null characters are not supported by the <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> class.</span></span> <span data-ttu-id="a6a32-105">El cambio solo afecta a las aplicaciones que usan <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> para leer datos <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> en proceso y que utilizan caracteres NULL como delimitadores.</span><span class="sxs-lookup"><span data-stu-id="a6a32-105">The change only affects apps that use <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> to read <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process and that use null characters as delimiters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a6a32-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a6a32-106">Suggestion</span></span>

<span data-ttu-id="a6a32-107">Se deben actualizar los datos de <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>, si es posible, para que no usen valores NULL insertados.</span><span class="sxs-lookup"><span data-stu-id="a6a32-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data should be updated, if possible, to not use embedded null characters.</span></span>

| <span data-ttu-id="a6a32-108">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="a6a32-108">Name</span></span>    | <span data-ttu-id="a6a32-109">Valor</span><span class="sxs-lookup"><span data-stu-id="a6a32-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a6a32-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a6a32-110">Scope</span></span>   |<span data-ttu-id="a6a32-111">Borde</span><span class="sxs-lookup"><span data-stu-id="a6a32-111">Edge</span></span>|
|<span data-ttu-id="a6a32-112">Versión</span><span class="sxs-lookup"><span data-stu-id="a6a32-112">Version</span></span>|<span data-ttu-id="a6a32-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="a6a32-113">4.5.1</span></span>|
|<span data-ttu-id="a6a32-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="a6a32-114">Type</span></span>|<span data-ttu-id="a6a32-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a6a32-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a6a32-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a6a32-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Tracing.EventListener.%23ctor>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.#ctor`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})`

-->
