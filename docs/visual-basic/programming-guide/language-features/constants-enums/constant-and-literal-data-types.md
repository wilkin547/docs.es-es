---
title: Tipos de datos constantes y literales
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: b94259326b42104db05d9fc5bb09f686075d0759
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414536"
---
# <a name="constant-and-literal-data-types-visual-basic"></a><span data-ttu-id="71307-102">Tipos de datos constantes y literales (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71307-102">Constant and Literal Data Types (Visual Basic)</span></span>
<span data-ttu-id="71307-103">Un literal es un valor que se expresa como en sí mismo en lugar de como el valor de una variable o el resultado de una expresión, como el número 3 o la cadena "Hello".</span><span class="sxs-lookup"><span data-stu-id="71307-103">A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello".</span></span> <span data-ttu-id="71307-104">Una constante es un nombre significativo que ocupa el lugar de un literal y mantiene este mismo valor en todo el programa, en lugar de una variable, cuyo valor puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="71307-104">A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.</span></span>  
  
 <span data-ttu-id="71307-105">Cuando [Option Infer](../../../language-reference/statements/option-infer-statement.md) es `Off` y [Option Strict](../../../language-reference/statements/option-strict-statement.md) es `On` , debe declarar todas las constantes explícitamente con un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="71307-105">When [Option Infer](../../../language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type.</span></span> <span data-ttu-id="71307-106">En el ejemplo siguiente, el tipo de datos de `MyByte` se declara explícitamente como un tipo de datos `Byte` :</span><span class="sxs-lookup"><span data-stu-id="71307-106">In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:</span></span>  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 <span data-ttu-id="71307-107">Cuando `Option Infer` es `On` o `Option Strict` es `Off` , puede declarar una constante sin especificar un tipo de datos con una `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="71307-107">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="71307-108">El compilador determina el tipo de la constante a partir del tipo de la expresión.</span><span class="sxs-lookup"><span data-stu-id="71307-108">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="71307-109">Un literal numérico entero se convierte de forma predeterminada en el `Integer` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="71307-109">A numeric integer literal is cast by default to the `Integer` data type.</span></span> <span data-ttu-id="71307-110">El tipo de datos predeterminado para los números de punto flotante es `Double` , y las palabras clave `True` y `False` especifica una `Boolean` constante.</span><span class="sxs-lookup"><span data-stu-id="71307-110">The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.</span></span>  
  
## <a name="literals-and-type-coercion"></a><span data-ttu-id="71307-111">Literales y coerción de tipos</span><span class="sxs-lookup"><span data-stu-id="71307-111">Literals and Type Coercion</span></span>  
 <span data-ttu-id="71307-112">En algunos casos, puede que desee forzar un literal a un tipo de datos determinado. por ejemplo, al asignar un valor literal entero especialmente grande a una variable de tipo `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="71307-112">In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`.</span></span> <span data-ttu-id="71307-113">En el ejemplo siguiente se genera un error:</span><span class="sxs-lookup"><span data-stu-id="71307-113">The following example produces an error:</span></span>  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 <span data-ttu-id="71307-114">El error se produce a partir de la representación del literal.</span><span class="sxs-lookup"><span data-stu-id="71307-114">The error results from the representation of the literal.</span></span> <span data-ttu-id="71307-115">El `Decimal` tipo de datos puede contener un valor de gran tamaño, pero el literal se representa implícitamente como `Long` , que no puede.</span><span class="sxs-lookup"><span data-stu-id="71307-115">The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.</span></span>  
  
 <span data-ttu-id="71307-116">Puede forzar un literal a un tipo de datos determinado de dos maneras: anexando un carácter de tipo a él o colocándolo dentro de los caracteres envolventes.</span><span class="sxs-lookup"><span data-stu-id="71307-116">You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters.</span></span> <span data-ttu-id="71307-117">Un carácter de tipo o caracteres de cierre deben preceder o seguir inmediatamente al literal, sin espacios ni caracteres intermedios de ningún tipo.</span><span class="sxs-lookup"><span data-stu-id="71307-117">A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.</span></span>  
  
 <span data-ttu-id="71307-118">Para que el ejemplo anterior funcione, puede anexar el `D` carácter de tipo al literal, lo que hace que se represente como un `Decimal` :</span><span class="sxs-lookup"><span data-stu-id="71307-118">To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:</span></span>  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 <span data-ttu-id="71307-119">En el ejemplo siguiente se muestra el uso correcto de caracteres de tipo y caracteres de inclusión:</span><span class="sxs-lookup"><span data-stu-id="71307-119">The following example demonstrates correct usage of type characters and enclosing characters:</span></span>  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 <span data-ttu-id="71307-120">En la tabla siguiente se muestran los caracteres envolventes y los caracteres de tipo disponibles en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="71307-120">The following table shows the enclosing characters and type characters available in Visual Basic.</span></span>  
  
|<span data-ttu-id="71307-121">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="71307-121">Data type</span></span>|<span data-ttu-id="71307-122">Carácter envolvente</span><span class="sxs-lookup"><span data-stu-id="71307-122">Enclosing character</span></span>|<span data-ttu-id="71307-123">Carácter de tipo anexado</span><span class="sxs-lookup"><span data-stu-id="71307-123">Appended type character</span></span>|  
|---|---|---|  
|`Boolean`|<span data-ttu-id="71307-124">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="71307-124">(none)</span></span>|<span data-ttu-id="71307-125">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="71307-125">(none)</span></span>|  
|`Byte`|<span data-ttu-id="71307-126">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="71307-126">(none)</span></span>|<span data-ttu-id="71307-127">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="71307-127">(none)</span></span>|  
|`Char`|<span data-ttu-id="71307-128">"</span><span class="sxs-lookup"><span data-stu-id="71307-128">"</span></span>|<span data-ttu-id="71307-129">C</span><span class="sxs-lookup"><span data-stu-id="71307-129">C</span></span>|  
|`Date`|#|<span data-ttu-id="71307-130">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="71307-130">(none)</span></span>|  
|`Decimal`|<span data-ttu-id="71307-131">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="71307-131">(none)</span></span>|<span data-ttu-id="71307-132">D o @</span><span class="sxs-lookup"><span data-stu-id="71307-132">D or @</span></span>|  
|`Double`|<span data-ttu-id="71307-133">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="71307-133">(none)</span></span>|<span data-ttu-id="71307-134">R o #</span><span class="sxs-lookup"><span data-stu-id="71307-134">R or #</span></span>|  
|`Integer`|<span data-ttu-id="71307-135">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="71307-135">(none)</span></span>|<span data-ttu-id="71307-136">I o%</span><span class="sxs-lookup"><span data-stu-id="71307-136">I or %</span></span>|  
|`Long`|<span data-ttu-id="71307-137">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="71307-137">(none)</span></span>|<span data-ttu-id="71307-138">L o &</span><span class="sxs-lookup"><span data-stu-id="71307-138">L or &</span></span>|  
|`Short`|<span data-ttu-id="71307-139">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="71307-139">(none)</span></span>|<span data-ttu-id="71307-140">S</span><span class="sxs-lookup"><span data-stu-id="71307-140">S</span></span>|  
|`Single`|<span data-ttu-id="71307-141">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="71307-141">(none)</span></span>|<span data-ttu-id="71307-142">F o!</span><span class="sxs-lookup"><span data-stu-id="71307-142">F or !</span></span>|  
|`String`|<span data-ttu-id="71307-143">"</span><span class="sxs-lookup"><span data-stu-id="71307-143">"</span></span>|<span data-ttu-id="71307-144">(ninguno)</span><span class="sxs-lookup"><span data-stu-id="71307-144">(none)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71307-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="71307-145">See also</span></span>

- [<span data-ttu-id="71307-146">Constantes definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="71307-146">User-Defined Constants</span></span>](user-defined-constants.md)
- [<span data-ttu-id="71307-147">Procedimiento para declarar una constante</span><span class="sxs-lookup"><span data-stu-id="71307-147">How to: Declare A Constant</span></span>](how-to-declare-a-constant.md)
- [<span data-ttu-id="71307-148">Información general sobre las constantes</span><span class="sxs-lookup"><span data-stu-id="71307-148">Constants Overview</span></span>](constants-overview.md)
- [<span data-ttu-id="71307-149">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="71307-149">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="71307-150">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="71307-150">Option Explicit Statement</span></span>](../../../language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="71307-151">Información general sobre las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="71307-151">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="71307-152">Cómo: Declarar una enumeración</span><span class="sxs-lookup"><span data-stu-id="71307-152">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="71307-153">Enumeraciones y calificación de nombres</span><span class="sxs-lookup"><span data-stu-id="71307-153">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="71307-154">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="71307-154">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="71307-155">Constantes y enumeraciones</span><span class="sxs-lookup"><span data-stu-id="71307-155">Constants and Enumerations</span></span>](../../../language-reference/constants-and-enumerations.md)
