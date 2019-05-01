---
title: Caracteres especiales en código (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 65fcd10521742e287c7934080b3352a06668df7a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967991"
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="cc715-102">Caracteres especiales en código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc715-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="cc715-103">A veces es necesario usar caracteres especiales en el código, es decir, los caracteres que no sean alfabéticos o numéricos.</span><span class="sxs-lookup"><span data-stu-id="cc715-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="cc715-104">La puntuación y caracteres especiales en el juego de caracteres de Visual Basic tienen varias finalidades, desde organizar el texto del programa hasta definir las tareas que realiza el compilador o el programa compilado.</span><span class="sxs-lookup"><span data-stu-id="cc715-104">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="cc715-105">No especifican que se deba realizar una operación.</span><span class="sxs-lookup"><span data-stu-id="cc715-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="cc715-106">Paréntesis</span><span class="sxs-lookup"><span data-stu-id="cc715-106">Parentheses</span></span>  
 <span data-ttu-id="cc715-107">Utilice paréntesis al definir un procedimiento, como un `Sub` o `Function`.</span><span class="sxs-lookup"><span data-stu-id="cc715-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="cc715-108">Todas las listas de argumentos de procedimiento debe ir entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="cc715-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="cc715-109">También se utilice paréntesis para agrupar las variables o argumentos en grupos lógicos, especialmente para invalidar el orden predeterminado de prioridad de operador en una expresión compleja.</span><span class="sxs-lookup"><span data-stu-id="cc715-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="cc715-110">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cc715-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 <span data-ttu-id="cc715-111">Tras la ejecución del código anterior, el valor de `d` es 8,225 y el valor de `e` es 3.</span><span class="sxs-lookup"><span data-stu-id="cc715-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="cc715-112">El cálculo para `d` utiliza la prioridad predeterminada de `/` sobre `+` y es equivalente a `d = b + (c / a)`.</span><span class="sxs-lookup"><span data-stu-id="cc715-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="cc715-113">Los paréntesis en el cálculo para `e` la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cc715-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="cc715-114">Separadores</span><span class="sxs-lookup"><span data-stu-id="cc715-114">Separators</span></span>  
 <span data-ttu-id="cc715-115">Separadores hacen lo que sugiere su nombre: separan dos secciones de código.</span><span class="sxs-lookup"><span data-stu-id="cc715-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="cc715-116">En Visual Basic, el carácter separador es los dos puntos (`:`).</span><span class="sxs-lookup"><span data-stu-id="cc715-116">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="cc715-117">Utilice separadores cuando desee incluir varias instrucciones en una sola línea en lugar de líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="cc715-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="cc715-118">Esto ahorra espacio y mejora la legibilidad del código.</span><span class="sxs-lookup"><span data-stu-id="cc715-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="cc715-119">El ejemplo siguiente muestra tres instrucciones separadas por signos de dos puntos.</span><span class="sxs-lookup"><span data-stu-id="cc715-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 <span data-ttu-id="cc715-120">Para obtener más información, vea [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="cc715-120">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="cc715-121">Los dos puntos (`:`) caracteres también se usan para identificar una etiqueta de instrucción.</span><span class="sxs-lookup"><span data-stu-id="cc715-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="cc715-122">Para obtener más información, vea [Cómo: Etiquetar instrucciones](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="cc715-122">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="cc715-123">Concatenación</span><span class="sxs-lookup"><span data-stu-id="cc715-123">Concatenation</span></span>  
 <span data-ttu-id="cc715-124">Use la `&` operador para *concatenación*, o vincular cadenas conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="cc715-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="cc715-125">No lo confunda con el `+` operador, que suma valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="cc715-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="cc715-126">Si usas el `+` para concatenar cuando se opera en valores numéricos, puede obtener resultados incorrectos.</span><span class="sxs-lookup"><span data-stu-id="cc715-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="cc715-127">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="cc715-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 <span data-ttu-id="cc715-128">Tras la ejecución del código anterior, el valor de `resultA` es 21,01 y el valor de `resultB` es "10,0111".</span><span class="sxs-lookup"><span data-stu-id="cc715-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="cc715-129">Operadores de acceso a miembros</span><span class="sxs-lookup"><span data-stu-id="cc715-129">Member Access Operators</span></span>  
 <span data-ttu-id="cc715-130">Para obtener acceso a un miembro de un tipo, usa el punto (`.`) o signo de exclamación (`!`) operador entre el nombre de tipo y el nombre del miembro.</span><span class="sxs-lookup"><span data-stu-id="cc715-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="cc715-131">Punto (.) Operador</span><span class="sxs-lookup"><span data-stu-id="cc715-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="cc715-132">Use el `.` operador en una clase, estructura, interfaz o enumeración como un operador de acceso de miembro.</span><span class="sxs-lookup"><span data-stu-id="cc715-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="cc715-133">El miembro puede ser un campo, propiedad, evento o método.</span><span class="sxs-lookup"><span data-stu-id="cc715-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="cc715-134">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cc715-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="cc715-135">Signo de exclamación (!) Operador</span><span class="sxs-lookup"><span data-stu-id="cc715-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="cc715-136">Use el `!` operador solo en una clase o interfaz como un operador de acceso de diccionario.</span><span class="sxs-lookup"><span data-stu-id="cc715-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="cc715-137">La clase o interfaz debe tener una propiedad predeterminada que acepta un único `String` argumento.</span><span class="sxs-lookup"><span data-stu-id="cc715-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="cc715-138">El identificador que sigue inmediatamente el `!` operador se convierte en el valor del argumento pasado a la propiedad predeterminada como una cadena.</span><span class="sxs-lookup"><span data-stu-id="cc715-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="cc715-139">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="cc715-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="cc715-140">Las tres líneas de salida `MsgBox` todos mostrar el valor `32856`.</span><span class="sxs-lookup"><span data-stu-id="cc715-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="cc715-141">La primera línea usa el acceso a propiedad tradicional `index`, el segundo usa el hecho de que `index` es la propiedad predeterminada de la clase `hasDefault`, y la tercera usa el acceso al diccionario para la clase.</span><span class="sxs-lookup"><span data-stu-id="cc715-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="cc715-142">Tenga en cuenta que el segundo operando de la `!` operador debe ser un identificador válido de Visual Basic no está entrecomillado comillas dobles (`" "`).</span><span class="sxs-lookup"><span data-stu-id="cc715-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="cc715-143">En otras palabras, no se puede utilizar un literal de cadena o una variable de cadena.</span><span class="sxs-lookup"><span data-stu-id="cc715-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="cc715-144">Los siguientes elementos cambiar a la última línea de la `MsgBox` llamada genera un error porque `"X"` es una cadena incluida literal.</span><span class="sxs-lookup"><span data-stu-id="cc715-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="cc715-145">Las referencias a colecciones predeterminadas deben ser explícitas.</span><span class="sxs-lookup"><span data-stu-id="cc715-145">References to default collections must be explicit.</span></span> <span data-ttu-id="cc715-146">En concreto, no puede usar el `!` operador en una variable en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cc715-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="cc715-147">El `!` carácter también se usa como el `Single` carácter de tipo.</span><span class="sxs-lookup"><span data-stu-id="cc715-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc715-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc715-148">See also</span></span>

- [<span data-ttu-id="cc715-149">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="cc715-149">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="cc715-150">Caracteres de tipo</span><span class="sxs-lookup"><span data-stu-id="cc715-150">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
