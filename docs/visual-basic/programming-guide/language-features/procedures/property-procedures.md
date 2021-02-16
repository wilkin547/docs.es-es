---
description: 'Más información sobre: procedimientos de propiedad (Visual Basic)'
title: Procedimientos de propiedad
ms.date: 07/20/2015
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
ms.openlocfilehash: 55588278cdb8423a4f13a4e7ecc02f7ea692a618
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466593"
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="04e58-103">Procedimientos de propiedad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04e58-103">Property Procedures (Visual Basic)</span></span>

<span data-ttu-id="04e58-104">Un procedimiento de propiedad es una serie de instrucciones Visual Basic que manipulan una propiedad personalizada en un módulo, clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="04e58-104">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="04e58-105">Los procedimientos de propiedad también se conocen como *descriptores de acceso de propiedad*.</span><span class="sxs-lookup"><span data-stu-id="04e58-105">Property procedures are also known as *property accessors*.</span></span>

<span data-ttu-id="04e58-106">Visual Basic proporciona para los siguientes procedimientos de propiedad:</span><span class="sxs-lookup"><span data-stu-id="04e58-106">Visual Basic provides for the following property procedures:</span></span>

- <span data-ttu-id="04e58-107">Un `Get` procedimiento devuelve el valor de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="04e58-107">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="04e58-108">Se llama cuando se tiene acceso a la propiedad en una expresión.</span><span class="sxs-lookup"><span data-stu-id="04e58-108">It is called when you access the property in an expression.</span></span>
- <span data-ttu-id="04e58-109">Un `Set` procedimiento establece una propiedad en un valor, incluida una referencia de objeto.</span><span class="sxs-lookup"><span data-stu-id="04e58-109">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="04e58-110">Se llama al asignar un valor a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="04e58-110">It is called when you assign a value to the property.</span></span>

<span data-ttu-id="04e58-111">Normalmente, los procedimientos de propiedades se definen en pares, mediante las `Get` `Set` instrucciones y, pero se puede definir cualquier procedimiento solo si la propiedad es de solo lectura ([instrucción Get](../../../language-reference/statements/get-statement.md)) o de solo escritura ([instrucción set](../../../language-reference/statements/set-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="04e58-111">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../language-reference/statements/set-statement.md)).</span></span>

