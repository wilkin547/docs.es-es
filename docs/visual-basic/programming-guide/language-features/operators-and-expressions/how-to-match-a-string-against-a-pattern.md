---
title: "Cómo: Comprobar si una cadena coincide con un modelo (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 83433bdb41df0ce40d0979f3f44603f10ba1c7d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-match-a-string-against-a-pattern-visual-basic"></a><span data-ttu-id="c43fa-102">Cómo: Comprobar si una cadena coincide con un modelo (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c43fa-102">How to: Match a String against a Pattern (Visual Basic)</span></span>
<span data-ttu-id="c43fa-103">Si desea averiguar si una expresión de la [tipo de datos String](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisface un patrón, puede usar el [operador Like](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c43fa-103">If you want to find out if an expression of the [String Data Type](../../../../visual-basic/language-reference/data-types/string-data-type.md) satisfies a pattern, then you can use the [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
 <span data-ttu-id="c43fa-104">`Like`se aplica a dos operandos.</span><span class="sxs-lookup"><span data-stu-id="c43fa-104">`Like` takes two operands.</span></span> <span data-ttu-id="c43fa-105">El operando izquierdo es una expresión de cadena y el operando derecho es una cadena que contiene el patrón que se usará para la coincidencia.</span><span class="sxs-lookup"><span data-stu-id="c43fa-105">The left operand is a string expression, and the right operand is a string containing the pattern to be used for matching.</span></span> <span data-ttu-id="c43fa-106">`Like`Devuelve un `Boolean` valor que indica si la expresión de cadena ajusta al modelo.</span><span class="sxs-lookup"><span data-stu-id="c43fa-106">`Like` returns a `Boolean` value indicating whether the string expression satisfies the pattern.</span></span>  
  
 <span data-ttu-id="c43fa-107">Puede hacer coincidir cada carácter de la expresión de cadena con un carácter concreto, un carácter comodín, una lista de caracteres o un intervalo de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c43fa-107">You can match each character in the string expression against a specific character, a wildcard character, a character list, or a character range.</span></span> <span data-ttu-id="c43fa-108">Las posiciones de las especificaciones de la cadena patrón corresponden a las posiciones de los caracteres que se debe coincidir en la expresión de cadena.</span><span class="sxs-lookup"><span data-stu-id="c43fa-108">The positions of the specifications in the pattern string correspond to the positions of the characters to be matched in the string expression.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-specific-character"></a><span data-ttu-id="c43fa-109">Para hacer coincidir un carácter en la expresión de cadena con un carácter específico</span><span class="sxs-lookup"><span data-stu-id="c43fa-109">To match a character in the string expression against a specific character</span></span>  
  
-   <span data-ttu-id="c43fa-110">Coloque el carácter concreto en la cadena de patrón directamente.</span><span class="sxs-lookup"><span data-stu-id="c43fa-110">Put the specific character directly in the pattern string.</span></span> <span data-ttu-id="c43fa-111">Algunos caracteres especiales deben incluirse entre corchetes (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="c43fa-111">Certain special characters must be enclosed in brackets (`[ ]`).</span></span> <span data-ttu-id="c43fa-112">Para obtener más información, consulte [operador Like](../../../../visual-basic/language-reference/operators/like-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c43fa-112">For more information, see [Like Operator](../../../../visual-basic/language-reference/operators/like-operator.md).</span></span>  
  
     <span data-ttu-id="c43fa-113">El ejemplo siguiente se comprueba si `myString` exactamente está formada por el carácter único `H`.</span><span class="sxs-lookup"><span data-stu-id="c43fa-113">The following example tests whether `myString` consists exactly of the single character `H`.</span></span>  
  
     [!code-vb[VbVbalrOperators#70](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_1.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-wildcard-character"></a><span data-ttu-id="c43fa-114">Para hacer coincidir un carácter en la expresión de cadena con un carácter comodín</span><span class="sxs-lookup"><span data-stu-id="c43fa-114">To match a character in the string expression against a wildcard character</span></span>  
  
-   <span data-ttu-id="c43fa-115">Coloque un signo de interrogación (`?`) en la cadena de patrón.</span><span class="sxs-lookup"><span data-stu-id="c43fa-115">Put a question mark (`?`) in the pattern string.</span></span> <span data-ttu-id="c43fa-116">Cualquier carácter válido en esta posición Obtiene una coincidencia correcta.</span><span class="sxs-lookup"><span data-stu-id="c43fa-116">Any valid character in this position makes a successful match.</span></span>  
  
     <span data-ttu-id="c43fa-117">El ejemplo siguiente se comprueba si `myString` está formada por el carácter único `W` seguido exactamente dos caracteres de los valores.</span><span class="sxs-lookup"><span data-stu-id="c43fa-117">The following example tests whether `myString` consists of the single character `W` followed by exactly two characters of any values.</span></span>  
  
     [!code-vb[VbVbalrOperators#71](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_2.vb)]  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters"></a><span data-ttu-id="c43fa-118">Para hacer coincidir un carácter en la expresión de cadena con una lista de caracteres</span><span class="sxs-lookup"><span data-stu-id="c43fa-118">To match a character in the string expression against a list of characters</span></span>  
  
-   <span data-ttu-id="c43fa-119">Coloque corchetes (`[ ]`) en la cadena del modelo y, dentro de los corchetes que coloque la lista de caracteres.</span><span class="sxs-lookup"><span data-stu-id="c43fa-119">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the list of characters.</span></span> <span data-ttu-id="c43fa-120">No separe los caracteres con comas o cualquier otro tipo de separador.</span><span class="sxs-lookup"><span data-stu-id="c43fa-120">Do not separate the characters with commas or any other separator.</span></span> <span data-ttu-id="c43fa-121">Cualquier carácter individual en la lista, realiza una coincidencia correcta.</span><span class="sxs-lookup"><span data-stu-id="c43fa-121">Any single character in the list makes a successful match.</span></span>  
  
     <span data-ttu-id="c43fa-122">El ejemplo siguiente se comprueba si `myString` está formada por cualquier carácter válido seguido por exactamente uno de los caracteres `A`, `C`, o `E`.</span><span class="sxs-lookup"><span data-stu-id="c43fa-122">The following example tests whether `myString` consists of any valid character followed by exactly one of the characters `A`, `C`, or `E`.</span></span>  
  
     [!code-vb[VbVbalrOperators#72](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_3.vb)]  
  
     <span data-ttu-id="c43fa-123">Tenga en cuenta que esta coincidencia distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c43fa-123">Note that this match is case-sensitive.</span></span>  
  
### <a name="to-match-a-character-in-the-string-expression-against-a-range-of-characters"></a><span data-ttu-id="c43fa-124">Para hacer coincidir un carácter en la expresión de cadena con un intervalo de caracteres</span><span class="sxs-lookup"><span data-stu-id="c43fa-124">To match a character in the string expression against a range of characters</span></span>  
  
-   <span data-ttu-id="c43fa-125">Coloque corchetes (`[ ]`) en la cadena de patrón y dentro de los corchetes que colocar los caracteres mínimo y máximo del intervalo, separados por un guión (`–`).</span><span class="sxs-lookup"><span data-stu-id="c43fa-125">Put brackets (`[ ]`) in the pattern string, and inside the brackets put the lowest and highest characters in the range, separated by a hyphen (`–`).</span></span> <span data-ttu-id="c43fa-126">Cualquier carácter individual dentro del intervalo, realiza una coincidencia correcta.</span><span class="sxs-lookup"><span data-stu-id="c43fa-126">Any single character within the range makes a successful match.</span></span>  
  
     <span data-ttu-id="c43fa-127">El ejemplo siguiente se comprueba si `myString` consta de los caracteres `num` seguido exactamente uno de los caracteres `i`, `j`, `k`, `l`, `m`, o `n`.</span><span class="sxs-lookup"><span data-stu-id="c43fa-127">The following example tests whether `myString` consists of the characters `num` followed by exactly one of the characters `i`, `j`, `k`, `l`, `m`, or `n`.</span></span>  
  
     [!code-vb[VbVbalrOperators#73](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_4.vb)]  
  
     <span data-ttu-id="c43fa-128">Tenga en cuenta que esta coincidencia distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c43fa-128">Note that this match is case-sensitive.</span></span>  
  
## <a name="matching-empty-strings"></a><span data-ttu-id="c43fa-129">Coincidencia de cadenas vacías</span><span class="sxs-lookup"><span data-stu-id="c43fa-129">Matching Empty Strings</span></span>  
 <span data-ttu-id="c43fa-130">`Like`trata la secuencia `[]` como una cadena de longitud cero (`""`).</span><span class="sxs-lookup"><span data-stu-id="c43fa-130">`Like` treats the sequence `[]` as a zero-length string (`""`).</span></span> <span data-ttu-id="c43fa-131">Puede usar `[]` para comprobar si la expresión de cadena completa está vacía, pero no puede utilizarlo para probar si una posición concreta en la expresión de cadena está vacía.</span><span class="sxs-lookup"><span data-stu-id="c43fa-131">You can use `[]` to test whether the entire string expression is empty, but you cannot use it to test if a particular position in the string expression is empty.</span></span> <span data-ttu-id="c43fa-132">Si una posición vacía es una de las opciones deberá comprobar, puede usar `Like` más de una vez.</span><span class="sxs-lookup"><span data-stu-id="c43fa-132">If an empty position is one of the options you need to test for, you can use `Like` more than once.</span></span>  
  
#### <a name="to-match-a-character-in-the-string-expression-against-a-list-of-characters-or-no-character"></a><span data-ttu-id="c43fa-133">Para hacer coincidir un carácter en la expresión de cadena con una lista de caracteres o ningún carácter</span><span class="sxs-lookup"><span data-stu-id="c43fa-133">To match a character in the string expression against a list of characters or no character</span></span>  
  
1.  <span data-ttu-id="c43fa-134">Llame a la `Like` operador dos veces en la misma expresión de cadena y conecte las dos llamadas con cualquiera el [operador o](../../../../visual-basic/language-reference/operators/or-operator.md) o [OrElse (operador)](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c43fa-134">Call the `Like` operator twice on the same string expression, and connect the two calls with either the [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md) or the [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md).</span></span>  
  
2.  <span data-ttu-id="c43fa-135">En la cadena de patrón para la primera `Like` cláusula, incluyen la lista de caracteres entre corchetes (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="c43fa-135">In the pattern string for the first `Like` clause, include the character list, enclosed in brackets (`[ ]`).</span></span>  
  
3.  <span data-ttu-id="c43fa-136">En la cadena de patrón para el segundo `Like` cláusula, no coloque ningún carácter en la posición en cuestión.</span><span class="sxs-lookup"><span data-stu-id="c43fa-136">In the pattern string for the second `Like` clause, do not put any character at the position in question.</span></span>  
  
     <span data-ttu-id="c43fa-137">En el ejemplo siguiente se comprueba el número de teléfono de siete dígitos `phoneNum` exactamente tres dígitos numéricos, seguido por un espacio, un guión (`–`), un período (`.`), o ningún carácter, seguidos por exactamente cuatro dígitos numéricos.</span><span class="sxs-lookup"><span data-stu-id="c43fa-137">The following example tests the seven-digit telephone number `phoneNum` for exactly three numeric digits, followed by a space, a hyphen (`–`), a period (`.`), or no character at all, followed by exactly four numeric digits.</span></span>  
  
     [!code-vb[VbVbalrOperators#74](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-match-a-string-against-a-pattern_5.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c43fa-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="c43fa-138">See Also</span></span>  
 [<span data-ttu-id="c43fa-139">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="c43fa-139">Comparison Operators</span></span>](../../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [<span data-ttu-id="c43fa-140">Operadores y expresiones</span><span class="sxs-lookup"><span data-stu-id="c43fa-140">Operators and Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="c43fa-141">Like (operador)</span><span class="sxs-lookup"><span data-stu-id="c43fa-141">Like Operator</span></span>](../../../../visual-basic/language-reference/operators/like-operator.md)  
 [<span data-ttu-id="c43fa-142">String (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="c43fa-142">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)
