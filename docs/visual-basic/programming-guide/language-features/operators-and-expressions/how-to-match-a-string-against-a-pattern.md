---
title: Filtrar Coincide con una cadena con un patrón (Visual Basic)
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
ms.openlocfilehash: 884c5ddf15deb49719915f10e107ba6a3431c4bc
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965949"
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="14543-102">Filtrar Coincide con una cadena con un patrón (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14543-102">How to: Match a String against a Pattern (Visual Basic)</span></span>
<span data-ttu-id="14543-103">Si desea averiguar si una expresión de la [tipo de datos String](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisface un patrón, puede usar el [Like (operador)](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="14543-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
 <span data-ttu-id="14543-104">`Like` toma dos operandos.</span><span class="sxs-lookup"><span data-stu-id="14543-104">`Like` takes two operands.</span></span> <span data-ttu-id="14543-105">El operando izquierdo es una expresión de cadena y el operando derecho es una cadena que contiene el patrón que se usará para la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="14543-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="14543-106">`Like` Devuelve un `Boolean` valor que indica si la expresión de cadena ajusta al modelo.</span><span class="sxs-lookup"><span data-stu-id="14543-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>  
  
 <span data-ttu-id="14543-107">Puede hacer coincidir cada carácter de la expresión de cadena con un carácter concreto, un carácter comodín, una lista de caracteres o un intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="14543-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="14543-108">Las posiciones de las especificaciones de la cadena patrón corresponden a las posiciones de los caracteres que debe coincidir con la expresión de cadena.</span><span class="sxs-lookup"><span data-stu-id="14543-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="14543-109">Para hacer coincidir un carácter en la expresión de cadena con un carácter específico</span><span class="sxs-lookup"><span data-stu-id="14543-109">To match a character in the string expression against a specific character</span></span>  
  
-   <span data-ttu-id="14543-110">Coloque el carácter concreto en la cadena de patrón directamente.</span><span class="sxs-lookup"><span data-stu-id="14543-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="14543-111">Algunos caracteres especiales deben escribirse entre corchetes (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="14543-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="14543-112">Para obtener más información, consulte [Like (operador)](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="14543-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
     <span data-ttu-id="14543-113">El siguiente ejemplo se comprueba si `myString` consta exactamente de carácter único `H`.</span><span class="sxs-lookup"><span data-stu-id="14543-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>  
  
     [!code-vb[VbVbalrOperators#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#70)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="14543-114">Para hacer coincidir un carácter en la expresión de cadena con un carácter comodín</span><span class="sxs-lookup"><span data-stu-id="14543-114">To match a character in the string expression against a wildcard character</span></span>  
  
-   <span data-ttu-id="14543-115">Ponga un signo de interrogación (`?`) en la cadena de patrón.</span><span class="sxs-lookup"><span data-stu-id="14543-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="14543-116">Cualquier carácter válido en esta posición realiza una coincidencia correcta.</span><span class="sxs-lookup"><span data-stu-id="14543-116">Any valid character in this position makes a successful match.</span></span>  
  
     <span data-ttu-id="14543-117">El siguiente ejemplo se comprueba si `myString` se compone del carácter único `W` seguido de exactamente dos caracteres de los valores.</span><span class="sxs-lookup"><span data-stu-id="14543-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>  
  
     [!code-vb[VbVbalrOperators#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#71)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="14543-118">Para hacer coincidir un carácter en la expresión de cadena con una lista de caracteres</span><span class="sxs-lookup"><span data-stu-id="14543-118">To match a character in the string expression against a list of characters</span></span>  
  
-   <span data-ttu-id="14543-119">Coloque corchetes (`[ ]`) en la cadena de patrón y dentro de los corchetes que ponga la lista de caracteres.</span><span class="sxs-lookup"><span data-stu-id="14543-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="14543-120">No separe los caracteres con comas o cualquier otro separador.</span><span class="sxs-lookup"><span data-stu-id="14543-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="14543-121">Cualquier carácter individual en la lista hace que sea una coincidencia correcta.</span><span class="sxs-lookup"><span data-stu-id="14543-121">Any single character in the list makes a successful match.</span></span>  
  
     <span data-ttu-id="14543-122">El siguiente ejemplo se comprueba si `myString` consta de cualquier carácter válido seguido exactamente uno de los caracteres `A`, `C`, o `E`.</span><span class="sxs-lookup"><span data-stu-id="14543-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>  
  
     [!code-vb[VbVbalrOperators#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#72)]  
  
     <span data-ttu-id="14543-123">Tenga en cuenta que esta coincidencia distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="14543-123">Note that this match is case-sensitive.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="14543-124">Para hacer coincidir un carácter en la expresión de cadena con un intervalo de caracteres</span><span class="sxs-lookup"><span data-stu-id="14543-124">To match a character in the string expression against a range of characters</span></span>  
  
-   <span data-ttu-id="14543-125">Coloque corchetes (`[ ]`) en la cadena de patrón y dentro de los corchetes que colocar los caracteres mínimo y máximo del intervalo, separados por un guión (`–`).</span><span class="sxs-lookup"><span data-stu-id="14543-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="14543-126">Cualquier carácter individual dentro del intervalo, realiza una coincidencia correcta.</span><span class="sxs-lookup"><span data-stu-id="14543-126">Any single character within the range makes a successful match.</span></span>  
  
     <span data-ttu-id="14543-127">El siguiente ejemplo se comprueba si `myString` consta de los caracteres `num` seguido exactamente uno de los caracteres `i`, `j`, `k`, `l`, `m`, o `n`.</span><span class="sxs-lookup"><span data-stu-id="14543-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>  
  
     [!code-vb[VbVbalrOperators#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#73)]  
  
     <span data-ttu-id="14543-128">Tenga en cuenta que esta coincidencia distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="14543-128">Note that this match is case-sensitive.</span></span>  
  
## <a name="matching-empty-strings"></a><span data-ttu-id="14543-129">Coincidencia de cadenas vacías</span><span class="sxs-lookup"><span data-stu-id="14543-129">Matching Empty Strings</span></span>  
 <span data-ttu-id="14543-130">`Like` trata la secuencia `[]` como una cadena de longitud cero (`""`).</span><span class="sxs-lookup"><span data-stu-id="14543-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="14543-131">Puede usar `[]` para comprobar si toda la expresión está vacía, pero no puede usar para probar si una posición concreta en la expresión de cadena está vacía.</span><span class="sxs-lookup"><span data-stu-id="14543-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="14543-132">Si una posición vacía es una de las opciones necesita va a comprobar, puede usar `Like` más de una vez.</span><span class="sxs-lookup"><span data-stu-id="14543-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="14543-133">Para hacer coincidir un carácter en la expresión de cadena con una lista de caracteres o ningún carácter</span><span class="sxs-lookup"><span data-stu-id="14543-133">To match a character in the string expression against a list of characters or no character</span></span>  
  
1.  <span data-ttu-id="14543-134">Llame a la `Like` operador dos veces en la misma expresión de cadena y conecte las dos llamadas con cualquiera el [operador o](../../../../visual-basic/language-reference/operators/or-operator.md) o [OrElse (operador)](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="14543-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
2.  <span data-ttu-id="14543-135">En la cadena de patrón para la primera `Like` cláusula, incluir la lista de caracteres entre corchetes (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="14543-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>  
  
3.  <span data-ttu-id="14543-136">En la cadena de patrón para el segundo `Like` cláusula, no coloque cualquier carácter en la posición en cuestión.</span><span class="sxs-lookup"><span data-stu-id="14543-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>  
  
     <span data-ttu-id="14543-137">El ejemplo siguiente comprueba el número de teléfono de siete dígitos `phoneNum` exactamente tres dígitos numéricos, seguida por un espacio, un guión (`–`), un período (`.`), o ningún carácter en absoluto, seguidos exactamente cuatro dígitos numéricos.</span><span class="sxs-lookup"><span data-stu-id="14543-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>  
  
     [!code-vb[VbVbalrOperators#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="14543-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="14543-138">See also</span></span>
- [<span data-ttu-id="14543-139">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="14543-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)
- [<span data-ttu-id="14543-140">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="14543-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="14543-141">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="14543-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="14543-142">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="14543-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
