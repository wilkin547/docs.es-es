---
ms.openlocfilehash: 277a91fbfbf0c6aaaa0dc044ef0c079ad8607699
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497809"
---
### <a name="blockingcollectionlttgttrytakefromany-does-not-throw-anymore"></a><span data-ttu-id="23d53-101">BlockingCollection&lt;T&gt;.TryTakeFromAny ya no inicia excepciones</span><span class="sxs-lookup"><span data-stu-id="23d53-101">BlockingCollection&lt;T&gt;.TryTakeFromAny does not throw anymore</span></span>

#### <a name="details"></a><span data-ttu-id="23d53-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="23d53-102">Details</span></span>

<span data-ttu-id="23d53-103">Si alguna de las colecciones de entrada está marcada como completada, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no devuelve -1 y <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> deja de iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="23d53-103">If one of the input collections is marked completed, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer returns -1 and <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer throws an exception.</span></span> <span data-ttu-id="23d53-104">Este cambio permite trabajar con colecciones cuando una de las colecciones está vacía o completa y la otra colección todavía tiene elementos que se pueden recuperar.</span><span class="sxs-lookup"><span data-stu-id="23d53-104">This change makes it possible to work with collections when one of the collections is either empty or completed, but the other collection still has items that can be retrieved.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="23d53-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="23d53-105">Suggestion</span></span>

<span data-ttu-id="23d53-106">Si se han usado un método TryTakeFromAny que devuelva -1 o un método TakeFromAny de inicio para el control de flujo en casos en los que se complete una recolección de bloqueo, es necesario cambiar dicho código para que use <code>.Any(b =&gt; b.IsCompleted)</code> para detectar dicha condición.</span><span class="sxs-lookup"><span data-stu-id="23d53-106">If TryTakeFromAny returning -1 or TakeFromAny throwing were used for control-flow purposes in cases of a blocking collection being completed, such code should now be changed to use <code>.Any(b =&gt; b.IsCompleted)</code> to detect that condition.</span></span>

| <span data-ttu-id="23d53-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="23d53-107">Name</span></span>    | <span data-ttu-id="23d53-108">Valor</span><span class="sxs-lookup"><span data-stu-id="23d53-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="23d53-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="23d53-109">Scope</span></span>   |<span data-ttu-id="23d53-110">Secundaria</span><span class="sxs-lookup"><span data-stu-id="23d53-110">Minor</span></span>|
|<span data-ttu-id="23d53-111">Versión</span><span class="sxs-lookup"><span data-stu-id="23d53-111">Version</span></span>|<span data-ttu-id="23d53-112">4.5</span><span class="sxs-lookup"><span data-stu-id="23d53-112">4.5</span></span>|
|<span data-ttu-id="23d53-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="23d53-113">Type</span></span>|<span data-ttu-id="23d53-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="23d53-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="23d53-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="23d53-115">Affected APIs</span></span>

- <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Concurrent.BlockingCollection`1.TakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.Threading.CancellationToken)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.Int32)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.TimeSpan)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.TimeSpan)``

-->
