---
title: Construcciones de alternancia en expresiones regulares de .NET
description: Obtenga información sobre cómo usar construcciones de alternancia para la coincidencia condicional en expresiones regulares.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- either/or matching
- alternative matching patterns
- regular expressions, alternation constructs
- alternation constructs
- optional matching patterns
- constructs, alternation
- .NET regular expressions, alternation constructs
ms.assetid: 071e22e9-fbb0-4ecf-add1-8d2424f9f2d1
ms.openlocfilehash: 4fb9960ad3c92494cd3aa47516f6ba82ab606ee5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825304"
---
# <a name="alternation-constructs-in-regular-expressions"></a><span data-ttu-id="905d8-103">Construcciones de alternancia en expresiones regulares</span><span class="sxs-lookup"><span data-stu-id="905d8-103">Alternation Constructs in Regular Expressions</span></span>

<span data-ttu-id="905d8-104">Las construcciones de alternancia modifican una expresión regular para habilitar la coincidencia condicional o “either/or”.</span><span class="sxs-lookup"><span data-stu-id="905d8-104">Alternation constructs modify a regular expression to enable either/or or conditional matching.</span></span> <span data-ttu-id="905d8-105">.NET admite tres construcciones de alternancia:</span><span class="sxs-lookup"><span data-stu-id="905d8-105">.NET supports three alternation constructs:</span></span>

