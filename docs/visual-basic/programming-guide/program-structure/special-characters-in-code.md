---
description: 'Más información sobre: caracteres especiales en el código (Visual Basic)'
title: Caracteres especiales en el código
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
ms.openlocfilehash: 4afadc13cea6cc41480cb1674b7ff6f31629b569
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468257"
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="f63a5-103">Caracteres especiales en código (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f63a5-103">Special Characters in Code (Visual Basic)</span></span>

<span data-ttu-id="f63a5-104">A veces, es necesario usar caracteres especiales en el código, es decir, caracteres que no son alfabéticos o numéricos.</span><span class="sxs-lookup"><span data-stu-id="f63a5-104">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="f63a5-105">Los caracteres de puntuación y especiales del juego de caracteres Visual Basic tienen varios usos, desde organizar el texto del programa hasta definir las tareas que realiza el compilador o el programa compilado.</span><span class="sxs-lookup"><span data-stu-id="f63a5-105">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="f63a5-106">No especifican que se deba realizar una operación.</span><span class="sxs-lookup"><span data-stu-id="f63a5-106">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="f63a5-107">Paréntesis</span><span class="sxs-lookup"><span data-stu-id="f63a5-107">Parentheses</span></span>  

 <span data-ttu-id="f63a5-108">Use paréntesis al definir un procedimiento, como `Sub` o `Function` .</span><span class="sxs-lookup"><span data-stu-id="f63a5-108">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="f63a5-109">Debe incluir todas las listas de argumentos de procedimientos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="f63a5-109">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="f63a5-110">También puede usar paréntesis para colocar variables o argumentos en grupos lógicos, especialmente para reemplazar el orden predeterminado de prioridad de los operadores en una expresión compleja.</span><span class="sxs-lookup"><span data-stu-id="f63a5-110">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="f63a5-111">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f63a5-111">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 <span data-ttu-id="f63a5-112">Después de la ejecución del código anterior, el valor de `d` es 8,225 y el valor de `e` es 3.</span><span class="sxs-lookup"><span data-stu-id="f63a5-112">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="f63a5-113">El cálculo de `d` utiliza la prioridad predeterminada de `/` over `+` y es equivalente a `d = b + (c / a)` .</span><span class="sxs-lookup"><span data-stu-id="f63a5-113">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="f63a5-114">Los paréntesis del cálculo para `e` invalidar la prioridad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f63a5-114">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="f63a5-115">Separadores</span><span class="sxs-lookup"><span data-stu-id="f63a5-115">Separators</span></span>  

 <span data-ttu-id="f63a5-116">Los separadores hacen lo que sugiere su nombre: separan secciones de código.</span><span class="sxs-lookup"><span data-stu-id="f63a5-116">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="f63a5-117">En Visual Basic, el carácter separador es el signo de dos puntos ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="f63a5-117">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="f63a5-118">Utilice separadores cuando desee incluir varias instrucciones en una sola línea en lugar de líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="f63a5-118">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="f63a5-119">Esto ahorra espacio y mejora la legibilidad del código.</span><span class="sxs-lookup"><span data-stu-id="f63a5-119">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="f63a5-120">En el ejemplo siguiente se muestran tres instrucciones separadas por dos puntos.</span><span class="sxs-lookup"><span data-stu-id="f63a5-120">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 <span data-ttu-id="f63a5-121">Para obtener más información, vea [Cómo: interrumpir y combinar instrucciones en el código](how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="f63a5-121">For more information, see [How to: Break and Combine Statements in Code](how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="f63a5-122">El carácter de dos puntos ( `:` ) también se usa para identificar una etiqueta de instrucción.</span><span class="sxs-lookup"><span data-stu-id="f63a5-122">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="f63a5-123">Para obtener más información, vea [Cómo: etiquetar instrucciones](how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="f63a5-123">For more information, see [How to: Label Statements](how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="f63a5-124">Concatenación</span><span class="sxs-lookup"><span data-stu-id="f63a5-124">Concatenation</span></span>  

 <span data-ttu-id="f63a5-125">Use el `&` operador para la *concatenación* o vincule cadenas.</span><span class="sxs-lookup"><span data-stu-id="f63a5-125">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="f63a5-126">No lo confunda con el `+` operador, que suma los valores numéricos.</span><span class="sxs-lookup"><span data-stu-id="f63a5-126">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="f63a5-127">Si usa el `+` operador para concatenar al trabajar con valores numéricos, puede obtener resultados incorrectos.</span><span class="sxs-lookup"><span data-stu-id="f63a5-127">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="f63a5-128">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f63a5-128">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 <span data-ttu-id="f63a5-129">Después de la ejecución del código anterior, el valor de `resultA` es 21,01 y el valor de `resultB` es "10,0111".</span><span class="sxs-lookup"><span data-stu-id="f63a5-129">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="f63a5-130">Operadores de acceso a miembros</span><span class="sxs-lookup"><span data-stu-id="f63a5-130">Member Access Operators</span></span>  

 <span data-ttu-id="f63a5-131">Para tener acceso a un miembro de un tipo, se usa el operador de punto ( `.` ) o el signo de exclamación ( `!` ) entre el nombre de tipo y el nombre de miembro.</span><span class="sxs-lookup"><span data-stu-id="f63a5-131">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="f63a5-132">Punto (.) Operator</span><span class="sxs-lookup"><span data-stu-id="f63a5-132">Dot (.) Operator</span></span>  

 <span data-ttu-id="f63a5-133">Use el `.` operador en una clase, estructura, interfaz o enumeración como un operador de acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="f63a5-133">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="f63a5-134">El miembro puede ser un campo, una propiedad, un evento o un método.</span><span class="sxs-lookup"><span data-stu-id="f63a5-134">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="f63a5-135">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f63a5-135">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="f63a5-136">Signo de exclamación (!) Operator</span><span class="sxs-lookup"><span data-stu-id="f63a5-136">Exclamation Point (!) Operator</span></span>  

 <span data-ttu-id="f63a5-137">Use el `!` operador solo en una clase o interfaz como operador de acceso a Diccionario.</span><span class="sxs-lookup"><span data-stu-id="f63a5-137">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="f63a5-138">La clase o la interfaz deben tener una propiedad predeterminada que acepte un solo `String` argumento.</span><span class="sxs-lookup"><span data-stu-id="f63a5-138">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="f63a5-139">El identificador que sigue inmediatamente al `!` operador se convierte en el valor de argumento pasado a la propiedad predeterminada como una cadena.</span><span class="sxs-lookup"><span data-stu-id="f63a5-139">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="f63a5-140">En el siguiente ejemplo se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f63a5-140">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="f63a5-141">Las tres líneas de salida `MsgBox` muestran el valor `32856` .</span><span class="sxs-lookup"><span data-stu-id="f63a5-141">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="f63a5-142">La primera línea usa el acceso tradicional a la propiedad `index` , la segunda hace uso del hecho que `index` es la propiedad predeterminada de la clase `hasDefault` y la tercera utiliza el acceso de diccionario a la clase.</span><span class="sxs-lookup"><span data-stu-id="f63a5-142">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="f63a5-143">Tenga en cuenta que el segundo operando del `!` operador debe ser un identificador de Visual Basic válido no incluido entre comillas dobles ( `" "` ).</span><span class="sxs-lookup"><span data-stu-id="f63a5-143">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="f63a5-144">En otras palabras, no puede usar un literal de cadena o una variable de cadena.</span><span class="sxs-lookup"><span data-stu-id="f63a5-144">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="f63a5-145">El siguiente cambio en la última línea de la `MsgBox` llamada genera un error porque `"X"` es un literal de cadena delimitado.</span><span class="sxs-lookup"><span data-stu-id="f63a5-145">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> <span data-ttu-id="f63a5-146">Las referencias a las colecciones predeterminadas deben ser explícitas.</span><span class="sxs-lookup"><span data-stu-id="f63a5-146">References to default collections must be explicit.</span></span> <span data-ttu-id="f63a5-147">En concreto, no se puede utilizar el `!` operador en una variable enlazada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f63a5-147">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="f63a5-148">El `!` carácter también se utiliza como `Single` carácter de tipo.</span><span class="sxs-lookup"><span data-stu-id="f63a5-148">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f63a5-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f63a5-149">See also</span></span>

- [<span data-ttu-id="f63a5-150">Convenciones de código y estructura de programas</span><span class="sxs-lookup"><span data-stu-id="f63a5-150">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="f63a5-151">Caracteres de tipo</span><span class="sxs-lookup"><span data-stu-id="f63a5-151">Type Characters</span></span>](../language-features/data-types/type-characters.md)
