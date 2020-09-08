---
ms.openlocfilehash: 06424c4fa40343a881356c20003300f65e93efbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497780"
---
### <a name="wf-serializes-expressionsliterallttgt-datetimes-differently-now-breaks-custom-xaml-parsers"></a><span data-ttu-id="7b2d4-101">WF ahora serializa el valor Expressions.Literal&lt;T&gt; DateTimes de forma diferente (interrumpe los analizadores de XAML personalizados)</span><span class="sxs-lookup"><span data-stu-id="7b2d4-101">WF serializes Expressions.Literal&lt;T&gt; DateTimes differently now (breaks custom XAML parsers)</span></span>

#### <a name="details"></a><span data-ttu-id="7b2d4-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="7b2d4-102">Details</span></span>

<span data-ttu-id="7b2d4-103">El objeto <xref:System.Windows.Markup.ValueSerializer> asociado convertirá un objeto <xref:System.DateTime?displayProperty=fullName> o <xref:System.DateTimeOffset?displayProperty=fullName> cuyos componentes Second y <xref:System.DateTime.Millisecond?displayProperty=fullName> sean distintos de cero y (para un valor <xref:System.DateTime?displayProperty=fullName>) cuya propiedad <xref:System.DateTime.Kind> no sea Unspecified en la sintaxis del elemento de propiedad en lugar de en una cadena.</span><span class="sxs-lookup"><span data-stu-id="7b2d4-103">The associated <xref:System.Windows.Markup.ValueSerializer> object will convert a <xref:System.DateTime?displayProperty=fullName> or <xref:System.DateTimeOffset?displayProperty=fullName> object whose Second and <xref:System.DateTime.Millisecond?displayProperty=fullName> components are non-zero and (for a <xref:System.DateTime?displayProperty=fullName> value) whose <xref:System.DateTime.Kind> property is not Unspecified to property element syntax instead of a string.</span></span> <span data-ttu-id="7b2d4-104">Este cambio permite realizar un recorrido de ida y vuelta por los valores <xref:System.DateTime?displayProperty=fullName> y <xref:System.DateTimeOffset?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="7b2d4-104">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="7b2d4-105">Los analizadores XAML personalizados que presuponen que la entrada XAML está en la sintaxis del atributo no funcionarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="7b2d4-105">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7b2d4-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="7b2d4-106">Suggestion</span></span>

<span data-ttu-id="7b2d4-107">Este cambio permite realizar un recorrido de ida y vuelta por los valores <xref:System.DateTime?displayProperty=fullName> y <xref:System.DateTimeOffset?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="7b2d4-107">This change allows <xref:System.DateTime?displayProperty=fullName> and <xref:System.DateTimeOffset?displayProperty=fullName> values to be round-tripped.</span></span> <span data-ttu-id="7b2d4-108">Los analizadores XAML personalizados que presuponen que la entrada XAML está en la sintaxis del atributo no funcionarán correctamente.</span><span class="sxs-lookup"><span data-stu-id="7b2d4-108">Custom XAML parsers that assume that input XAML is in the attribute syntax will not function correctly.</span></span>

| <span data-ttu-id="7b2d4-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="7b2d4-109">Name</span></span>    | <span data-ttu-id="7b2d4-110">Valor</span><span class="sxs-lookup"><span data-stu-id="7b2d4-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7b2d4-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="7b2d4-111">Scope</span></span>   |<span data-ttu-id="7b2d4-112">Borde</span><span class="sxs-lookup"><span data-stu-id="7b2d4-112">Edge</span></span>|
|<span data-ttu-id="7b2d4-113">Versión</span><span class="sxs-lookup"><span data-stu-id="7b2d4-113">Version</span></span>|<span data-ttu-id="7b2d4-114">4.5</span><span class="sxs-lookup"><span data-stu-id="7b2d4-114">4.5</span></span>|
|<span data-ttu-id="7b2d4-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="7b2d4-115">Type</span></span>|<span data-ttu-id="7b2d4-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="7b2d4-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="7b2d4-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7b2d4-117">Affected APIs</span></span>

<span data-ttu-id="7b2d4-118">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="7b2d4-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
