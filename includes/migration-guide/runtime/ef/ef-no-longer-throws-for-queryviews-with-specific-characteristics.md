---
ms.openlocfilehash: ceae6b85c14862b1b1183d01def0dda723ee0c2b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496259"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a><span data-ttu-id="26119-101">EF ya no inicia excepciones para elementos QueryView con características específicas</span><span class="sxs-lookup"><span data-stu-id="26119-101">EF no longer throws for QueryViews with specific characteristics</span></span>

#### <a name="details"></a><span data-ttu-id="26119-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="26119-102">Details</span></span>

<span data-ttu-id="26119-103">Entity Framework ya no inicia una excepción <xref:System.StackOverflowException?displayProperty=fullName> cuando una aplicación ejecuta una consulta que usa QueryView con una propiedad de navegación 0..1 que intenta incluir las entidades relacionadas como parte de la consulta.</span><span class="sxs-lookup"><span data-stu-id="26119-103">Entity Framework no longer throws a <xref:System.StackOverflowException?displayProperty=fullName> exception when an app executes a query that involves a QueryView with a 0..1 navigation property that attempts to include the related entities as part of the query.</span></span> <span data-ttu-id="26119-104">Por ejemplo, mediante una llamada a <code>.Include(e =&gt; e.RelatedNavProp)</code>.</span><span class="sxs-lookup"><span data-stu-id="26119-104">For example, by calling <code>.Include(e =&gt; e.RelatedNavProp)</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="26119-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="26119-105">Suggestion</span></span>

<span data-ttu-id="26119-106">Este cambio solo afecta al código que usa QueryViews con relaciones 1-0..1 cuando se ejecutan consultas que realizan llamadas a .Include.</span><span class="sxs-lookup"><span data-stu-id="26119-106">This change only affects code that uses QueryViews with 1-0..1 relationships when running queries that call .Include.</span></span> <span data-ttu-id="26119-107">Mejora la fiabilidad y debe ser transparente para casi todas las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="26119-107">It improves reliability and should be transparent to almost all apps.</span></span> <span data-ttu-id="26119-108">Pero puede deshabilitarlo si causa un comportamiento inesperado; para ello, agregue la entrada siguiente a la sección <code>&lt;appSettings&gt;</code> del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="26119-108">However, if it causes unexpected behavior, you can disable it by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the app's configuration file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="26119-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="26119-109">Name</span></span>    | <span data-ttu-id="26119-110">Valor</span><span class="sxs-lookup"><span data-stu-id="26119-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="26119-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="26119-111">Scope</span></span>   |<span data-ttu-id="26119-112">Borde</span><span class="sxs-lookup"><span data-stu-id="26119-112">Edge</span></span>|
|<span data-ttu-id="26119-113">Versión</span><span class="sxs-lookup"><span data-stu-id="26119-113">Version</span></span>|<span data-ttu-id="26119-114">4.5.2</span><span class="sxs-lookup"><span data-stu-id="26119-114">4.5.2</span></span>|
|<span data-ttu-id="26119-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="26119-115">Type</span></span>|<span data-ttu-id="26119-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="26119-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="26119-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="26119-117">Affected APIs</span></span>

<span data-ttu-id="26119-118">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="26119-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
