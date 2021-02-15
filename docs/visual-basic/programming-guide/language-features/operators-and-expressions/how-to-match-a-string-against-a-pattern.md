---
description: 'Más información sobre: Cómo: buscar coincidencias de una cadena con un patrón (Visual Basic)'
title: Procedimiento para comprobar si una cadena coincide con un patrón
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
ms.openlocfilehash: f3e3426f85d420726571f03c88546d181cdccf97
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100461949"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="a348a-103">Cómo: Comprobar si una cadena coincide con un modelo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a348a-103">How to: Match a String against a Pattern (Visual Basic)</span></span>

<span data-ttu-id="a348a-104">Si desea averiguar si una expresión del tipo de datos de [cadena](../../../language-reference/data-types/string-data-type.md) satisface un modelo, puede usar el [operador like](../../../language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a348a-104">If you want to find out if an expression of the [String Data Type](../../../language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="a348a-105">`Like` toma dos operandos.</span><span class="sxs-lookup"><span data-stu-id="a348a-105">`Like` takes two operands.</span></span> <span data-ttu-id="a348a-106">El operando izquierdo es una expresión de cadena y el operando derecho es una cadena que contiene el patrón que se va a usar para la búsqueda de coincidencias.</span><span class="sxs-lookup"><span data-stu-id="a348a-106">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="a348a-107">`Like` Devuelve un `Boolean` valor que indica si la expresión de cadena satisface el modelo.</span><span class="sxs-lookup"><span data-stu-id="a348a-107">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>

<span data-ttu-id="a348a-108">Puede hacer coincidir cada carácter de la expresión de cadena con un carácter específico, un carácter comodín, una lista de caracteres o un intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a348a-108">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="a348a-109">Las posiciones de las especificaciones en la cadena de patrón corresponden a las posiciones de los caracteres que se van a buscar en la expresión de cadena.</span><span class="sxs-lookup"><span data-stu-id="a348a-109">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="a348a-110">Para hacer coincidir un carácter de la expresión de cadena con un carácter concreto</span><span class="sxs-lookup"><span data-stu-id="a348a-110">To match a character in the string expression against a specific character</span></span>

<span data-ttu-id="a348a-111">Coloque el carácter específico directamente en la cadena de patrón.</span><span class="sxs-lookup"><span data-stu-id="a348a-111">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="a348a-112">Algunos caracteres especiales deben ir entre corchetes ( `[ ]` ).</span><span class="sxs-lookup"><span data-stu-id="a348a-112">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="a348a-113">Para obtener más información, vea [operador like](../../../language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a348a-113">For more information, see [Like Operator](../../../language-reference/operators/like-operator.md).</span></span>

<span data-ttu-id="a348a-114">En el ejemplo siguiente se comprueba si `myString` consta exactamente del carácter único `H` .</span><span class="sxs-lookup"><span data-stu-id="a348a-114">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>

[!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]

## <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="a348a-115">Para hacer coincidir un carácter de la expresión de cadena con un carácter comodín</span><span class="sxs-lookup"><span data-stu-id="a348a-115">To match a character in the string expression against a wildcard character</span></span>

<span data-ttu-id="a348a-116">Coloque un signo de interrogación ( `?` ) en la cadena de patrón.</span><span class="sxs-lookup"><span data-stu-id="a348a-116">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="a348a-117">Cualquier carácter válido en esta posición realiza una coincidencia correcta.</span><span class="sxs-lookup"><span data-stu-id="a348a-117">Any valid character in this position makes a successful match.</span></span>

<span data-ttu-id="a348a-118">En el ejemplo siguiente se comprueba si `myString` consta del carácter individual `W` seguido de exactamente dos caracteres de cualquier valor.</span><span class="sxs-lookup"><span data-stu-id="a348a-118">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>

[!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]

## <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="a348a-119">Para hacer coincidir un carácter de la expresión de cadena con una lista de caracteres</span><span class="sxs-lookup"><span data-stu-id="a348a-119">To match a character in the string expression against a list of characters</span></span>

<span data-ttu-id="a348a-120">Escriba corchetes ( `[ ]` ) en la cadena de patrón y, dentro de los corchetes, coloque la lista de caracteres.</span><span class="sxs-lookup"><span data-stu-id="a348a-120">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="a348a-121">No separe los caracteres con comas ni con ningún otro separador.</span><span class="sxs-lookup"><span data-stu-id="a348a-121">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="a348a-122">Cualquier carácter individual de la lista realiza una coincidencia correcta.</span><span class="sxs-lookup"><span data-stu-id="a348a-122">Any single character in the list makes a successful match.</span></span>

<span data-ttu-id="a348a-123">En el ejemplo siguiente se comprueba si `myString` consta de cualquier carácter válido seguido de exactamente uno de los caracteres `A` , `C` o `E` .</span><span class="sxs-lookup"><span data-stu-id="a348a-123">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>

[!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]

<span data-ttu-id="a348a-124">Tenga en cuenta que esta coincidencia distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a348a-124">Note that this match is case-sensitive.</span></span>

## <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="a348a-125">Para hacer coincidir un carácter de la expresión de cadena con un intervalo de caracteres</span><span class="sxs-lookup"><span data-stu-id="a348a-125">To match a character in the string expression against a range of characters</span></span>

<span data-ttu-id="a348a-126">Escriba corchetes ( `[ ]` ) en la cadena de patrón y, dentro de los corchetes, coloque los caracteres más bajos y más altos en el intervalo, separados por un guión ( `–` ).</span><span class="sxs-lookup"><span data-stu-id="a348a-126">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="a348a-127">Cualquier carácter individual del intervalo realiza una coincidencia correcta.</span><span class="sxs-lookup"><span data-stu-id="a348a-127">Any single character within the range makes a successful match.</span></span>

<span data-ttu-id="a348a-128">En el ejemplo siguiente se comprueba si `myString` consta de los caracteres `num` seguidos de exactamente uno de los caracteres `i` , `j` ,, `k` `l` , `m` o `n` .</span><span class="sxs-lookup"><span data-stu-id="a348a-128">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>

[!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]

<span data-ttu-id="a348a-129">Tenga en cuenta que esta coincidencia distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a348a-129">Note that this match is case-sensitive.</span></span>

## <a name="matching-empty-strings"></a><span data-ttu-id="a348a-130">Coincidencia de cadenas vacías</span><span class="sxs-lookup"><span data-stu-id="a348a-130">Matching Empty Strings</span></span>

<span data-ttu-id="a348a-131">`Like` trata la secuencia `[]` como una cadena de longitud cero ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="a348a-131">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="a348a-132">Puede usar `[]` para comprobar si la expresión de cadena completa está vacía, pero no puede utilizarla para probar si una posición determinada en la expresión de cadena está vacía.</span><span class="sxs-lookup"><span data-stu-id="a348a-132">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="a348a-133">Si una posición vacía es una de las opciones que necesita probar, puede usar `Like` más de una vez.</span><span class="sxs-lookup"><span data-stu-id="a348a-133">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>

### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="a348a-134">Para hacer coincidir un carácter de la expresión de cadena con una lista de caracteres o sin carácter</span><span class="sxs-lookup"><span data-stu-id="a348a-134">To match a character in the string expression against a list of characters or no character</span></span>

1. <span data-ttu-id="a348a-135">Llame al `Like` operador dos veces en la misma expresión de cadena y conecte las dos llamadas con el [operador o](../../../language-reference/operators/or-operator.md) o con el [operador OrElse](../../../language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="a348a-135">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../language-reference/operators/or-operator.md) or the [OrElse Operator](../../../language-reference/operators/orelse-operator.md).</span></span>

2. <span data-ttu-id="a348a-136">En la cadena de patrón de la primera `Like` cláusula, incluya la lista de caracteres entre corchetes ( `[ ]` ).</span><span class="sxs-lookup"><span data-stu-id="a348a-136">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>

3. <span data-ttu-id="a348a-137">En la cadena de patrón de la segunda `Like` cláusula, no coloque ningún carácter en la posición en cuestión.</span><span class="sxs-lookup"><span data-stu-id="a348a-137">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>

    <span data-ttu-id="a348a-138">En el ejemplo siguiente se prueba el número de teléfono `phoneNum` de siete dígitos para exactamente tres dígitos, seguidos de un espacio, un guión ( `–` ), un punto ( `.` ) o ningún carácter, seguido de exactamente cuatro dígitos numéricos.</span><span class="sxs-lookup"><span data-stu-id="a348a-138">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>

    [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]

## <a name="see-also"></a><span data-ttu-id="a348a-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a348a-139">See also</span></span>

- [<span data-ttu-id="a348a-140">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="a348a-140">Comparison Operators</span></span>](../../../language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="a348a-141">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="a348a-141">Operators and Expressions</span></span>](index.md)
- [<span data-ttu-id="a348a-142">Like (Operador)</span><span class="sxs-lookup"><span data-stu-id="a348a-142">Like Operator</span></span>](../../../language-reference/operators/like-operator.md)
- [<span data-ttu-id="a348a-143">String (Tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="a348a-143">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)
