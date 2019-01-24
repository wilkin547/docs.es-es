---
title: Tipos de datos constantes y literales (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: d85ff343587e8689a4859a09c8dc80932374a82e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498653"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="5923f-102">Tipos de datos constantes y literales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5923f-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="5923f-103">Un literal es un valor que se expresa por sí misma, en lugar de como valor de una variable o el resultado de una expresión, como el número 3 o la cadena "Hello".</span><span class="sxs-lookup"><span data-stu-id="5923f-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="5923f-104">Una constante es un nombre descriptivo que ocupa el lugar de un literal y conserva este mismo valor en todo el programa, en lugar de una variable, cuyo valor puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="5923f-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="5923f-105">Cuando [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) es `Off` y [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) es `On`, debe declarar explícitamente todas las constantes con un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5923f-105">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="5923f-106">En el ejemplo siguiente, el tipo de datos de `MyByte` se declara explícitamente como tipo de datos `Byte`:</span><span class="sxs-lookup"><span data-stu-id="5923f-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 <span data-ttu-id="5923f-107">Cuando `Option Infer` es `On` o `Option Strict` es `Off`, puede declarar una constante sin especificar un tipo de datos con un `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="5923f-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="5923f-108">El compilador determina el tipo de la constante del tipo de la expresión.</span><span class="sxs-lookup"><span data-stu-id="5923f-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="5923f-109">Un literal de entero numérico se convierte de forma predeterminada para el `Integer` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="5923f-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="5923f-110">Tipo de datos predeterminado para números de punto flotante es `Double`y las palabras clave `True` y `False` especificar un `Boolean` constante.</span><span class="sxs-lookup"><span data-stu-id="5923f-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="5923f-111">Literales y conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="5923f-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="5923f-112">En algunos casos, es posible que desee forzar que un literal a un tipo de datos determinado; Por ejemplo, al asignar un valor literal integral especialmente grande a una variable de tipo `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="5923f-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="5923f-113">En el ejemplo siguiente, se produce un error:</span><span class="sxs-lookup"><span data-stu-id="5923f-113">The following example produces an error:</span></span>  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="5923f-114">Los resultados de error de la representación del literal.</span><span class="sxs-lookup"><span data-stu-id="5923f-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="5923f-115">El `Decimal` tipo de datos puede contener un valor de este tamaño, pero el literal implícitamente se representa como un `Long`, cuáles no.</span><span class="sxs-lookup"><span data-stu-id="5923f-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="5923f-116">Se puede convertir un literal a un tipo de datos determinado de dos maneras: mediante la anexión de un carácter de tipo a él o colocando entre caracteres de inclusión.</span><span class="sxs-lookup"><span data-stu-id="5923f-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="5923f-117">Un carácter de tipo o caracteres de cierre deben preceder inmediatamente o siga del literal, sin ningún espacio intermedio o cualquier tipo de carácter.</span><span class="sxs-lookup"><span data-stu-id="5923f-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="5923f-118">Para que funcione el ejemplo anterior, puede anexar el `D` escribir carácter en el literal, lo que hace que se puede representar como un `Decimal`:</span><span class="sxs-lookup"><span data-stu-id="5923f-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 <span data-ttu-id="5923f-119">El ejemplo siguiente muestra el uso correcto de caracteres de tipo y de inclusión:</span><span class="sxs-lookup"><span data-stu-id="5923f-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 <span data-ttu-id="5923f-120">La siguiente tabla muestra los caracteres de inclusión y caracteres de tipo disponibles en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5923f-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="5923f-121">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="5923f-121">Data type</span></span>|<span data-ttu-id="5923f-122">Carácter de inclusión</span><span class="sxs-lookup"><span data-stu-id="5923f-122">Enclosing character</span></span>|<span data-ttu-id="5923f-123">Carácter de tipo anexado</span><span class="sxs-lookup"><span data-stu-id="5923f-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="5923f-124">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="5923f-124">(none)</span></span>|<span data-ttu-id="5923f-125">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="5923f-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="5923f-126">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="5923f-126">(none)</span></span>|<span data-ttu-id="5923f-127">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="5923f-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="5923f-128">"</span><span class="sxs-lookup"><span data-stu-id="5923f-128">"</span></span>|<span data-ttu-id="5923f-129">C</span><span class="sxs-lookup"><span data-stu-id="5923f-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="5923f-130">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="5923f-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="5923f-131">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="5923f-131">(none)</span></span>|<span data-ttu-id="5923f-132">D. o @</span><span class="sxs-lookup"><span data-stu-id="5923f-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="5923f-133">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="5923f-133">(none)</span></span>|<span data-ttu-id="5923f-134">R o #</span><span class="sxs-lookup"><span data-stu-id="5923f-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="5923f-135">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="5923f-135">(none)</span></span>|<span data-ttu-id="5923f-136">O %</span><span class="sxs-lookup"><span data-stu-id="5923f-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="5923f-137">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="5923f-137">(none)</span></span>|<span data-ttu-id="5923f-138">L o &</span><span class="sxs-lookup"><span data-stu-id="5923f-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="5923f-139">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="5923f-139">(none)</span></span>|<span data-ttu-id="5923f-140">S</span><span class="sxs-lookup"><span data-stu-id="5923f-140">S</span></span>|  
|`Single`|<span data-ttu-id="5923f-141">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="5923f-141">(none)</span></span>|<span data-ttu-id="5923f-142">F o!</span><span class="sxs-lookup"><span data-stu-id="5923f-142">F or !</span></span>|  
|`String`|<span data-ttu-id="5923f-143">"</span><span class="sxs-lookup"><span data-stu-id="5923f-143">"</span></span>|<span data-ttu-id="5923f-144">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="5923f-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5923f-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="5923f-145">See also</span></span>
- [<span data-ttu-id="5923f-146">Constantes definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="5923f-146">User-Defined Constants</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [<span data-ttu-id="5923f-147">Cómo: Declarar una constante</span><span class="sxs-lookup"><span data-stu-id="5923f-147">How to: Declare A Constant</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [<span data-ttu-id="5923f-148">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="5923f-148">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [<span data-ttu-id="5923f-149">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5923f-149">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="5923f-150">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="5923f-150">Option Explicit Statement</span></span>](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="5923f-151">Información general sobre las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="5923f-151">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [<span data-ttu-id="5923f-152">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="5923f-152">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [<span data-ttu-id="5923f-153">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="5923f-153">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [<span data-ttu-id="5923f-154">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="5923f-154">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="5923f-155">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="5923f-155">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
