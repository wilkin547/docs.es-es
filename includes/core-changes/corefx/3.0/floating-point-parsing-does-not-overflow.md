---
ms.openlocfilehash: 935d9b2368ea4a0eeca7943dcbd584d24d2a6633
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721404"
---
### <a name="floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception"></a><span data-ttu-id="74f21-101">Las operaciones de análisis de punto flotante ya no producen un error o lanzan una excepción OverflowException</span><span class="sxs-lookup"><span data-stu-id="74f21-101">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>

<span data-ttu-id="74f21-102">Los métodos de análisis de punto flotante ya no lanzan una <xref:System.OverflowException> o devuelven `false` cuando analizan una cadena cuyo valor numérico está fuera del rango del tipo de punto flotante <xref:System.Single> o <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="74f21-102">The floating-point parsing methods no longer throw an <xref:System.OverflowException> or return `false` when they parse a string whose numeric value is outside the range of the <xref:System.Single> or <xref:System.Double> floating-point type.</span></span>

#### <a name="change-description"></a><span data-ttu-id="74f21-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="74f21-103">Change description</span></span>

<span data-ttu-id="74f21-104">En .NET Core 2.2 y versiones anteriores, los métodos <xref:System.Double.Parse%2A?displayProperty=nameWithType> y <xref:System.Single.Parse%2A?displayProperty=nameWithType> lanzan una <xref:System.OverflowException> para los valores que se encuentran fuera del rango de su tipo respectivo.</span><span class="sxs-lookup"><span data-stu-id="74f21-104">In .NET Core 2.2 and earlier versions, the <xref:System.Double.Parse%2A?displayProperty=nameWithType> and <xref:System.Single.Parse%2A?displayProperty=nameWithType> methods throw an <xref:System.OverflowException> for values that outside the range of their respective type.</span></span> <span data-ttu-id="74f21-105">Los métodos <xref:System.Double.TryParse%2A?displayProperty=nameWithType> y <xref:System.Single.TryParse%2A?displayProperty=nameWithType> devuelven `false` para las representaciones de cadena de valores numéricos fuera del rango.</span><span class="sxs-lookup"><span data-stu-id="74f21-105">The <xref:System.Double.TryParse%2A?displayProperty=nameWithType> and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> methods return `false` for the string representations of out-of-range numeric values.</span></span>

<span data-ttu-id="74f21-106">A partir de .NET Core 3.0, los métodos <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType> y <xref:System.Single.TryParse%2A?displayProperty=nameWithType> ya no producen errores al analizar cadenas numéricas fuera del rango.</span><span class="sxs-lookup"><span data-stu-id="74f21-106">Starting with .NET Core 3.0, the <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>, and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> methods no longer fail when parsing out-of-range numeric strings.</span></span> <span data-ttu-id="74f21-107">En su lugar, los métodos de análisis de <xref:System.Double> devuelven <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> para los valores que superan <xref:System.Double.MaxValue?displayProperty=nameWithType> y <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> para los valores menores que <xref:System.Double.MinValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="74f21-107">Instead, the <xref:System.Double> parsing methods return <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> for values that exceed <xref:System.Double.MaxValue?displayProperty=nameWithType>, and they return <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> for values that are less than <xref:System.Double.MinValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="74f21-108">Del mismo modo, los métodos de análisis de <xref:System.Single> devuelven <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> para los valores que superan <xref:System.Single.MaxValue?displayProperty=nameWithType> y <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> para los valores menores que <xref:System.Single.MinValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="74f21-108">Similarly, the <xref:System.Single> parsing methods return <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> for values that exceed <xref:System.Single.MaxValue?displayProperty=nameWithType>, and they return <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> for values that are less than <xref:System.Single.MinValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="74f21-109">Este cambio se ha realizado para mejorar el cumplimiento de la norma IEEE 754:2008.</span><span class="sxs-lookup"><span data-stu-id="74f21-109">This change was made for improved IEEE 754:2008 compliance.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="74f21-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="74f21-110">Version introduced</span></span>

<span data-ttu-id="74f21-111">3.0</span><span class="sxs-lookup"><span data-stu-id="74f21-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="74f21-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="74f21-112">Recommended action</span></span>

<span data-ttu-id="74f21-113">Este cambio puede afectar al código de alguna de estas dos formas:</span><span class="sxs-lookup"><span data-stu-id="74f21-113">This change can affect your code in either of two ways:</span></span>

- <span data-ttu-id="74f21-114">El código depende del controlador para que <xref:System.OverflowException> se ejecute cuando se produce un desbordamiento.</span><span class="sxs-lookup"><span data-stu-id="74f21-114">Your code depends on the handler for the <xref:System.OverflowException> to execute when an overflow occurs.</span></span> <span data-ttu-id="74f21-115">En este caso, debe quitar la instrucción `catch` y colocar cualquier código necesario en una instrucción `If` que compruebe si <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> o <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> es `true`.</span><span class="sxs-lookup"><span data-stu-id="74f21-115">In this case, you should remove the `catch` statement and place any necessary code in an `If` statement that tests whether <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> or <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> is `true`.</span></span>

- <span data-ttu-id="74f21-116">El código presupone que los valores de punto flotante no son `Infinity`.</span><span class="sxs-lookup"><span data-stu-id="74f21-116">Your code assumes that floating-point values are not `Infinity`.</span></span> <span data-ttu-id="74f21-117">En este caso, debe agregar el código necesario para comprobar los valores de punto flotante de `PositiveInfinity` y `NegativeInfinity`.</span><span class="sxs-lookup"><span data-stu-id="74f21-117">In this case, you should add the necessary code to check for floating-point values of `PositiveInfinity` and `NegativeInfinity`.</span></span>

#### <a name="category"></a><span data-ttu-id="74f21-118">Categoría</span><span class="sxs-lookup"><span data-stu-id="74f21-118">Category</span></span>

<span data-ttu-id="74f21-119">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="74f21-119">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="74f21-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="74f21-120">Affected APIs</span></span>

- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