<span data-ttu-id="04e58-112">Puede omitir el `Get` `Set` procedimiento y cuando use una propiedad implementada automáticamente.</span><span class="sxs-lookup"><span data-stu-id="04e58-112">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="04e58-113">Para obtener más información, vea [Propiedades implementadas automáticamente](./auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="04e58-113">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>

<span data-ttu-id="04e58-114">Puede definir propiedades en clases, estructuras y módulos.</span><span class="sxs-lookup"><span data-stu-id="04e58-114">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="04e58-115">Las propiedades son de `Public` forma predeterminada, lo que significa que puede llamarlas desde cualquier lugar de la aplicación que pueda tener acceso al contenedor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="04e58-115">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>

<span data-ttu-id="04e58-116">Para obtener una comparación de propiedades y variables, vea [diferencias entre propiedades y variables en Visual Basic](differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="04e58-116">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](differences-between-properties-and-variables.md).</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="04e58-117">Sintaxis de declaración</span><span class="sxs-lookup"><span data-stu-id="04e58-117">Declaration syntax</span></span>

<span data-ttu-id="04e58-118">Una propiedad se define mediante un bloque de código incluido en la [instrucción Property](../../../language-reference/statements/property-statement.md) y la `End Property` instrucción.</span><span class="sxs-lookup"><span data-stu-id="04e58-118">A property itself is defined by a block of code enclosed within the [Property Statement](../../../language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="04e58-119">Dentro de este bloque, cada procedimiento de propiedad aparece como un bloque interno delimitado por una instrucción de declaración ( `Get` o `Set` ) y la declaración de coincidencia `End` .</span><span class="sxs-lookup"><span data-stu-id="04e58-119">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>

<span data-ttu-id="04e58-120">La sintaxis para declarar una propiedad y sus procedimientos es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="04e58-120">The syntax for declaring a property and its procedures is as follows:</span></span>

```vb
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
' - or -
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]
```

<span data-ttu-id="04e58-121">`Modifiers`Puede especificar el nivel de acceso e información relacionada con la sobrecarga, el reemplazo, el uso compartido y el sombreado, así como si la propiedad es de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="04e58-121">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="04e58-122">`AccessLevel`En el `Get` procedimiento o `Set` puede ser cualquier nivel que sea más restrictivo que el nivel de acceso especificado para la propiedad.</span><span class="sxs-lookup"><span data-stu-id="04e58-122">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="04e58-123">Para obtener más información, vea [Property Statement](../../../language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="04e58-123">For more information, see [Property Statement](../../../language-reference/statements/property-statement.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="04e58-124">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="04e58-124">Data Type</span></span>

<span data-ttu-id="04e58-125">El tipo de datos y el nivel de acceso principal de una propiedad se definen en la `Property` instrucción, no en los procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="04e58-125">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="04e58-126">Una propiedad solo puede tener un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="04e58-126">A property can have only one data type.</span></span> <span data-ttu-id="04e58-127">Por ejemplo, no se puede definir una propiedad para almacenar un `Decimal` valor, pero recuperar un `Double` valor.</span><span class="sxs-lookup"><span data-stu-id="04e58-127">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>

### <a name="access-level"></a><span data-ttu-id="04e58-128">Nivel de acceso</span><span class="sxs-lookup"><span data-stu-id="04e58-128">Access Level</span></span>

<span data-ttu-id="04e58-129">Sin embargo, puede definir un nivel de acceso principal para una propiedad y restringir aún más el nivel de acceso en uno de sus procedimientos de propiedad.</span><span class="sxs-lookup"><span data-stu-id="04e58-129">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="04e58-130">Por ejemplo, puede definir una `Public` propiedad y, a continuación, definir un `Private Set` procedimiento.</span><span class="sxs-lookup"><span data-stu-id="04e58-130">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="04e58-131">El `Get` procedimiento sigue siendo `Public` .</span><span class="sxs-lookup"><span data-stu-id="04e58-131">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="04e58-132">Puede cambiar el nivel de acceso solo en uno de los procedimientos de una propiedad, y solo puede hacer que sea más restrictivo que el nivel de acceso principal.</span><span class="sxs-lookup"><span data-stu-id="04e58-132">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="04e58-133">Para obtener más información, vea [Cómo: declarar una propiedad con niveles de acceso mixtos](how-to-declare-a-property-with-mixed-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="04e58-133">For more information, see [How to: Declare a Property with Mixed Access Levels](how-to-declare-a-property-with-mixed-access-levels.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="04e58-134">Declaración de parámetros</span><span class="sxs-lookup"><span data-stu-id="04e58-134">Parameter declaration</span></span>

<span data-ttu-id="04e58-135">Los parámetros se declaran de la misma manera que en los [procedimientos sub](sub-procedures.md), salvo que el mecanismo de paso debe ser `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="04e58-135">You declare each parameter the same way you do for [Sub Procedures](sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>

<span data-ttu-id="04e58-136">La sintaxis de cada parámetro de la lista de parámetros es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="04e58-136">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] ByVal [ParamArray] parametername As datatype
```

<span data-ttu-id="04e58-137">Si el parámetro es opcional, también debe proporcionar un valor predeterminado como parte de su declaración.</span><span class="sxs-lookup"><span data-stu-id="04e58-137">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="04e58-138">La sintaxis para especificar un valor predeterminado es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="04e58-138">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional ByVal parametername As datatype = defaultvalue
```

## <a name="property-value"></a><span data-ttu-id="04e58-139">Valor de propiedad</span><span class="sxs-lookup"><span data-stu-id="04e58-139">Property value</span></span>

<span data-ttu-id="04e58-140">En un `Get` procedimiento, el valor devuelto se proporciona a la expresión de llamada como el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="04e58-140">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>

<span data-ttu-id="04e58-141">En un `Set` procedimiento, el nuevo valor de la propiedad se pasa al parámetro de la `Set` instrucción.</span><span class="sxs-lookup"><span data-stu-id="04e58-141">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="04e58-142">Si declara explícitamente un parámetro, debe declararlo con el mismo tipo de datos que la propiedad.</span><span class="sxs-lookup"><span data-stu-id="04e58-142">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="04e58-143">Si no declara un parámetro, el compilador utiliza el parámetro implícito `Value` para representar el nuevo valor que se va a asignar a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="04e58-143">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="04e58-144">Sintaxis de llamada</span><span class="sxs-lookup"><span data-stu-id="04e58-144">Calling syntax</span></span>

<span data-ttu-id="04e58-145">Un procedimiento de propiedad se invoca implícitamente haciendo referencia a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="04e58-145">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="04e58-146">Use el nombre de la propiedad de la misma manera que usaría el nombre de una variable, salvo que debe proporcionar valores para todos los argumentos que no son opcionales y debe incluir la lista de argumentos entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="04e58-146">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="04e58-147">Si no se proporciona ningún argumento, puede omitir los paréntesis opcionalmente.</span><span class="sxs-lookup"><span data-stu-id="04e58-147">If no arguments are supplied, you can optionally omit the parentheses.</span></span>

<span data-ttu-id="04e58-148">La sintaxis de una llamada implícita a un `Set` procedimiento es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="04e58-148">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>

```vb
propertyname[(argumentlist)] = expression
```

<span data-ttu-id="04e58-149">La sintaxis de una llamada implícita a un `Get` procedimiento es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="04e58-149">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="04e58-150">Ilustración de declaration y Call</span><span class="sxs-lookup"><span data-stu-id="04e58-150">Illustration of declaration and call</span></span>

<span data-ttu-id="04e58-151">La siguiente propiedad almacena un nombre completo como dos nombres constituyentes, el nombre y el apellido.</span><span class="sxs-lookup"><span data-stu-id="04e58-151">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="04e58-152">Cuando el código de llamada Lee `fullName` , el `Get` procedimiento combina los dos nombres constituyentes y devuelve el nombre completo.</span><span class="sxs-lookup"><span data-stu-id="04e58-152">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="04e58-153">Cuando el código de llamada asigna un nuevo nombre completo, el `Set` procedimiento intenta dividirlo en dos nombres constituyentes.</span><span class="sxs-lookup"><span data-stu-id="04e58-153">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="04e58-154">Si no encuentra un espacio, lo almacena como el nombre.</span><span class="sxs-lookup"><span data-stu-id="04e58-154">If it does not find a space, it stores it all as the first name.</span></span>

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

<span data-ttu-id="04e58-155">En el ejemplo siguiente se muestran las llamadas típicas a los procedimientos de propiedad de `fullName` :</span><span class="sxs-lookup"><span data-stu-id="04e58-155">The following example shows typical calls to the property procedures of `fullName`:</span></span>

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a><span data-ttu-id="04e58-156">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04e58-156">See also</span></span>

- [<span data-ttu-id="04e58-157">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="04e58-157">Procedures</span></span>](index.md)
- [<span data-ttu-id="04e58-158">Procedimientos de función</span><span class="sxs-lookup"><span data-stu-id="04e58-158">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="04e58-159">Procedimientos de operador</span><span class="sxs-lookup"><span data-stu-id="04e58-159">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="04e58-160">Argumentos y parámetros de procedimiento</span><span class="sxs-lookup"><span data-stu-id="04e58-160">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="04e58-161">Diferencias entre propiedades y variables en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04e58-161">Differences Between Properties and Variables in Visual Basic</span></span>](differences-between-properties-and-variables.md)
- [<span data-ttu-id="04e58-162">Procedimiento para crear una propiedad</span><span class="sxs-lookup"><span data-stu-id="04e58-162">How to: Create a Property</span></span>](how-to-create-a-property.md)
- [<span data-ttu-id="04e58-163">Procedimiento para llamar a un procedimiento de propiedad</span><span class="sxs-lookup"><span data-stu-id="04e58-163">How to: Call a Property Procedure</span></span>](how-to-call-a-property-procedure.md)
- [<span data-ttu-id="04e58-164">Cómo: Declarar y llamar a una propiedad predeterminada en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="04e58-164">How to: Declare and Call a Default Property in Visual Basic</span></span>](how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="04e58-165">Procedimiento para establecer un valor en una propiedad</span><span class="sxs-lookup"><span data-stu-id="04e58-165">How to: Put a Value in a Property</span></span>](how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="04e58-166">Procedimiento para obtener un valor de una propiedad</span><span class="sxs-lookup"><span data-stu-id="04e58-166">How to: Get a Value from a Property</span></span>](how-to-get-a-value-from-a-property.md)
