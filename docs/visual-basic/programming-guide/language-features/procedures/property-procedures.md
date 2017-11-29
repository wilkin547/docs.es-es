---
title: Procedimientos de propiedad (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cbdf49d5c3eb5ef71b25a060d62f55f19098f445
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="15476-102">Procedimientos de propiedad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15476-102">Property Procedures (Visual Basic)</span></span>
<span data-ttu-id="15476-103">Un procedimiento de propiedad es una serie de [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] las instrucciones que manipulan una propiedad personalizada en un módulo, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="15476-103">A property procedure is a series of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="15476-104">Procedimientos de propiedad son también se denomina *descriptores de acceso de propiedad*.</span><span class="sxs-lookup"><span data-stu-id="15476-104">Property procedures are also known as *property accessors*.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="15476-105">Proporciona los procedimientos de propiedad siguientes:</span><span class="sxs-lookup"><span data-stu-id="15476-105"> provides for the following property procedures:</span></span>  
  
-   <span data-ttu-id="15476-106">A `Get` procedimiento devuelve el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="15476-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="15476-107">Se llama cuando tiene acceso a la propiedad en una expresión.</span><span class="sxs-lookup"><span data-stu-id="15476-107">It is called when you access the property in an expression.</span></span>  
  
-   <span data-ttu-id="15476-108">A `Set` procedimiento establece una propiedad en un valor, lo cual incluye una referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="15476-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="15476-109">Se llama cuando se asigna un valor a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="15476-109">It is called when you assign a value to the property.</span></span>  
  
 <span data-ttu-id="15476-110">Normalmente se definen los procedimientos de propiedad en pares, mediante la `Get` y `Set` las instrucciones, pero puede definir cualquier procedimiento solamente si la propiedad es de solo lectura ([instrucción Get](../../../../visual-basic/language-reference/statements/get-statement.md)) o de solo escritura ([establecer Instrucción](../../../../visual-basic/language-reference/statements/set-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="15476-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>  
  
 <span data-ttu-id="15476-111">Puede omitir el `Get` y `Set` procedimiento cuando se usa una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="15476-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="15476-112">Para obtener más información, vea [Propiedades implementadas automáticamente](./auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="15476-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="15476-113">Puede definir propiedades en las clases, estructuras y módulos.</span><span class="sxs-lookup"><span data-stu-id="15476-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="15476-114">Las propiedades son `Public` de forma predeterminada, lo que significa que se pueden llamar desde cualquier lugar en la aplicación que pueda tener acceso al contenedor de propiedades.</span><span class="sxs-lookup"><span data-stu-id="15476-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>  
  
 <span data-ttu-id="15476-115">Para obtener una comparación de propiedades y variables, consulte [diferencias entre propiedades y Variables en Visual Basic](./differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="15476-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md).</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="15476-116">Sintaxis de la declaración</span><span class="sxs-lookup"><span data-stu-id="15476-116">Declaration Syntax</span></span>  
 <span data-ttu-id="15476-117">Una propiedad en sí se define mediante un bloque de código delimitado por las [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md) y `End Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="15476-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="15476-118">Dentro de este bloque, cada procedimiento property aparece como un bloque interno encerrado entre una instrucción de declaración (`Get` o `Set`) y la búsqueda de coincidencias `End` declaración.</span><span class="sxs-lookup"><span data-stu-id="15476-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>  
  
 <span data-ttu-id="15476-119">La sintaxis para declarar una propiedad y sus procedimientos es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="15476-119">The syntax for declaring a property and its procedures is as follows:</span></span>  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 <span data-ttu-id="15476-120">La `Modifiers` puede especificar el nivel de acceso e información relativa a la sobrecarga, invalidación, uso compartido y sombreado, así como si la propiedad es de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="15476-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="15476-121">El `AccessLevel` en el `Get` o `Set` procedimiento puede ser cualquier nivel más restrictivo que el nivel de acceso especificado para la propiedad en Sí.</span><span class="sxs-lookup"><span data-stu-id="15476-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="15476-122">Para obtener más información, consulte [Property (instrucción)](../../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="15476-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="15476-123">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="15476-123">Data Type</span></span>  
 <span data-ttu-id="15476-124">Tipo de datos de una propiedad y el nivel de acceso principal se definen en el `Property` instrucción y no en los procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="15476-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="15476-125">Una propiedad puede tener solo un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="15476-125">A property can have only one data type.</span></span> <span data-ttu-id="15476-126">Por ejemplo, no se puede definir una propiedad que se va a almacenar un `Decimal` valor pero recuperar un `Double` valor.</span><span class="sxs-lookup"><span data-stu-id="15476-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>  
  
### <a name="access-level"></a><span data-ttu-id="15476-127">Nivel de acceso</span><span class="sxs-lookup"><span data-stu-id="15476-127">Access Level</span></span>  
 <span data-ttu-id="15476-128">Sin embargo, puede definir un nivel de acceso principal para una propiedad y restringir aún más el nivel de acceso en uno de los procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="15476-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="15476-129">Por ejemplo, puede definir un `Public` propiedad y, a continuación, defina un `Private Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="15476-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="15476-130">El `Get` procedimiento permanece `Public`.</span><span class="sxs-lookup"><span data-stu-id="15476-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="15476-131">Puede cambiar el nivel de acceso sólo en uno de los procedimientos de una propiedad, y sea aún más restrictivo que el nivel de acceso principal.</span><span class="sxs-lookup"><span data-stu-id="15476-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="15476-132">Para obtener más información, consulte [Cómo: declarar una propiedad con niveles de acceso mixtos](./how-to-declare-a-property-with-mixed-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="15476-132">For more information, see [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="15476-133">Declaración de parámetro</span><span class="sxs-lookup"><span data-stu-id="15476-133">Parameter Declaration</span></span>  
 <span data-ttu-id="15476-134">Declarar cada parámetro de la misma manera que lo hace para [Sub (procedimientos)](./sub-procedures.md), salvo que el mecanismo para pasar argumentos debe ser `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="15476-134">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>  
  
 <span data-ttu-id="15476-135">La sintaxis para cada parámetro en la lista de parámetros es como sigue:</span><span class="sxs-lookup"><span data-stu-id="15476-135">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 <span data-ttu-id="15476-136">Si el parámetro es opcional, también debe proporcionar un valor predeterminado como parte de su declaración.</span><span class="sxs-lookup"><span data-stu-id="15476-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="15476-137">La sintaxis para especificar un valor predeterminado es como sigue:</span><span class="sxs-lookup"><span data-stu-id="15476-137">The syntax for specifying a default value is as follows:</span></span>  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a><span data-ttu-id="15476-138">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="15476-138">Property Value</span></span>  
 <span data-ttu-id="15476-139">En un `Get` procedimiento, el valor devuelto se suministra a la expresión de llamada como el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="15476-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>  
  
 <span data-ttu-id="15476-140">En un `Set` procedimiento, el nuevo valor de propiedad se pasa al parámetro de la `Set` instrucción.</span><span class="sxs-lookup"><span data-stu-id="15476-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="15476-141">Si se declara explícitamente un parámetro, se debe declarar con el mismo tipo de datos como la propiedad.</span><span class="sxs-lookup"><span data-stu-id="15476-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="15476-142">Si no se declara un parámetro, el compilador utiliza el parámetro implícito `Value` para representar el nuevo valor que se asignará a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="15476-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="15476-143">Sintaxis de llamada</span><span class="sxs-lookup"><span data-stu-id="15476-143">Calling Syntax</span></span>  
 <span data-ttu-id="15476-144">Invocar un procedimiento de propiedad implícitamente haciendo referencia a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="15476-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="15476-145">Utilice el nombre de la propiedad de la misma manera que se debe utilizar el nombre de una variable, excepto en que debe proporcionar valores para todos los argumentos que no son opcionales, y debe incluir la lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="15476-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="15476-146">Si no se proporcionan argumentos, se pueden omitir los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="15476-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="15476-147">La sintaxis de una llamada implícita a un `Set` procedimiento es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="15476-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>  
  
 `propertyname[(argumentlist)] = expression`  
  
 <span data-ttu-id="15476-148">La sintaxis de una llamada implícita a un `Get` procedimiento es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="15476-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="15476-149">Ilustración de declaración y llamada</span><span class="sxs-lookup"><span data-stu-id="15476-149">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="15476-150">La propiedad siguiente almacena un nombre completo como dos nombres que lo componen, el nombre y el apellido.</span><span class="sxs-lookup"><span data-stu-id="15476-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="15476-151">Cuando se lee el código de llamada `fullName`, el `Get` procedimiento combina los dos nombres constituyentes y devuelve el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="15476-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="15476-152">Cuando el código de llamada asigna un nuevo nombre completo, el `Set` procedimiento intenta dividir en dos nombres que lo componen.</span><span class="sxs-lookup"><span data-stu-id="15476-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="15476-153">Si no encuentra un espacio, lo almacena todos como el nombre.</span><span class="sxs-lookup"><span data-stu-id="15476-153">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 <span data-ttu-id="15476-154">El ejemplo siguiente muestra las llamadas típicas a los procedimientos de propiedad de `fullName`.</span><span class="sxs-lookup"><span data-stu-id="15476-154">The following example shows typical calls to the property procedures of `fullName`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="15476-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="15476-155">See Also</span></span>  
 [<span data-ttu-id="15476-156">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="15476-156">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="15476-157">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="15476-157">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="15476-158">Procedimientos de operadores</span><span class="sxs-lookup"><span data-stu-id="15476-158">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="15476-159">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="15476-159">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="15476-160">Diferencias entre propiedades y Variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15476-160">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="15476-161">Crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="15476-161">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="15476-162">Llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="15476-162">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="15476-163">Cómo: declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="15476-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="15476-164">Establecer un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="15476-164">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="15476-165">Obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="15476-165">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
