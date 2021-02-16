---
description: 'Más información sobre: Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic'
title: Procedimiento para declarar y llamar a una propiedad predeterminada
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
ms.openlocfilehash: 2a0e82fe89bb89613996f613930ace1aa6e41b7f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472454"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="77f9e-103">Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="77f9e-103">How to: Declare and Call a Default Property in Visual Basic</span></span>

<span data-ttu-id="77f9e-104">Una *propiedad predeterminada* es una propiedad de clase o estructura a la que el código puede tener acceso sin especificarla.</span><span class="sxs-lookup"><span data-stu-id="77f9e-104">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="77f9e-105">Cuando el código de llamada llama a una clase o estructura, pero no a una propiedad, y el contexto permite el acceso a una propiedad, Visual Basic resuelve el acceso a la propiedad predeterminada de la clase o la estructura, si existe una.</span><span class="sxs-lookup"><span data-stu-id="77f9e-105">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="77f9e-106">Una clase o estructura puede tener como máximo una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="77f9e-106">A class or structure can have at most one default property.</span></span> <span data-ttu-id="77f9e-107">Sin embargo, puede sobrecargar una propiedad predeterminada y tener más de una versión.</span><span class="sxs-lookup"><span data-stu-id="77f9e-107">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="77f9e-108">Para obtener más información, vea [default](../../../language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="77f9e-108">For more information, see [Default](../../../language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="77f9e-109">Para declarar una propiedad predeterminada</span><span class="sxs-lookup"><span data-stu-id="77f9e-109">To declare a default property</span></span>  
  
1. <span data-ttu-id="77f9e-110">Declare la propiedad de la manera normal.</span><span class="sxs-lookup"><span data-stu-id="77f9e-110">Declare the property in the normal way.</span></span> <span data-ttu-id="77f9e-111">No especifique la `Shared` `Private` palabra clave o.</span><span class="sxs-lookup"><span data-stu-id="77f9e-111">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2. <span data-ttu-id="77f9e-112">Incluya la `Default` palabra clave en la declaración de propiedad.</span><span class="sxs-lookup"><span data-stu-id="77f9e-112">Include the `Default` keyword in the property declaration.</span></span>  
  
3. <span data-ttu-id="77f9e-113">Especifique al menos un parámetro para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="77f9e-113">Specify at least one parameter for the property.</span></span> <span data-ttu-id="77f9e-114">No se puede definir una propiedad predeterminada que no tome al menos un argumento.</span><span class="sxs-lookup"><span data-stu-id="77f9e-114">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="77f9e-115">Para llamar a una propiedad predeterminada</span><span class="sxs-lookup"><span data-stu-id="77f9e-115">To call a default property</span></span>  
  
1. <span data-ttu-id="77f9e-116">Declare una variable de la clase contenedora o el tipo de estructura.</span><span class="sxs-lookup"><span data-stu-id="77f9e-116">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. <span data-ttu-id="77f9e-117">Use el nombre de la variable solo en una expresión en la que normalmente incluiría el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="77f9e-117">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="77f9e-118">Siga el nombre de la variable con una lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="77f9e-118">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="77f9e-119">Una propiedad predeterminada debe tomar al menos un argumento.</span><span class="sxs-lookup"><span data-stu-id="77f9e-119">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. <span data-ttu-id="77f9e-120">Para recuperar el valor de propiedad predeterminado, use el nombre de la variable, con una lista de argumentos, en una expresión o siguiendo el signo igual ( `=` ) en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="77f9e-120">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. <span data-ttu-id="77f9e-121">Para establecer el valor predeterminado de la propiedad, use el nombre de la variable, con una lista de argumentos, en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="77f9e-121">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. <span data-ttu-id="77f9e-122">Siempre puede especificar el nombre de la propiedad predeterminada junto con el nombre de la variable, tal y como haría para tener acceso a cualquier otra propiedad.</span><span class="sxs-lookup"><span data-stu-id="77f9e-122">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="77f9e-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77f9e-123">Example</span></span>  

 <span data-ttu-id="77f9e-124">En el ejemplo siguiente se declara una propiedad predeterminada en una clase.</span><span class="sxs-lookup"><span data-stu-id="77f9e-124">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="77f9e-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="77f9e-125">Example</span></span>  

 <span data-ttu-id="77f9e-126">En el ejemplo siguiente se muestra cómo llamar a la propiedad predeterminada `myProperty` en la clase `class1` .</span><span class="sxs-lookup"><span data-stu-id="77f9e-126">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="77f9e-127">Las tres instrucciones de asignación almacenan valores en `myProperty` y la <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> llamada Lee los valores.</span><span class="sxs-lookup"><span data-stu-id="77f9e-127">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 <span data-ttu-id="77f9e-128">El uso más común de una propiedad predeterminada es la <xref:Microsoft.VisualBasic.Collection.Item%2A> propiedad de varias clases de colección.</span><span class="sxs-lookup"><span data-stu-id="77f9e-128">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="77f9e-129">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="77f9e-129">Robust Programming</span></span>  

 <span data-ttu-id="77f9e-130">Las propiedades predeterminadas pueden dar lugar a una pequeña reducción en los caracteres de código fuente, pero pueden hacer que el código sea más difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="77f9e-130">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="77f9e-131">Si el código de llamada no está familiarizado con su clase o estructura, cuando hace referencia al nombre de la clase o de la estructura no puede estar seguro de si esa referencia tiene acceso a la clase o estructura, o a una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="77f9e-131">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="77f9e-132">Esto puede provocar errores del compilador o errores de lógica sutiles en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="77f9e-132">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="77f9e-133">Puede reducir en cierta medida la posibilidad de que se produzcan errores de propiedad predeterminados Si usa siempre la [instrucción Option Strict](../../../language-reference/statements/option-strict-statement.md) para establecer la comprobación del tipo de compilador en `On` .</span><span class="sxs-lookup"><span data-stu-id="77f9e-133">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="77f9e-134">Si piensa utilizar una clase o estructura predefinida en el código, debe determinar si tiene una propiedad predeterminada y, en ese caso, cuál es su nombre.</span><span class="sxs-lookup"><span data-stu-id="77f9e-134">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="77f9e-135">Debido a estas desventajas, considere la posibilidad de no definir las propiedades predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="77f9e-135">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="77f9e-136">Para facilitar la lectura del código, también debe considerar la posibilidad de hacer referencia siempre a todas las propiedades explícitamente, incluso a las propiedades predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="77f9e-136">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77f9e-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="77f9e-137">See also</span></span>

- [<span data-ttu-id="77f9e-138">Procedimientos de propiedad</span><span class="sxs-lookup"><span data-stu-id="77f9e-138">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="77f9e-139">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="77f9e-139">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="77f9e-140">Property Statement</span><span class="sxs-lookup"><span data-stu-id="77f9e-140">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="77f9e-141">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="77f9e-141">Default</span></span>](../../../language-reference/modifiers/default.md)
- [<span data-ttu-id="77f9e-142">Diferencias entre propiedades y variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="77f9e-142">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="77f9e-143">Procedimiento para crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="77f9e-143">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="77f9e-144">Procedimiento para declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="77f9e-144">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="77f9e-145">Procedimiento para llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="77f9e-145">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="77f9e-146">Procedimiento para establecer un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="77f9e-146">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="77f9e-147">Procedimiento para obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="77f9e-147">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
