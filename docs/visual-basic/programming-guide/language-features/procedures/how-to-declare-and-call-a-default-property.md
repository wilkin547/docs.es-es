---
title: Filtrar Declarar y llamar a una propiedad predeterminada en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: 9ca9a0ccdac3ac13429928233a0c09d58427ce74
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295645"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="4466c-102">Filtrar Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4466c-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="4466c-103">Un *propiedad predeterminada* es una propiedad de clase o estructura que el código puede tener acceso sin especificarlo.</span><span class="sxs-lookup"><span data-stu-id="4466c-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="4466c-104">Al llamar a los nombres de código de una clase o estructura, pero no una propiedad y el contexto permite el acceso a una propiedad, Visual Basic resuelve el acceso a esa clase o propiedad de la estructura predeterminada si existe alguno.</span><span class="sxs-lookup"><span data-stu-id="4466c-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="4466c-105">Una clase o estructura puede tener como máximo una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4466c-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="4466c-106">Sin embargo, puede sobrecargar una propiedad predeterminada y tiene más de una versión de éste.</span><span class="sxs-lookup"><span data-stu-id="4466c-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="4466c-107">Para obtener más información, consulte [predeterminado](../../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="4466c-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="4466c-108">Para declarar una propiedad predeterminada</span><span class="sxs-lookup"><span data-stu-id="4466c-108">To declare a default property</span></span>  
  
1. <span data-ttu-id="4466c-109">Declare la propiedad de la manera normal.</span><span class="sxs-lookup"><span data-stu-id="4466c-109">Declare the property in the normal way.</span></span> <span data-ttu-id="4466c-110">No se especifica la `Shared` o `Private` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="4466c-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2. <span data-ttu-id="4466c-111">Incluir el `Default` palabra clave en la declaración de propiedad.</span><span class="sxs-lookup"><span data-stu-id="4466c-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3. <span data-ttu-id="4466c-112">Especifique al menos un parámetro para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="4466c-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="4466c-113">No se puede definir una propiedad predeterminada que no tiene al menos un argumento.</span><span class="sxs-lookup"><span data-stu-id="4466c-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="4466c-114">Para llamar a una propiedad predeterminada</span><span class="sxs-lookup"><span data-stu-id="4466c-114">To call a default property</span></span>  
  
1. <span data-ttu-id="4466c-115">Declare una variable del tipo de clase o estructura contenedora.</span><span class="sxs-lookup"><span data-stu-id="4466c-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. <span data-ttu-id="4466c-116">Utilice el nombre de variable solo en una expresión donde normalmente incluiría el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="4466c-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="4466c-117">Siga el nombre de variable con una lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="4466c-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="4466c-118">Una propiedad predeterminada debe tener al menos un argumento.</span><span class="sxs-lookup"><span data-stu-id="4466c-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. <span data-ttu-id="4466c-119">Para recuperar el valor de propiedad predeterminado, use el nombre de variable con una lista de argumentos en una expresión o siguiendo la igual (`=`) inicie sesión en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="4466c-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. <span data-ttu-id="4466c-120">Para establecer el valor de propiedad predeterminado, use el nombre de variable con una lista de argumentos, en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="4466c-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. <span data-ttu-id="4466c-121">Siempre puede especificar el nombre de propiedad predeterminado junto con el nombre de variable, justo como lo haría para tener acceso a cualquier otra propiedad.</span><span class="sxs-lookup"><span data-stu-id="4466c-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="4466c-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4466c-122">Example</span></span>  
 <span data-ttu-id="4466c-123">El ejemplo siguiente declara una propiedad predeterminada en una clase.</span><span class="sxs-lookup"><span data-stu-id="4466c-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="4466c-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4466c-124">Example</span></span>  
 <span data-ttu-id="4466c-125">En el ejemplo siguiente se muestra cómo llamar a la propiedad predeterminada `myProperty` en la clase `class1`.</span><span class="sxs-lookup"><span data-stu-id="4466c-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="4466c-126">Las tres instrucciones de asignación almacenan valores en `myProperty`y el <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> llamada lee los valores.</span><span class="sxs-lookup"><span data-stu-id="4466c-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 <span data-ttu-id="4466c-127">El uso más común de una propiedad predeterminada es la <xref:Microsoft.VisualBasic.Collection.Item%2A> propiedad en diversas clases de colección.</span><span class="sxs-lookup"><span data-stu-id="4466c-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4466c-128">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="4466c-128">Robust Programming</span></span>  
 <span data-ttu-id="4466c-129">Propiedades predeterminadas pueden producir una pequeña reducción en caracteres de código fuente, pero puede hacer que su código más difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="4466c-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="4466c-130">Si el código de llamada no está familiarizado con la clase o estructura, cuando realiza una referencia al nombre de clase o estructura no puede estar seguro si esa referencia tiene acceso a la clase o estructura en Sí o una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4466c-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="4466c-131">Esto puede conducir a errores del compilador o errores sutiles tiempo de ejecución de lógica.</span><span class="sxs-lookup"><span data-stu-id="4466c-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="4466c-132">Algo puede reducir la posibilidad de errores de propiedad predeterminado al usar siempre el [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) para establecer el tipo de compilador para la comprobación `On`.</span><span class="sxs-lookup"><span data-stu-id="4466c-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="4466c-133">Si va a usar una clase o estructura en el código, debe determinar si tiene una propiedad predeterminada y si es así, lo que su nombre es.</span><span class="sxs-lookup"><span data-stu-id="4466c-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="4466c-134">Debido a estos inconvenientes, considere la posibilidad de no definir propiedades predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="4466c-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="4466c-135">Para mejorar la legibilidad de código, debe también tener en cuenta siempre referencia explícitamente a todas las propiedades, propiedades incluso predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="4466c-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4466c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="4466c-136">See also</span></span>

- [<span data-ttu-id="4466c-137">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="4466c-137">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="4466c-138">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="4466c-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="4466c-139">Property Statement</span><span class="sxs-lookup"><span data-stu-id="4466c-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="4466c-140">Default</span><span class="sxs-lookup"><span data-stu-id="4466c-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)
- [<span data-ttu-id="4466c-141">Diferencias entre propiedades y variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4466c-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="4466c-142">Filtrar para crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="4466c-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="4466c-143">Filtrar para declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="4466c-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="4466c-144">Filtrar para llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="4466c-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="4466c-145">Filtrar para establecer un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="4466c-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="4466c-146">Filtrar para obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="4466c-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
