---
title: "Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8baa03e37325a6ad7065ec1a60052b3ea6a46c6f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="8ebea-102">Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8ebea-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="8ebea-103">A *propiedad predeterminada* es una propiedad de clase o estructura que el código puede tener acceso sin especificarlo.</span><span class="sxs-lookup"><span data-stu-id="8ebea-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="8ebea-104">Al llamar a código nombres de una clase o estructura pero no una propiedad, y el contexto permite el acceso a una propiedad, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] resuelve el acceso a esa clase o una propiedad de la estructura de forma predeterminada, si existe.</span><span class="sxs-lookup"><span data-stu-id="8ebea-104">When calling code names a class or structure but not a property, and the context allows access to a property, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="8ebea-105">Una clase o estructura puede tener a lo sumo una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8ebea-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="8ebea-106">Sin embargo, puede sobrecargar una propiedad predeterminada y tener más de una versión del mismo.</span><span class="sxs-lookup"><span data-stu-id="8ebea-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="8ebea-107">Para obtener más información, consulte [predeterminado](../../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="8ebea-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="8ebea-108">Para declarar una propiedad predeterminada</span><span class="sxs-lookup"><span data-stu-id="8ebea-108">To declare a default property</span></span>  
  
1.  <span data-ttu-id="8ebea-109">Declare la propiedad de la forma habitual.</span><span class="sxs-lookup"><span data-stu-id="8ebea-109">Declare the property in the normal way.</span></span> <span data-ttu-id="8ebea-110">No se especifica la `Shared` o `Private` (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="8ebea-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2.  <span data-ttu-id="8ebea-111">Incluir el `Default` palabra clave en la declaración de propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ebea-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3.  <span data-ttu-id="8ebea-112">Especifique al menos un parámetro para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ebea-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="8ebea-113">No se puede definir una propiedad predeterminada que no tiene al menos un argumento.</span><span class="sxs-lookup"><span data-stu-id="8ebea-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="8ebea-114">Para llamar a una propiedad predeterminada</span><span class="sxs-lookup"><span data-stu-id="8ebea-114">To call a default property</span></span>  
  
1.  <span data-ttu-id="8ebea-115">Declare una variable del tipo de clase o estructura contenedora.</span><span class="sxs-lookup"><span data-stu-id="8ebea-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  <span data-ttu-id="8ebea-116">Utilice el nombre de variable solo en una expresión donde normalmente incluiría el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ebea-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  <span data-ttu-id="8ebea-117">Siga el nombre de variable con una lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="8ebea-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="8ebea-118">Una propiedad predeterminada debe tener al menos un argumento.</span><span class="sxs-lookup"><span data-stu-id="8ebea-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  <span data-ttu-id="8ebea-119">Para recuperar el valor de propiedad predeterminado, utilice el nombre de variable con una lista de argumentos, en una expresión o tras la igual (`=`) iniciar sesión en una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="8ebea-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  <span data-ttu-id="8ebea-120">Para establecer el valor de propiedad predeterminado, utilice el nombre de variable con una lista de argumentos, en el lado izquierdo de una instrucción de asignación.</span><span class="sxs-lookup"><span data-stu-id="8ebea-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  <span data-ttu-id="8ebea-121">Siempre puede especificar el nombre de propiedad predeterminado junto con el nombre de variable justo como lo haría para tener acceso a cualquier otra propiedad.</span><span class="sxs-lookup"><span data-stu-id="8ebea-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a><span data-ttu-id="8ebea-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ebea-122">Example</span></span>  
 <span data-ttu-id="8ebea-123">En el ejemplo siguiente se declara una propiedad predeterminada en una clase.</span><span class="sxs-lookup"><span data-stu-id="8ebea-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a><span data-ttu-id="8ebea-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ebea-124">Example</span></span>  
 <span data-ttu-id="8ebea-125">En el ejemplo siguiente se muestra cómo llamar a la propiedad predeterminada `myProperty` en la clase `class1`.</span><span class="sxs-lookup"><span data-stu-id="8ebea-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="8ebea-126">Las tres instrucciones de asignación almacenan valores en `myProperty`y el <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> llamada lee los valores.</span><span class="sxs-lookup"><span data-stu-id="8ebea-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 <span data-ttu-id="8ebea-127">El uso más común de una propiedad predeterminada es la <xref:Microsoft.VisualBasic.Collection.Item%2A> propiedad en diversas clases de colección.</span><span class="sxs-lookup"><span data-stu-id="8ebea-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8ebea-128">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="8ebea-128">Robust Programming</span></span>  
 <span data-ttu-id="8ebea-129">Propiedades predeterminadas pueden producir una pequeña reducción en caracteres de código fuente, pero puede hacer que el código más difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="8ebea-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="8ebea-130">Si el código de llamada no está familiarizado con la clase o estructura, cuando hace referencia al nombre de clase o estructura no podrá saber si esa referencia tiene acceso a la clase o estructura en Sí o una propiedad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8ebea-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="8ebea-131">Esto puede conducir a errores del compilador o errores sutiles lógicos de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8ebea-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="8ebea-132">Algo puede reducir la posibilidad de errores de propiedades de forma predeterminada al usar siempre el [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md) para establecer el tipo de compilador comprobación `On`.</span><span class="sxs-lookup"><span data-stu-id="8ebea-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="8ebea-133">Si planea usar una clase o estructura en el código, debe determinar si tiene una propiedad predeterminada y si es así, lo que su nombre es.</span><span class="sxs-lookup"><span data-stu-id="8ebea-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="8ebea-134">Debido a estas desventajas, considere la posibilidad de no definir propiedades predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="8ebea-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="8ebea-135">Para la legibilidad del código, debe tener en cuenta siempre que hace referencia a todas las propiedades de forma explícita, incluso predeterminados propiedades.</span><span class="sxs-lookup"><span data-stu-id="8ebea-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ebea-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ebea-136">See Also</span></span>  
 [<span data-ttu-id="8ebea-137">Procedimientos de propiedades</span><span class="sxs-lookup"><span data-stu-id="8ebea-137">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="8ebea-138">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="8ebea-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="8ebea-139">Property (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8ebea-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="8ebea-140">Predetermiado</span><span class="sxs-lookup"><span data-stu-id="8ebea-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)  
 [<span data-ttu-id="8ebea-141">Diferencias entre propiedades y Variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8ebea-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="8ebea-142">Crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="8ebea-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="8ebea-143">Declarar una propiedad con niveles de acceso mixtos</span><span class="sxs-lookup"><span data-stu-id="8ebea-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="8ebea-144">Llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="8ebea-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="8ebea-145">Establecer un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="8ebea-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="8ebea-146">Obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="8ebea-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