- [<span data-ttu-id="905d8-106">Coincidencia de patrones con &#124;</span><span class="sxs-lookup"><span data-stu-id="905d8-106">Pattern matching with &#124;</span></span>](#Either_Or)
- [<span data-ttu-id="905d8-107">Coincidencia condicional con (?(expresión)sí&#124;no)</span><span class="sxs-lookup"><span data-stu-id="905d8-107">Conditional matching with (?(expression)yes&#124;no)</span></span>](#Conditional_Expr)
- [<span data-ttu-id="905d8-108">Coincidencia condicional basada en un grupo capturado válido</span><span class="sxs-lookup"><span data-stu-id="905d8-108">Conditional matching based on a valid captured group</span></span>](#Conditional_Group)

<a name="Either_Or"></a>
## <a name="pattern-matching-with-124"></a><span data-ttu-id="905d8-109">Coincidencia de patrones con &#124;</span><span class="sxs-lookup"><span data-stu-id="905d8-109">Pattern Matching with &#124;</span></span>

<span data-ttu-id="905d8-110">Puede usar el carácter de barra vertical (`|`) para hacer coincidir un elemento de una serie de patrones, donde el carácter `|` separa cada patrón.</span><span class="sxs-lookup"><span data-stu-id="905d8-110">You can use the vertical bar (`|`) character to match any one of a series of patterns, where the `|` character separates each pattern.</span></span>

<span data-ttu-id="905d8-111">Como sucede con la clase de caracteres positivos, el carácter `|` puede utilizarse para hacer coincidir un elemento de una serie de caracteres individuales.</span><span class="sxs-lookup"><span data-stu-id="905d8-111">Like the positive character class, the `|` character can be used to match any one of a number of single characters.</span></span> <span data-ttu-id="905d8-112">En el ejemplo siguiente se utiliza una clase de caracteres positivos y un patrón either/or que coincide con el carácter `|` para buscar apariciones de las palabras "gray" o "grey" en una cadena.</span><span class="sxs-lookup"><span data-stu-id="905d8-112">The following example uses both a positive character class and either/or pattern matching with the `|` character to locate occurrences of the words "gray" or "grey" in a string.</span></span> <span data-ttu-id="905d8-113">En este caso, el carácter `|` produce una expresión regular que es más detallada.</span><span class="sxs-lookup"><span data-stu-id="905d8-113">In this case, the `|` character produces a regular expression that is more verbose.</span></span>

[!code-csharp[RegularExpressions.Language.Alternation#1](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation1.cs#1)]
[!code-vb[RegularExpressions.Language.Alternation#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation1.vb#1)]

<span data-ttu-id="905d8-114">La expresión regular que usa el carácter `|`, `\bgr(a|e)y\b`, se interpreta como se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="905d8-114">The regular expression that uses the `|` character, `\bgr(a|e)y\b`, is interpreted as shown in the following table:</span></span>

|<span data-ttu-id="905d8-115">Modelo</span><span class="sxs-lookup"><span data-stu-id="905d8-115">Pattern</span></span>|<span data-ttu-id="905d8-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="905d8-116">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="905d8-117">Empieza en un límite de palabras.</span><span class="sxs-lookup"><span data-stu-id="905d8-117">Start at a word boundary.</span></span>|  
|`gr`|<span data-ttu-id="905d8-118">Coincide con los caracteres "gr".</span><span class="sxs-lookup"><span data-stu-id="905d8-118">Match the characters "gr".</span></span>|  
|<code>(a&#124;e)</code>|<span data-ttu-id="905d8-119">Coincide con una "a" o una "e".</span><span class="sxs-lookup"><span data-stu-id="905d8-119">Match either an "a" or an "e".</span></span>|  
|`y\b`|<span data-ttu-id="905d8-120">Coincide con una "y" en un límite de palabras.</span><span class="sxs-lookup"><span data-stu-id="905d8-120">Match a "y" on a word boundary.</span></span>|  

<span data-ttu-id="905d8-121">El carácter `|` también se puede usar para realizar una coincidencia either/or con varios caracteres o subexpresiones, que pueden incluir cualquier combinación de literales de carácter y elementos de lenguaje de expresión regular.</span><span class="sxs-lookup"><span data-stu-id="905d8-121">The `|` character can also be used to perform an either/or match with multiple characters or subexpressions, which can include any combination of character literals and regular expression language elements.</span></span> <span data-ttu-id="905d8-122">(La clase de caracteres no proporciona esta funcionalidad). En el ejemplo siguiente, se usa el carácter `|` para extraer un número de la seguridad social (SSN) de EE. UU., de nueve dígitos y en formato *ddd*-*dd*-*dddd*, o un número de identificación de empleador (EIN), de nueve dígitos y en formato *dd*-*ddddddd*.</span><span class="sxs-lookup"><span data-stu-id="905d8-122">(The character class does not provide this functionality.) The following example uses the `|` character to extract either a U.S. Social Security Number (SSN), which is a 9-digit number with the format *ddd*-*dd*-*dddd*, or a U.S. Employer Identification Number (EIN), which is a 9-digit number with the format *dd*-*ddddddd*.</span></span>

[!code-csharp[RegularExpressions.Language.Alternation#2](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation2.cs#2)]
[!code-vb[RegularExpressions.Language.Alternation#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation2.vb#2)]  

<span data-ttu-id="905d8-123">La expresión regular `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` se interpreta como se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="905d8-123">The regular expression `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table:</span></span>
  
|<span data-ttu-id="905d8-124">Modelo</span><span class="sxs-lookup"><span data-stu-id="905d8-124">Pattern</span></span>|<span data-ttu-id="905d8-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="905d8-125">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="905d8-126">Empieza en un límite de palabras.</span><span class="sxs-lookup"><span data-stu-id="905d8-126">Start at a word boundary.</span></span>|  
|<code>(\d{2}-\d{7}&#124;\d{3}-\d{2}-\d{4})</code>|<span data-ttu-id="905d8-127">Coincide con cualquiera de las siguientes opciones: dos dígitos decimales seguidos de un guión seguido de siete dígitos decimales; o tres dígitos decimales, un guión, dos dígitos decimales, otro guión y cuatro dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="905d8-127">Match either of the following: two decimal digits followed by a hyphen followed by seven decimal digits; or three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="905d8-128">Finalizar la búsqueda de coincidencias en un límite de palabras.</span><span class="sxs-lookup"><span data-stu-id="905d8-128">End the match at a word boundary.</span></span>|  
  
<a name="Conditional_Expr"></a>
## <a name="conditional-matching-with-an-expression"></a><span data-ttu-id="905d8-129">Coincidencia condicional con una expresión</span><span class="sxs-lookup"><span data-stu-id="905d8-129">Conditional matching with an expression</span></span>

<span data-ttu-id="905d8-130">Este elemento del lenguaje intenta coincidir con uno de dos patrones en función de si puede coincidir con un patrón inicial.</span><span class="sxs-lookup"><span data-stu-id="905d8-130">This language element attempts to match one of two patterns depending on whether it can match an initial pattern.</span></span> <span data-ttu-id="905d8-131">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="905d8-131">Its syntax is:</span></span>  

<span data-ttu-id="905d8-132">`(?(` *expresión* `)` *sí* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="905d8-132">`(?(` *expression* `)` *yes* `|` *no* `)`</span></span>

<span data-ttu-id="905d8-133">donde *expresión* es el patrón inicial de coincidencia, *sí* es el patrón de coincidencia si se encuentra una coincidencia para *expresión* y *no* es el patrón opcional de coincidencia si no se encuentra ninguna coincidencia para *expresión* .</span><span class="sxs-lookup"><span data-stu-id="905d8-133">where *expression* is the initial pattern to match, *yes* is the pattern to match if *expression* is matched, and *no* is the optional pattern to match if *expression* is not matched.</span></span> <span data-ttu-id="905d8-134">El motor de expresiones regulares trata a la *expresión* como una aserción de ancho cero; es decir, el motor de expresiones regulares no avanza en el flujo de entrada después de evaluar la *expresión*.</span><span class="sxs-lookup"><span data-stu-id="905d8-134">The regular expression engine treats *expression* as a zero-width assertion; that is, the regular expression engine does not advance in the input stream after it evaluates *expression*.</span></span> <span data-ttu-id="905d8-135">Por tanto, esta construcción es equivalente a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="905d8-135">Therefore, this construct is equivalent to the following:</span></span>

<span data-ttu-id="905d8-136">`(?(?=` *expresión* `)` *sí* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="905d8-136">`(?(?=` *expression* `)` *yes* `|` *no* `)`</span></span>

<span data-ttu-id="905d8-137">donde `(?=`*expresión*`)` es una construcción de aserción de ancho cero.</span><span class="sxs-lookup"><span data-stu-id="905d8-137">where `(?=`*expression*`)` is a zero-width assertion construct.</span></span> <span data-ttu-id="905d8-138">Para más información, consulte la sección sobre [Construcciones de agrupamiento en expresiones regulares](grouping-constructs-in-regular-expressions.md). Como el motor de expresiones regulares interpreta la *expresión* como un delimitador (una aserción de ancho cero), la *expresión* debe ser una aserción de ancho cero (para más información, consulte [Delimitadores en expresiones regulares](anchors-in-regular-expressions.md)) o una subexpresión que también esté incluida en *sí*.</span><span class="sxs-lookup"><span data-stu-id="905d8-138">(For more information, see [Grouping Constructs](grouping-constructs-in-regular-expressions.md).) Because the regular expression engine interprets *expression* as an anchor (a zero-width assertion), *expression* must either be a zero-width assertion (for more information, see [Anchors](anchors-in-regular-expressions.md)) or a subexpression that is also contained in *yes*.</span></span> <span data-ttu-id="905d8-139">De lo contrario, no se pueden encontrar coincidencias para el patrón *sí* .</span><span class="sxs-lookup"><span data-stu-id="905d8-139">Otherwise, the *yes* pattern cannot be matched.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="905d8-140">Si *expresión* es un grupo de captura con nombre o con numeración, la construcción de alternancia se interpreta como una prueba de captura; para obtener más información, consulte la sección siguiente, [Coincidencia condicional basada en un grupo capturado válido](#Conditional_Group).</span><span class="sxs-lookup"><span data-stu-id="905d8-140">If *expression* is a named or numbered capturing group, the alternation construct is interpreted as a capture test; for more information, see the next section, [Conditional Matching Based on a Valid Capture Group](#Conditional_Group).</span></span> <span data-ttu-id="905d8-141">En otras palabras, el motor de expresiones regulares no intenta coincidir con la subcadena capturada, sino que, en vez de eso, comprueba la presencia o la ausencia del grupo.</span><span class="sxs-lookup"><span data-stu-id="905d8-141">In other words, the regular expression engine does not attempt to match the captured substring, but instead tests for the presence or absence of the group.</span></span>  
  
<span data-ttu-id="905d8-142">El siguiente ejemplo es una variación del que aparece en la sección [Coincidencia de patrones either/or con &#124;](#Either_Or).</span><span class="sxs-lookup"><span data-stu-id="905d8-142">The following example is a variation of the example that appears in the [Either/Or Pattern Matching with &#124;](#Either_Or) section.</span></span> <span data-ttu-id="905d8-143">En él se usa la coincidencia condicional para determinar si los tres primeros caracteres después de un límite de palabra son dos dígitos seguidos por un guión.</span><span class="sxs-lookup"><span data-stu-id="905d8-143">It uses conditional matching to determine whether the first three characters after a word boundary are two digits followed by a hyphen.</span></span> <span data-ttu-id="905d8-144">Si es así, intenta buscar un número de identificación de empleador (EIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="905d8-144">If they are, it attempts to match a U.S. Employer Identification Number (EIN).</span></span> <span data-ttu-id="905d8-145">Si no, intenta buscar un número de la seguridad social (SSN) de EE.UU.</span><span class="sxs-lookup"><span data-stu-id="905d8-145">If not, it attempts to match a U.S. Social Security Number (SSN).</span></span>

[!code-csharp[RegularExpressions.Language.Alternation#3](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation3.cs#3)]
[!code-vb[RegularExpressions.Language.Alternation#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation3.vb#3)]

<span data-ttu-id="905d8-146">El patrón de la expresión regular `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` se interpreta como se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="905d8-146">The regular expression pattern `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table:</span></span>

|<span data-ttu-id="905d8-147">Modelo</span><span class="sxs-lookup"><span data-stu-id="905d8-147">Pattern</span></span>|<span data-ttu-id="905d8-148">Descripción</span><span class="sxs-lookup"><span data-stu-id="905d8-148">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="905d8-149">Empieza en un límite de palabras.</span><span class="sxs-lookup"><span data-stu-id="905d8-149">Start at a word boundary.</span></span>|  
|`(?(\d{2}-)`|<span data-ttu-id="905d8-150">Determina si los tres caracteres siguientes están compuestos de dos dígitos seguidos de un guión.</span><span class="sxs-lookup"><span data-stu-id="905d8-150">Determine whether the next three characters consist of two digits followed by a hyphen.</span></span>|  
|`\d{2}-\d{7}`|<span data-ttu-id="905d8-151">Si el patrón anterior coincide, coincide con dos dígitos seguidos de un guión seguido de siete dígitos.</span><span class="sxs-lookup"><span data-stu-id="905d8-151">If the previous pattern matches, match two digits followed by a hyphen followed by seven digits.</span></span>|  
|`\d{3}-\d{2}-\d{4}`|<span data-ttu-id="905d8-152">Si el patrón anterior no coincide, coincide con tres dígitos decimales, un guión, dos dígitos decimales, otro guión y cuatro dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="905d8-152">If the previous pattern does not match, match three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="905d8-153">Coincide con un límite de palabras.</span><span class="sxs-lookup"><span data-stu-id="905d8-153">Match a word boundary.</span></span>|  

<a name="Conditional_Group"></a>
## <a name="conditional-matching-based-on-a-valid-captured-group"></a><span data-ttu-id="905d8-154">Coincidencia condicional basada en un grupo capturado válido</span><span class="sxs-lookup"><span data-stu-id="905d8-154">Conditional matching based on a valid captured group</span></span>

<span data-ttu-id="905d8-155">Este elemento del lenguaje intenta coincidir con uno de dos patrones en función de si coincidió con un grupo de captura especificado.</span><span class="sxs-lookup"><span data-stu-id="905d8-155">This language element attempts to match one of two patterns depending on whether it has matched a specified capturing group.</span></span> <span data-ttu-id="905d8-156">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="905d8-156">Its syntax is:</span></span>

<span data-ttu-id="905d8-157">`(?(` *nombre* `)` *sí* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="905d8-157">`(?(` *name* `)` *yes* `|` *no* `)`</span></span>

<span data-ttu-id="905d8-158">o</span><span class="sxs-lookup"><span data-stu-id="905d8-158">or</span></span>

<span data-ttu-id="905d8-159">`(?(` *número* `)` *sí* `|` *no* `)`</span><span class="sxs-lookup"><span data-stu-id="905d8-159">`(?(` *number* `)` *yes* `|` *no* `)`</span></span>

<span data-ttu-id="905d8-160">donde *nombre* es el nombre y *número* es el número de un grupo de captura, *sí* es la expresión que debe coincidir si *nombre* o *número* tienen una coincidencia, y *no* es la expresión opcional que debe coincidir si no la tienen.</span><span class="sxs-lookup"><span data-stu-id="905d8-160">where *name* is the name and *number* is the number of a capturing group, *yes* is the expression to match if *name* or *number* has a match, and *no* is the optional expression to match if it does not.</span></span>

<span data-ttu-id="905d8-161">Si *nombre* no se corresponde con el nombre de un grupo de captura que se usa en el patrón de expresión regular, la construcción de alternancia se interpreta como una prueba de expresión, tal como se explica en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="905d8-161">If *name* does not correspond to the name of a capturing group that is used in the regular expression pattern, the alternation construct is interpreted as an expression test, as explained in the previous section.</span></span> <span data-ttu-id="905d8-162">Normalmente, esto significa que *expresión* se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="905d8-162">Typically, this means that *expression* evaluates to `false`.</span></span> <span data-ttu-id="905d8-163">Si *número* no se corresponde con un grupo de captura numerado que se usa en el patrón de expresión regular, el motor de expresiones regulares genera una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="905d8-163">If *number* does not correspond to a numbered capturing group that is used in the regular expression pattern, the regular expression engine throws an <xref:System.ArgumentException>.</span></span>

<span data-ttu-id="905d8-164">El siguiente ejemplo es una variación del que aparece en la sección [Coincidencia de patrones either/or con &#124;](#Either_Or).</span><span class="sxs-lookup"><span data-stu-id="905d8-164">The following example is a variation of the example that appears in the [Either/Or Pattern Matching with &#124;](#Either_Or) section.</span></span> <span data-ttu-id="905d8-165">En él se usa un grupo de captura denominado `n2` que consta de dos dígitos seguidos por un guión.</span><span class="sxs-lookup"><span data-stu-id="905d8-165">It uses a capturing group named `n2` that consists of two digits followed by a hyphen.</span></span> <span data-ttu-id="905d8-166">La construcción de alternancia prueba si este grupo de captura ha coincidido en la cadena de entrada.</span><span class="sxs-lookup"><span data-stu-id="905d8-166">The alternation construct tests whether this capturing group has been matched in the input string.</span></span> <span data-ttu-id="905d8-167">En caso afirmativo, la construcción de alternancia intenta hacer coincidir los últimos siete dígitos de un número de identificación de empleador de identificación de empleador (EIN) de EE. UU.</span><span class="sxs-lookup"><span data-stu-id="905d8-167">If it has, the alternation construct attempts to match the last seven digits of a nine-digit U.S. Employer Identification Number (EIN).</span></span> <span data-ttu-id="905d8-168">En caso negativo, intenta coincidir con un número de la seguridad social (SSN) de EE.UU.</span><span class="sxs-lookup"><span data-stu-id="905d8-168">If it has not, it attempts to match a nine-digit U.S. Social Security Number (SSN).</span></span>

[!code-csharp[RegularExpressions.Language.Alternation#4](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation4.cs#4)]
[!code-vb[RegularExpressions.Language.Alternation#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation4.vb#4)]

<span data-ttu-id="905d8-169">El patrón de la expresión regular `\b(?<n2>\d{2}-)?(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` se interpreta como se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="905d8-169">The regular expression pattern `\b(?<n2>\d{2}-)?(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` is interpreted as shown in the following table:</span></span>

|<span data-ttu-id="905d8-170">Modelo</span><span class="sxs-lookup"><span data-stu-id="905d8-170">Pattern</span></span>|<span data-ttu-id="905d8-171">Descripción</span><span class="sxs-lookup"><span data-stu-id="905d8-171">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="905d8-172">Empieza en un límite de palabras.</span><span class="sxs-lookup"><span data-stu-id="905d8-172">Start at a word boundary.</span></span>|  
|`(?<n2>\d{2}-)?`|<span data-ttu-id="905d8-173">Coincide con cero o con dos dígitos seguidos por un guión.</span><span class="sxs-lookup"><span data-stu-id="905d8-173">Match zero or one occurrence of two digits followed by a hyphen.</span></span> <span data-ttu-id="905d8-174">Este grupo de captura se denomina `n2`.</span><span class="sxs-lookup"><span data-stu-id="905d8-174">Name this capturing group `n2`.</span></span>|  
|`(?(n2)`|<span data-ttu-id="905d8-175">Prueba si `n2` coincidió con la cadena de entrada.</span><span class="sxs-lookup"><span data-stu-id="905d8-175">Test whether `n2` was matched in the input string.</span></span>|  
|`\d{7}`|<span data-ttu-id="905d8-176">Si `n2` coincidió, coincide con siete dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="905d8-176">If `n2` was matched, match seven decimal digits.</span></span>|  
|<code>&#124;\d{3}-\d{2}-\d{4}</code>|<span data-ttu-id="905d8-177">Si `n2` no coincidió, coincide con tres dígitos decimales, un guión, dos dígitos decimales, otro guión y cuatro dígitos decimales.</span><span class="sxs-lookup"><span data-stu-id="905d8-177">If `n2` was not matched, match three decimal digits, a hyphen, two decimal digits, another hyphen, and four decimal digits.</span></span>|  
|`\b`|<span data-ttu-id="905d8-178">Coincide con un límite de palabras.</span><span class="sxs-lookup"><span data-stu-id="905d8-178">Match a word boundary.</span></span>|  

<span data-ttu-id="905d8-179">En el ejemplo siguiente se muestra una variación de este ejemplo, pero con un grupo numerado en lugar de un grupo con nombre.</span><span class="sxs-lookup"><span data-stu-id="905d8-179">A variation of this example that uses a numbered group instead of a named group is shown in the following example.</span></span> <span data-ttu-id="905d8-180">Su patrón de expresión regular es `\b(\d{2}-)?(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`.</span><span class="sxs-lookup"><span data-stu-id="905d8-180">Its regular expression pattern is `\b(\d{2}-)?(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`.</span></span>

[!code-csharp[RegularExpressions.Language.Alternation#5](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation5.cs#5)]
[!code-vb[RegularExpressions.Language.Alternation#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation5.vb#5)]

## <a name="see-also"></a><span data-ttu-id="905d8-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="905d8-181">See also</span></span>

- [<span data-ttu-id="905d8-182">Lenguaje de expresiones regulares: referencia rápida</span><span class="sxs-lookup"><span data-stu-id="905d8-182">Regular Expression Language - Quick Reference</span></span>](regular-expression-language-quick-reference.md)
