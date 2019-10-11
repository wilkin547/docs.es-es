---
title: Procedimiento Buscar coincidencias con una cadena en un patrón (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- pattern matching
- strings [Visual Basic], comparing
- string comparison [Visual Basic], operators
- Visual Basic code, operators
- pattern matching [Visual Basic], string comparison
- string comparison [Visual Basic]
- Like operator [Visual Basic], pattern matching
- pattern matching, empty strings
- operators [Visual Basic], comparison
ms.assetid: 19a83804-b5af-4739-928b-ac93e64e457f
ms.openlocfilehash: 0bac0869d9e319071abb31dd0576edf0450aa198
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054151"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="65275-102">Procedimiento Buscar coincidencias con una cadena en un patrón (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65275-102">How to: Match a String against a Pattern (Visual Basic)</span></span>

<span data-ttu-id="65275-103">Si desea averiguar si una expresión del tipo de datos de [cadena](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisface un modelo, puede usar el [operador like](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="65275-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="65275-104">`Like`toma dos operandos.</span><span class="sxs-lookup"><span data-stu-id="65275-104">`Like` takes two operands.</span></span> <span data-ttu-id="65275-105">El operando izquierdo es una expresión de cadena y el operando derecho es una cadena que contiene el patrón que se va a usar para la búsqueda de coincidencias.</span><span class="sxs-lookup"><span data-stu-id="65275-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="65275-106">`Like`Devuelve un `Boolean` valor que indica si la expresión de cadena satisface el modelo.</span><span class="sxs-lookup"><span data-stu-id="65275-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>

<span data-ttu-id="65275-107">Puede hacer coincidir cada carácter de la expresión de cadena con un carácter específico, un carácter comodín, una lista de caracteres o un intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="65275-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="65275-108">Las posiciones de las especificaciones en la cadena de patrón corresponden a las posiciones de los caracteres que se van a buscar en la expresión de cadena.</span><span class="sxs-lookup"><span data-stu-id="65275-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="65275-109">Para hacer coincidir un carácter de la expresión de cadena con un carácter concreto</span><span class="sxs-lookup"><span data-stu-id="65275-109">To match a character in the string expression against a specific character</span></span>

<span data-ttu-id="65275-110">Coloque el carácter específico directamente en la cadena de patrón.</span><span class="sxs-lookup"><span data-stu-id="65275-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="65275-111">Algunos caracteres especiales deben ir entre corchetes (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="65275-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="65275-112">Para obtener más información, vea [operador like](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="65275-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="65275-113">En el ejemplo siguiente se `myString` comprueba si consta exactamente del carácter `H`único.</span><span class="sxs-lookup"><span data-stu-id="65275-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="65275-114">Para hacer coincidir un carácter de la expresión de cadena con un carácter comodín</span><span class="sxs-lookup"><span data-stu-id="65275-114">To match a character in the string expression against a wildcard character</span></span>

<span data-ttu-id="65275-115">Coloque un signo de interrogación (`?`) en la cadena de patrón.</span><span class="sxs-lookup"><span data-stu-id="65275-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="65275-116">Cualquier carácter válido en esta posición realiza una coincidencia correcta.</span><span class="sxs-lookup"><span data-stu-id="65275-116">Any valid character in this position makes a successful match.</span></span>

<span data-ttu-id="65275-117">En el ejemplo siguiente se `myString` comprueba si consta del carácter `W` individual seguido de exactamente dos caracteres de cualquier valor.</span><span class="sxs-lookup"><span data-stu-id="65275-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="65275-118">Para hacer coincidir un carácter de la expresión de cadena con una lista de caracteres</span><span class="sxs-lookup"><span data-stu-id="65275-118">To match a character in the string expression against a list of characters</span></span>

<span data-ttu-id="65275-119">Escriba corchetes`[ ]`() en la cadena de patrón y, dentro de los corchetes, coloque la lista de caracteres.</span><span class="sxs-lookup"><span data-stu-id="65275-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="65275-120">No separe los caracteres con comas ni con ningún otro separador.</span><span class="sxs-lookup"><span data-stu-id="65275-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="65275-121">Cualquier carácter individual de la lista realiza una coincidencia correcta.</span><span class="sxs-lookup"><span data-stu-id="65275-121">Any single character in the list makes a successful match.</span></span>

<span data-ttu-id="65275-122">En el ejemplo siguiente se `myString` comprueba si consta de cualquier carácter válido seguido de exactamente uno de `A`los `C`caracteres, `E`o.</span><span class="sxs-lookup"><span data-stu-id="65275-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

<span data-ttu-id="65275-123">Tenga en cuenta que esta coincidencia distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="65275-123">Note that this match is case-sensitive.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="65275-124">Para hacer coincidir un carácter de la expresión de cadena con un intervalo de caracteres</span><span class="sxs-lookup"><span data-stu-id="65275-124">To match a character in the string expression against a range of characters</span></span>

<span data-ttu-id="65275-125">Escriba corchetes`[ ]`() en la cadena de patrón y, dentro de los corchetes, coloque los caracteres más bajos y más altos en el`–`intervalo, separados por un guión ().</span><span class="sxs-lookup"><span data-stu-id="65275-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="65275-126">Cualquier carácter individual del intervalo realiza una coincidencia correcta.</span><span class="sxs-lookup"><span data-stu-id="65275-126">Any single character within the range makes a successful match.</span></span>

<span data-ttu-id="65275-127">En el ejemplo siguiente se `myString` comprueba si consta de `num` los caracteres seguidos de exactamente uno `i`de `l`los `k`caracteres, `m` `j`,, `n`, o.</span><span class="sxs-lookup"><span data-stu-id="65275-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

<span data-ttu-id="65275-128">Tenga en cuenta que esta coincidencia distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="65275-128">Note that this match is case-sensitive.</span></span>

## <a name="matching-empty-strings"></a><span data-ttu-id="65275-129">Coincidencia de cadenas vacías</span><span class="sxs-lookup"><span data-stu-id="65275-129">Matching Empty Strings</span></span>

<span data-ttu-id="65275-130">`Like`trata la secuencia `[]` como una cadena de longitud cero (`""`).</span><span class="sxs-lookup"><span data-stu-id="65275-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="65275-131">Puede usar `[]` para comprobar si la expresión de cadena completa está vacía, pero no puede utilizarla para probar si una posición determinada en la expresión de cadena está vacía.</span><span class="sxs-lookup"><span data-stu-id="65275-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="65275-132">Si una posición vacía es una de las opciones que necesita probar, puede usar `Like` más de una vez.</span><span class="sxs-lookup"><span data-stu-id="65275-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="65275-133">Para hacer coincidir un carácter de la expresión de cadena con una lista de caracteres o sin carácter</span><span class="sxs-lookup"><span data-stu-id="65275-133">To match a character in the string expression against a list of characters or no character</span></span>

1. <span data-ttu-id="65275-134">Llame al operador `Like` dos veces en la misma expresión de cadena y conecte las dos llamadas con el operador [Or](../../../../visual-basic/language-reference/operators/or-operator.md) o[OrElse](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="65275-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>

2. <span data-ttu-id="65275-135">En la cadena de patrón de la `Like` primera cláusula, incluya la lista de caracteres entre corchetes`[ ]`().</span><span class="sxs-lookup"><span data-stu-id="65275-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>

3. <span data-ttu-id="65275-136">En la cadena de patrón de la `Like` segunda cláusula, no coloque ningún carácter en la posición en cuestión.</span><span class="sxs-lookup"><span data-stu-id="65275-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>

    <span data-ttu-id="65275-137">En el ejemplo siguiente se prueba el número `phoneNum` de teléfono de siete dígitos para exactamente tres dígitos, seguidos de un espacio, un guión (`–`),`.`un punto () o ningún carácter, seguido de exactamente cuatro dígitos numéricos.</span><span class="sxs-lookup"><span data-stu-id="65275-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a><span data-ttu-id="65275-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="65275-138">See also</span></span>

- [<span data-ttu-id="65275-139">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="65275-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="65275-140">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="65275-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="65275-141">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="65275-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="65275-142">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="65275-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
