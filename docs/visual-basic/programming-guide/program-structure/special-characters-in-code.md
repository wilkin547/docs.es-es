---
title: "Caracteres especiales en código (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 11c5ef9ad41fc2362d9ba4f2cb5eb5b63a9ca31c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="cc93c-102">Caracteres especiales en código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc93c-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="cc93c-103">En ocasiones tendrá que usar caracteres especiales en el código, es decir, caracteres que no sean alfabéticos o numéricos.</span><span class="sxs-lookup"><span data-stu-id="cc93c-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="cc93c-104">Los signos de puntuación y caracteres especiales en el [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] juego de caracteres tienen varias finalidades, desde organizar el texto del programa hasta definir las tareas que realiza el compilador o el programa compilado.</span><span class="sxs-lookup"><span data-stu-id="cc93c-104">The punctuation and special characters in the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="cc93c-105">No especifican que se deba realizar una operación.</span><span class="sxs-lookup"><span data-stu-id="cc93c-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="cc93c-106">Paréntesis</span><span class="sxs-lookup"><span data-stu-id="cc93c-106">Parentheses</span></span>  
 <span data-ttu-id="cc93c-107">Utilice paréntesis al definir un procedimiento, como un `Sub` o `Function`.</span><span class="sxs-lookup"><span data-stu-id="cc93c-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="cc93c-108">Todas las listas de argumentos de procedimiento deben incluir entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="cc93c-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="cc93c-109">También se utilizan paréntesis para agrupar variables o argumentos en grupos lógicos, especialmente para invalidar el orden predeterminado de prioridad de operador en una expresión compleja.</span><span class="sxs-lookup"><span data-stu-id="cc93c-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="cc93c-110">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cc93c-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 <span data-ttu-id="cc93c-111">Tras la ejecución del código anterior, el valor de `d` es 8,225 y el valor de `e` es 3.</span><span class="sxs-lookup"><span data-stu-id="cc93c-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="cc93c-112">El cálculo de `d` utiliza la prioridad predeterminada de `/` sobre `+` y es equivalente a `d = b + (c / a)`.</span><span class="sxs-lookup"><span data-stu-id="cc93c-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="cc93c-113">Los paréntesis en el cálculo de `e` alto la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cc93c-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="cc93c-114">Separadores</span><span class="sxs-lookup"><span data-stu-id="cc93c-114">Separators</span></span>  
 <span data-ttu-id="cc93c-115">Los separadores hacen lo que sugiere su nombre: separan dos secciones de código.</span><span class="sxs-lookup"><span data-stu-id="cc93c-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="cc93c-116">En [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], el carácter separador es el signo de dos puntos (`:`).</span><span class="sxs-lookup"><span data-stu-id="cc93c-116">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], the separator character is the colon (`:`).</span></span> <span data-ttu-id="cc93c-117">Utilice separadores cuando van a incluir varias instrucciones en una sola línea en lugar de líneas separadas.</span><span class="sxs-lookup"><span data-stu-id="cc93c-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="cc93c-118">Esto ahorra espacio y mejora la legibilidad del código.</span><span class="sxs-lookup"><span data-stu-id="cc93c-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="cc93c-119">En el siguiente ejemplo muestra tres instrucciones separadas por signos de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="cc93c-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 <span data-ttu-id="cc93c-120">Para obtener más información, consulte [Cómo: salto y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="cc93c-120">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="cc93c-121">Los dos puntos (`:`) caracteres también se usan para identificar una etiqueta de instrucción.</span><span class="sxs-lookup"><span data-stu-id="cc93c-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="cc93c-122">Para obtener más información, consulte [Cómo: instrucciones de la etiqueta](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="cc93c-122">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="cc93c-123">Concatenación</span><span class="sxs-lookup"><span data-stu-id="cc93c-123">Concatenation</span></span>  
 <span data-ttu-id="cc93c-124">Use la `&` operador para *concatenación*, o se vinculan las cadenas.</span><span class="sxs-lookup"><span data-stu-id="cc93c-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="cc93c-125">No debe confundirse con el `+` operador, que suma los valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="cc93c-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="cc93c-126">Si usas el `+` operador que se va a concatenar al operar en valores numéricos, puede obtener resultados incorrectos.</span><span class="sxs-lookup"><span data-stu-id="cc93c-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="cc93c-127">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="cc93c-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 <span data-ttu-id="cc93c-128">Tras la ejecución del código anterior, el valor de `resultA` es 21,01 y el valor de `resultB` es "10,0111".</span><span class="sxs-lookup"><span data-stu-id="cc93c-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="cc93c-129">Operadores de acceso a miembros</span><span class="sxs-lookup"><span data-stu-id="cc93c-129">Member Access Operators</span></span>  
 <span data-ttu-id="cc93c-130">Para obtener acceso a un miembro de un tipo, use el punto (`.`) o signo de exclamación (`!`) (operador) entre el nombre de tipo y el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="cc93c-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="cc93c-131">Punto (.) Operador</span><span class="sxs-lookup"><span data-stu-id="cc93c-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="cc93c-132">Use la `.` operador en una clase, estructura, interfaz o enumeración como un operador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="cc93c-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="cc93c-133">El miembro puede ser un campo, propiedad, evento o método.</span><span class="sxs-lookup"><span data-stu-id="cc93c-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="cc93c-134">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cc93c-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="cc93c-135">Signo de exclamación (!) Operador</span><span class="sxs-lookup"><span data-stu-id="cc93c-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="cc93c-136">Use la `!` operador solo en una clase o interfaz como un operador de acceso de diccionario.</span><span class="sxs-lookup"><span data-stu-id="cc93c-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="cc93c-137">La clase o interfaz debe tener una propiedad predeterminada que acepta un único `String` argumento.</span><span class="sxs-lookup"><span data-stu-id="cc93c-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="cc93c-138">El identificador que sigue inmediatamente el `!` operador se convierte en el valor del argumento pasado a la propiedad predeterminada como una cadena.</span><span class="sxs-lookup"><span data-stu-id="cc93c-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="cc93c-139">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="cc93c-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 <span data-ttu-id="cc93c-140">Las tres líneas de salida `MsgBox` todos mostrar el valor `32856`.</span><span class="sxs-lookup"><span data-stu-id="cc93c-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="cc93c-141">La primera línea utiliza el acceso tradicional a la propiedad `index`, la segunda hace uso del hecho de que `index` es la propiedad predeterminada de la clase `hasDefault`, y la tercera utiliza acceso de diccionario a la clase.</span><span class="sxs-lookup"><span data-stu-id="cc93c-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="cc93c-142">Tenga en cuenta que el segundo operando de la `!` operador debe ser un identificador válido de Visual Basic no está entre comillas dobles (`" "`).</span><span class="sxs-lookup"><span data-stu-id="cc93c-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="cc93c-143">En otras palabras, no se puede utilizar un literal de cadena o una variable de cadena.</span><span class="sxs-lookup"><span data-stu-id="cc93c-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="cc93c-144">Cambia ni lo siguiente a la última línea de la `MsgBox` llamada genera un error porque `"X"` es una cadena entre comillas literal.</span><span class="sxs-lookup"><span data-stu-id="cc93c-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="cc93c-145">Las referencias a colecciones predeterminadas deben ser explícitas.</span><span class="sxs-lookup"><span data-stu-id="cc93c-145">References to default collections must be explicit.</span></span> <span data-ttu-id="cc93c-146">En concreto, no puede usar el `!` operador en una variable en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cc93c-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="cc93c-147">El `!` caracteres también se usan como el `Single` carácter de tipo.</span><span class="sxs-lookup"><span data-stu-id="cc93c-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc93c-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc93c-148">See Also</span></span>  
 [<span data-ttu-id="cc93c-149">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="cc93c-149">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="cc93c-150">Caracteres de tipo</span><span class="sxs-lookup"><span data-stu-id="cc93c-150">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
