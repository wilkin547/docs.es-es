---
description: 'Más información acerca de: instrucción Dim (Visual Basic)'
title: Dim (instrucción)
ms.date: 05/12/2018
f1_keywords:
- vb.Dim
- Dim
helpviewer_keywords:
- Public keyword [Visual Basic], in Dim statement
- Dim statement [Visual Basic]
- fixed-length strings [Visual Basic], declaring
- variables [Visual Basic], declaring
- WithEvents keyword [Visual Basic], Dim statement
- dynamic arrays [Visual Basic], Dim statement
- variables [Visual Basic], initializing
- '{} braces'
- fields [Visual Basic], as member variables
- declarations [Visual Basic], dynamic arrays
- member variables [Visual Basic]
- default values [Visual Basic]
- data types [Visual Basic], assigning
- braces {}
- As keyword [Visual Basic], in Dim statement
- arrays [Visual Basic], declaring
- New keyword [Visual Basic], Dim statement
- To keyword [Visual Basic], in Dim statement
- storage [Visual Basic], allocating
- local variables [Visual Basic]
- declaration statements [Visual Basic]
- Dim statement [Visual Basic], syntax
- variables [Visual Basic], member and local
ms.assetid: fae3eca1-f0b2-4400-994b-7aa58a848448
ms.openlocfilehash: b950ae95af01be4e064ac9177300f144e0cc08b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795201"
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="01ce3-103">DIM (instrucción Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01ce3-103">Dim statement (Visual Basic)</span></span>

<span data-ttu-id="01ce3-104">Declara y asigna espacio de almacenamiento para una o más variables.</span><span class="sxs-lookup"><span data-stu-id="01ce3-104">Declares and allocates storage space for one or more variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="01ce3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01ce3-105">Syntax</span></span>

```vb
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]
Dim [ WithEvents ] variablelist
```

## <a name="parts"></a><span data-ttu-id="01ce3-106">Partes</span><span class="sxs-lookup"><span data-stu-id="01ce3-106">Parts</span></span>

- `attributelist`

  <span data-ttu-id="01ce3-107">Opcional.</span><span class="sxs-lookup"><span data-stu-id="01ce3-107">Optional.</span></span> <span data-ttu-id="01ce3-108">Vea [lista de atributos](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-108">See [Attribute List](attribute-list.md).</span></span>

- `accessmodifier`

  <span data-ttu-id="01ce3-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="01ce3-109">Optional.</span></span> <span data-ttu-id="01ce3-110">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="01ce3-110">Can be one of the following:</span></span>

  - [<span data-ttu-id="01ce3-111">Público</span><span class="sxs-lookup"><span data-stu-id="01ce3-111">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="01ce3-112">Protegido</span><span class="sxs-lookup"><span data-stu-id="01ce3-112">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="01ce3-113">Friend</span><span class="sxs-lookup"><span data-stu-id="01ce3-113">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="01ce3-114">Privado</span><span class="sxs-lookup"><span data-stu-id="01ce3-114">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="01ce3-115">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="01ce3-115">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="01ce3-116">Private Protected</span><span class="sxs-lookup"><span data-stu-id="01ce3-116">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="01ce3-117">Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-117">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `Shared`

  <span data-ttu-id="01ce3-118">Opcional.</span><span class="sxs-lookup"><span data-stu-id="01ce3-118">Optional.</span></span> <span data-ttu-id="01ce3-119">Vea [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-119">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="01ce3-120">Opcional.</span><span class="sxs-lookup"><span data-stu-id="01ce3-120">Optional.</span></span> <span data-ttu-id="01ce3-121">Vea [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-121">See [Shadows](../modifiers/shadows.md).</span></span>

- `Static`

  <span data-ttu-id="01ce3-122">Opcional.</span><span class="sxs-lookup"><span data-stu-id="01ce3-122">Optional.</span></span> <span data-ttu-id="01ce3-123">Vea [static](../modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-123">See [Static](../modifiers/static.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="01ce3-124">Opcional.</span><span class="sxs-lookup"><span data-stu-id="01ce3-124">Optional.</span></span> <span data-ttu-id="01ce3-125">Vea [ReadOnly](../modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-125">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WithEvents`

  <span data-ttu-id="01ce3-126">Opcional.</span><span class="sxs-lookup"><span data-stu-id="01ce3-126">Optional.</span></span> <span data-ttu-id="01ce3-127">Especifica que se trata de variables de objeto que hacen referencia a las instancias de una clase que puede generar eventos.</span><span class="sxs-lookup"><span data-stu-id="01ce3-127">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="01ce3-128">Vea [WithEvents](../modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-128">See [WithEvents](../modifiers/withevents.md).</span></span>

- `variablelist`

  <span data-ttu-id="01ce3-129">Necesario.</span><span class="sxs-lookup"><span data-stu-id="01ce3-129">Required.</span></span> <span data-ttu-id="01ce3-130">Lista de variables que se declaran en esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="01ce3-130">List of variables being declared in this statement.</span></span>

  `variable [ , variable ... ]`

  <span data-ttu-id="01ce3-131">Cada `variable` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="01ce3-131">Each `variable` has the following syntax and parts:</span></span>

  <span data-ttu-id="01ce3-132">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="01ce3-132">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>

  |<span data-ttu-id="01ce3-133">Parte</span><span class="sxs-lookup"><span data-stu-id="01ce3-133">Part</span></span>|<span data-ttu-id="01ce3-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="01ce3-134">Description</span></span>|
  |---|---|
  |`variablename`|<span data-ttu-id="01ce3-135">Necesario.</span><span class="sxs-lookup"><span data-stu-id="01ce3-135">Required.</span></span> <span data-ttu-id="01ce3-136">nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="01ce3-136">Name of the variable.</span></span> <span data-ttu-id="01ce3-137">Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-137">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|
  |`boundslist`|<span data-ttu-id="01ce3-138">Opcional.</span><span class="sxs-lookup"><span data-stu-id="01ce3-138">Optional.</span></span> <span data-ttu-id="01ce3-139">Lista de los límites de cada dimensión de una variable de matriz.</span><span class="sxs-lookup"><span data-stu-id="01ce3-139">List of bounds of each dimension of an array variable.</span></span>|
  |`New`|<span data-ttu-id="01ce3-140">Opcional.</span><span class="sxs-lookup"><span data-stu-id="01ce3-140">Optional.</span></span> <span data-ttu-id="01ce3-141">Crea una nueva instancia de la clase cuando `Dim` se ejecuta la instrucción.</span><span class="sxs-lookup"><span data-stu-id="01ce3-141">Creates a new instance of the class when the `Dim` statement runs.</span></span>|
  |`datatype`|<span data-ttu-id="01ce3-142">Opcional.</span><span class="sxs-lookup"><span data-stu-id="01ce3-142">Optional.</span></span> <span data-ttu-id="01ce3-143">Tipo de datos de la variable.</span><span class="sxs-lookup"><span data-stu-id="01ce3-143">Data type of the variable.</span></span>|
  |`With`|<span data-ttu-id="01ce3-144">Opcional.</span><span class="sxs-lookup"><span data-stu-id="01ce3-144">Optional.</span></span> <span data-ttu-id="01ce3-145">Presenta la lista de inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="01ce3-145">Introduces the object initializer list.</span></span>|
  |`propertyname`|<span data-ttu-id="01ce3-146">Opcional.</span><span class="sxs-lookup"><span data-stu-id="01ce3-146">Optional.</span></span> <span data-ttu-id="01ce3-147">Nombre de una propiedad de la clase en la que se va a crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="01ce3-147">The name of a property in the class you are making an instance of.</span></span>|
  |`propinitializer`|<span data-ttu-id="01ce3-148">Requerido después de `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="01ce3-148">Required after `propertyname` =.</span></span> <span data-ttu-id="01ce3-149">Expresión que se evalúa y asigna al nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="01ce3-149">The expression that is evaluated and assigned to the property name.</span></span>|
  |`initializer`|<span data-ttu-id="01ce3-150">Opcional si `New` no se especifica.</span><span class="sxs-lookup"><span data-stu-id="01ce3-150">Optional if `New` is not specified.</span></span> <span data-ttu-id="01ce3-151">Expresión que se evalúa y se asigna a la variable cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="01ce3-151">Expression that is evaluated and assigned to the variable when it is created.</span></span>|

## <a name="remarks"></a><span data-ttu-id="01ce3-152">Observaciones</span><span class="sxs-lookup"><span data-stu-id="01ce3-152">Remarks</span></span>

<span data-ttu-id="01ce3-153">El compilador Visual Basic usa la `Dim` instrucción para determinar el tipo de datos de la variable y otra información, como el código que puede tener acceso a la variable.</span><span class="sxs-lookup"><span data-stu-id="01ce3-153">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="01ce3-154">En el ejemplo siguiente se declara una variable para que contenga un `Integer` valor.</span><span class="sxs-lookup"><span data-stu-id="01ce3-154">The following example declares a variable to hold an `Integer` value.</span></span>

```vb
Dim numberOfStudents As Integer
```

<span data-ttu-id="01ce3-155">Puede especificar cualquier tipo de datos o el nombre de una enumeración, estructura, clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="01ce3-155">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

```vb
Dim finished As Boolean
Dim monitorBox As System.Windows.Forms.Form
```

<span data-ttu-id="01ce3-156">Para un tipo de referencia, use la `New` palabra clave para crear una nueva instancia de la clase o estructura especificada por el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="01ce3-156">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="01ce3-157">Si usa `New` , no utiliza una expresión de inicializador.</span><span class="sxs-lookup"><span data-stu-id="01ce3-157">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="01ce3-158">En su lugar, se proporcionan argumentos, si son necesarios, al constructor de la clase a partir de la cual se crea la variable.</span><span class="sxs-lookup"><span data-stu-id="01ce3-158">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>

```vb
Dim bottomLabel As New System.Windows.Forms.Label
```

<span data-ttu-id="01ce3-159">Puede declarar una variable en un procedimiento, un bloque, una clase, una estructura o un módulo.</span><span class="sxs-lookup"><span data-stu-id="01ce3-159">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="01ce3-160">No se puede declarar una variable en un archivo de código fuente, un espacio de nombres o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="01ce3-160">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="01ce3-161">Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="01ce3-161">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="01ce3-162">Una variable que se declara en el nivel de módulo, fuera de cualquier procedimiento, es una variable o *campo* *miembro* .</span><span class="sxs-lookup"><span data-stu-id="01ce3-162">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="01ce3-163">Las variables de miembro están en el ámbito a lo largo de su clase, estructura o módulo.</span><span class="sxs-lookup"><span data-stu-id="01ce3-163">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="01ce3-164">Una variable que se declara en el nivel de procedimiento es una *variable local*.</span><span class="sxs-lookup"><span data-stu-id="01ce3-164">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="01ce3-165">Las variables locales están en el ámbito solo dentro de su procedimiento o bloque.</span><span class="sxs-lookup"><span data-stu-id="01ce3-165">Local variables are in scope only within their procedure or block.</span></span>

<span data-ttu-id="01ce3-166">Los modificadores de acceso siguientes se usan para declarar variables fuera de un procedimiento: `Public` , `Protected` , `Friend` , `Protected Friend` y `Private` .</span><span class="sxs-lookup"><span data-stu-id="01ce3-166">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="01ce3-167">Para obtener más información, consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-167">For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="01ce3-168">La `Dim` palabra clave es opcional y normalmente se omite si se especifica cualquiera de los modificadores siguientes: `Public` , `Protected` , `Friend` , `Protected Friend` , `Private` , `Shared` , `Shadows` ,, `Static` `ReadOnly` o `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="01ce3-168">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>

```vb
Public maximumAllowed As Double
Protected Friend currentUserName As String
Private salary As Decimal
Static runningTotal As Integer
```

<span data-ttu-id="01ce3-169">Si `Option Explicit` es on (valor predeterminado), el compilador requiere una declaración para cada variable que se use.</span><span class="sxs-lookup"><span data-stu-id="01ce3-169">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="01ce3-170">Para obtener más información, vea [Option Explicit (instrucción](option-explicit-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="01ce3-170">For more information, see [Option Explicit Statement](option-explicit-statement.md).</span></span>

## <a name="specifying-an-initial-value"></a><span data-ttu-id="01ce3-171">Especificar un valor inicial</span><span class="sxs-lookup"><span data-stu-id="01ce3-171">Specifying an initial value</span></span>

<span data-ttu-id="01ce3-172">Puede asignar un valor a una variable cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="01ce3-172">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="01ce3-173">Para un tipo de valor, se usa un *inicializador* para proporcionar una expresión que se va a asignar a la variable.</span><span class="sxs-lookup"><span data-stu-id="01ce3-173">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="01ce3-174">La expresión se debe evaluar como una constante que se puede calcular en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="01ce3-174">The expression must evaluate to a constant that can be calculated at compile time.</span></span>

```vb
Dim quantity As Integer = 10
Dim message As String = "Just started"
```

<span data-ttu-id="01ce3-175">Si se especifica un inicializador y no se especifica un tipo de datos en una `As` cláusula, la *inferencia de tipos* se utiliza para deducir el tipo de datos del inicializador.</span><span class="sxs-lookup"><span data-stu-id="01ce3-175">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="01ce3-176">En el ejemplo siguiente, `num1` y `num2` están fuertemente tipados como enteros.</span><span class="sxs-lookup"><span data-stu-id="01ce3-176">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="01ce3-177">En la segunda declaración, la inferencia de tipos infiere el tipo a partir del valor 3.</span><span class="sxs-lookup"><span data-stu-id="01ce3-177">In the second declaration, type inference infers the type from the value 3.</span></span>

```vb
' Use explicit typing.
Dim num1 As Integer = 3

' Use local type inference.
Dim num2 = 3
```

<span data-ttu-id="01ce3-178">La inferencia de tipos se aplica en el nivel de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01ce3-178">Type inference applies at the procedure level.</span></span> <span data-ttu-id="01ce3-179">No se aplica fuera de un procedimiento en una clase, estructura, módulo o interfaz.</span><span class="sxs-lookup"><span data-stu-id="01ce3-179">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="01ce3-180">Para obtener más información sobre la inferencia de tipos, vea [Option Infer Statement](option-infer-statement.md) e [inferencia de tipo local](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-180">For more information about type inference, see [Option Infer Statement](option-infer-statement.md) and [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>

<span data-ttu-id="01ce3-181">Para obtener información sobre lo que ocurre cuando no se especifica un tipo de datos o un inicializador, vea [valores y tipos de datos predeterminados](dim-statement.md#default) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="01ce3-181">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](dim-statement.md#default) later in this topic.</span></span>

<span data-ttu-id="01ce3-182">Puede usar un *inicializador de objeto* para declarar instancias de tipos con nombre y anónimos.</span><span class="sxs-lookup"><span data-stu-id="01ce3-182">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="01ce3-183">En el código siguiente se crea una instancia de una `Student` clase y se utiliza un inicializador de objeto para inicializar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="01ce3-183">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>

```vb
Dim student1 As New Student With {.First = "Michael",
                                  .Last = "Tucker"}
```

<span data-ttu-id="01ce3-184">Para obtener más información sobre los inicializadores de objeto, vea [Cómo: declarar un objeto usando un inicializador](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)de objeto, [inicializadores de objeto: tipos con nombre y anónimos](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), y [tipos anónimos](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-184">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

## <a name="declaring-multiple-variables"></a><span data-ttu-id="01ce3-185">Declarar varias variables</span><span class="sxs-lookup"><span data-stu-id="01ce3-185">Declaring multiple variables</span></span>

<span data-ttu-id="01ce3-186">Puede declarar varias variables en una instrucción de declaración, especificando el nombre de la variable para cada una de ellas y siguiendo cada nombre de matriz entre paréntesis.</span><span class="sxs-lookup"><span data-stu-id="01ce3-186">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="01ce3-187">Las variables se separan con comas.</span><span class="sxs-lookup"><span data-stu-id="01ce3-187">Multiple variables are separated by commas.</span></span>

```vb
Dim lastTime, nextTime, allTimes() As Date
```

<span data-ttu-id="01ce3-188">Si se declara más de una variable con una `As` cláusula, no se puede proporcionar un inicializador para ese grupo de variables.</span><span class="sxs-lookup"><span data-stu-id="01ce3-188">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>

<span data-ttu-id="01ce3-189">Puede especificar tipos de datos diferentes para variables diferentes mediante una cláusula independiente `As` para cada variable que declare.</span><span class="sxs-lookup"><span data-stu-id="01ce3-189">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="01ce3-190">Cada variable toma el tipo de datos especificado en la primera cláusula que se `As` encuentra después de su `variablename` parte.</span><span class="sxs-lookup"><span data-stu-id="01ce3-190">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>

```vb
Dim a, b, c As Single, x, y As Double, i As Integer
' a, b, and c are all Single; x and y are both Double
```

## <a name="arrays"></a><span data-ttu-id="01ce3-191">Matrices</span><span class="sxs-lookup"><span data-stu-id="01ce3-191">Arrays</span></span>

<span data-ttu-id="01ce3-192">Puede declarar una variable para que contenga una *matriz*, que puede contener varios valores.</span><span class="sxs-lookup"><span data-stu-id="01ce3-192">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="01ce3-193">Para especificar que una variable contiene una matriz, siga `variablename` inmediatamente con paréntesis.</span><span class="sxs-lookup"><span data-stu-id="01ce3-193">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="01ce3-194">Para obtener más información sobre las matrices, consulte [Matrices](../../programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-194">For more information about arrays, see [Arrays](../../programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="01ce3-195">Puede especificar el límite inferior y superior de cada dimensión de una matriz.</span><span class="sxs-lookup"><span data-stu-id="01ce3-195">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="01ce3-196">Para ello, incluya un `boundslist` dentro de los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="01ce3-196">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="01ce3-197">Para cada dimensión, `boundslist` especifica el límite superior y, opcionalmente, el límite inferior.</span><span class="sxs-lookup"><span data-stu-id="01ce3-197">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="01ce3-198">El límite inferior es siempre cero, tanto si se especifica como si no.</span><span class="sxs-lookup"><span data-stu-id="01ce3-198">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="01ce3-199">Cada índice puede variar de cero a través de su valor de límite superior.</span><span class="sxs-lookup"><span data-stu-id="01ce3-199">Each index can vary from zero through its upper bound value.</span></span>

<span data-ttu-id="01ce3-200">Las dos instrucciones siguientes son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="01ce3-200">The following two statements are equivalent.</span></span> <span data-ttu-id="01ce3-201">Cada instrucción declara una matriz de 21 `Integer` elementos.</span><span class="sxs-lookup"><span data-stu-id="01ce3-201">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="01ce3-202">Al tener acceso a la matriz, el índice puede variar de 0 a 20.</span><span class="sxs-lookup"><span data-stu-id="01ce3-202">When you access the array, the index can vary from 0 through 20.</span></span>

```vb
Dim totals(20) As Integer
Dim totals(0 To 20) As Integer
```

<span data-ttu-id="01ce3-203">La instrucción siguiente declara una matriz bidimensional de tipo `Double` .</span><span class="sxs-lookup"><span data-stu-id="01ce3-203">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="01ce3-204">La matriz tiene 4 filas (3 + 1) de 6 columnas (5 + 1) cada una.</span><span class="sxs-lookup"><span data-stu-id="01ce3-204">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="01ce3-205">Tenga en cuenta que un límite superior representa el valor más alto posible para el índice, no la longitud de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="01ce3-205">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="01ce3-206">La longitud de la dimensión es el límite superior más uno.</span><span class="sxs-lookup"><span data-stu-id="01ce3-206">The length of the dimension is the upper bound plus one.</span></span>

```vb
Dim matrix2(3, 5) As Double
```

<span data-ttu-id="01ce3-207">Una matriz puede tener de 1 a 32 dimensiones.</span><span class="sxs-lookup"><span data-stu-id="01ce3-207">An array can have from 1 to 32 dimensions.</span></span>

<span data-ttu-id="01ce3-208">Puede dejar todos los límites en blanco en una declaración de matriz.</span><span class="sxs-lookup"><span data-stu-id="01ce3-208">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="01ce3-209">Si lo hace, la matriz tiene el número de dimensiones que especifique, pero no se inicializa.</span><span class="sxs-lookup"><span data-stu-id="01ce3-209">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="01ce3-210">Tiene un valor de `Nothing` hasta que inicializa al menos algunos de sus elementos.</span><span class="sxs-lookup"><span data-stu-id="01ce3-210">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="01ce3-211">La `Dim` instrucción debe especificar límites para todas las dimensiones o para ninguna dimensión.</span><span class="sxs-lookup"><span data-stu-id="01ce3-211">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>

```vb
' Declare an array with blank array bounds.
Dim messages() As String
' Initialize the array.
ReDim messages(4)
```

<span data-ttu-id="01ce3-212">Si la matriz tiene más de una dimensión, debe incluir comas entre paréntesis para indicar el número de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="01ce3-212">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>

```vb
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte
```

<span data-ttu-id="01ce3-213">Puede declarar una *matriz de longitud cero* declarando una de las dimensiones de la matriz para que sea-1.</span><span class="sxs-lookup"><span data-stu-id="01ce3-213">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="01ce3-214">Una variable que contiene una matriz de longitud cero no tiene el valor `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="01ce3-214">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="01ce3-215">Ciertas funciones Common Language Runtime requieren matrices de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="01ce3-215">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="01ce3-216">Si intenta obtener acceso a una matriz de este tipo, se produce una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="01ce3-216">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="01ce3-217">Para más información, consulte [Matrices](../../programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-217">For more information, see [Arrays](../../programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="01ce3-218">Puede inicializar los valores de una matriz mediante un literal de matriz.</span><span class="sxs-lookup"><span data-stu-id="01ce3-218">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="01ce3-219">Para ello, incluya los valores de inicialización entre llaves ( `{}` ).</span><span class="sxs-lookup"><span data-stu-id="01ce3-219">To do this, surround the initialization values with braces (`{}`).</span></span>

```vb
Dim longArray() As Long = {0, 1, 2, 3}
```

<span data-ttu-id="01ce3-220">En el caso de las matrices multidimensionales, la inicialización de cada dimensión independiente se incluye entre llaves en la dimensión externa.</span><span class="sxs-lookup"><span data-stu-id="01ce3-220">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="01ce3-221">Los elementos se especifican en orden de fila principal.</span><span class="sxs-lookup"><span data-stu-id="01ce3-221">The elements are specified in row-major order.</span></span>

```vb
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}
```

<span data-ttu-id="01ce3-222">Para obtener más información sobre los literales de matriz, vea [matrices](../../programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-222">For more information about array literals, see [Arrays](../../programming-guide/language-features/arrays/index.md).</span></span>

## <a name="default-data-types-and-values"></a><a name="default"></a> <span data-ttu-id="01ce3-223">Valores y tipos de datos predeterminados</span><span class="sxs-lookup"><span data-stu-id="01ce3-223">Default data types and values</span></span>

<span data-ttu-id="01ce3-224">En la tabla siguiente se describen los resultados de diversas combinaciones resultantes de especificar el tipo de datos y el inicializador en una instrucción `Dim`.</span><span class="sxs-lookup"><span data-stu-id="01ce3-224">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>

|<span data-ttu-id="01ce3-225">¿Tipo de datos especificado?</span><span class="sxs-lookup"><span data-stu-id="01ce3-225">Data type specified?</span></span>|<span data-ttu-id="01ce3-226">¿Inicializador especificado?</span><span class="sxs-lookup"><span data-stu-id="01ce3-226">Initializer specified?</span></span>|<span data-ttu-id="01ce3-227">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01ce3-227">Example</span></span>|<span data-ttu-id="01ce3-228">Resultado</span><span class="sxs-lookup"><span data-stu-id="01ce3-228">Result</span></span>|
|---|---|---|---|
|<span data-ttu-id="01ce3-229">No</span><span class="sxs-lookup"><span data-stu-id="01ce3-229">No</span></span>|<span data-ttu-id="01ce3-230">No</span><span class="sxs-lookup"><span data-stu-id="01ce3-230">No</span></span>|`Dim qty`|<span data-ttu-id="01ce3-231">Si [Option Strict](option-strict-statement.md) está establecido en OFF (valor predeterminado), la variable se establece en `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="01ce3-231">If [Option Strict](option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="01ce3-232">Si `Option Strict` está activado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="01ce3-232">If `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="01ce3-233">No</span><span class="sxs-lookup"><span data-stu-id="01ce3-233">No</span></span>|<span data-ttu-id="01ce3-234">Sí</span><span class="sxs-lookup"><span data-stu-id="01ce3-234">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="01ce3-235">Si [Option Infer](option-infer-statement.md) es on (valor predeterminado), la variable toma el tipo de datos del inicializador.</span><span class="sxs-lookup"><span data-stu-id="01ce3-235">If [Option Infer](option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="01ce3-236">Vea [inferencia de tipo de local](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-236">See [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="01ce3-237">Si `Option Infer` está desactivado y `Option Strict` está desactivado, la variable toma el tipo de datos de `Object`.</span><span class="sxs-lookup"><span data-stu-id="01ce3-237">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="01ce3-238">Si `Option Infer` está desactivado y `Option Strict` está activado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="01ce3-238">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="01ce3-239">Sí</span><span class="sxs-lookup"><span data-stu-id="01ce3-239">Yes</span></span>|<span data-ttu-id="01ce3-240">No</span><span class="sxs-lookup"><span data-stu-id="01ce3-240">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="01ce3-241">La variable se inicializa con el valor predeterminado del tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="01ce3-241">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="01ce3-242">Vea la tabla que aparece más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="01ce3-242">See the table later in this section.</span></span>|
|<span data-ttu-id="01ce3-243">Sí</span><span class="sxs-lookup"><span data-stu-id="01ce3-243">Yes</span></span>|<span data-ttu-id="01ce3-244">Sí</span><span class="sxs-lookup"><span data-stu-id="01ce3-244">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="01ce3-245">Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="01ce3-245">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|

<span data-ttu-id="01ce3-246">Si especifica un tipo de datos pero no especifica un inicializador, Visual Basic inicializa la variable en el valor predeterminado para su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="01ce3-246">If you specify a data type but do not specify an initializer, Visual Basic initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="01ce3-247">En la tabla siguiente se muestran los valores de inicialización predeterminados.</span><span class="sxs-lookup"><span data-stu-id="01ce3-247">The following table shows the default initialization values.</span></span>

|<span data-ttu-id="01ce3-248">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="01ce3-248">Data type</span></span>|<span data-ttu-id="01ce3-249">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="01ce3-249">Default value</span></span>|
|---|---|
|<span data-ttu-id="01ce3-250">Todos los tipos numéricos (incluidos `Byte` y `SByte` )</span><span class="sxs-lookup"><span data-stu-id="01ce3-250">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="01ce3-251">0</span><span class="sxs-lookup"><span data-stu-id="01ce3-251">0</span></span>|
|`Char`|<span data-ttu-id="01ce3-252">Binario 0</span><span class="sxs-lookup"><span data-stu-id="01ce3-252">Binary 0</span></span>|
|<span data-ttu-id="01ce3-253">Todos los tipos de referencia (incluidas `Object` , `String` y todas las matrices)</span><span class="sxs-lookup"><span data-stu-id="01ce3-253">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|
|`Boolean`|`False`|
|`Date`|<span data-ttu-id="01ce3-254">12:00 A.M. del 1 de enero del año 1 (01/01/0001 12:00:00 AM)</span><span class="sxs-lookup"><span data-stu-id="01ce3-254">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|

<span data-ttu-id="01ce3-255">Cada elemento de una estructura se inicializa como si fuera una variable independiente.</span><span class="sxs-lookup"><span data-stu-id="01ce3-255">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="01ce3-256">Si declara la longitud de una matriz pero no inicializa sus elementos, cada elemento se inicializa como si fuera una variable independiente.</span><span class="sxs-lookup"><span data-stu-id="01ce3-256">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>

## <a name="static-local-variable-lifetime"></a><span data-ttu-id="01ce3-257">Duración de la variable local estática</span><span class="sxs-lookup"><span data-stu-id="01ce3-257">Static local variable lifetime</span></span>

<span data-ttu-id="01ce3-258">Una `Static` variable local tiene una duración más larga que la del procedimiento en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="01ce3-258">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="01ce3-259">Los límites de la duración de la variable dependen de dónde se declara el procedimiento y de si es `Shared` .</span><span class="sxs-lookup"><span data-stu-id="01ce3-259">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>

|<span data-ttu-id="01ce3-260">Declaración de procedimiento</span><span class="sxs-lookup"><span data-stu-id="01ce3-260">Procedure declaration</span></span>|<span data-ttu-id="01ce3-261">Variable inicializada</span><span class="sxs-lookup"><span data-stu-id="01ce3-261">Variable initialized</span></span>|<span data-ttu-id="01ce3-262">La variable deja de existir</span><span class="sxs-lookup"><span data-stu-id="01ce3-262">Variable stops existing</span></span>|
|---|---|---|
|<span data-ttu-id="01ce3-263">En un módulo</span><span class="sxs-lookup"><span data-stu-id="01ce3-263">In a module</span></span>|<span data-ttu-id="01ce3-264">La primera vez que se llama al procedimiento</span><span class="sxs-lookup"><span data-stu-id="01ce3-264">The first time the procedure is called</span></span>|<span data-ttu-id="01ce3-265">Cuando el programa detiene la ejecución</span><span class="sxs-lookup"><span data-stu-id="01ce3-265">When your program stops execution</span></span>|
|<span data-ttu-id="01ce3-266">En una clase o estructura, el procedimiento es `Shared`</span><span class="sxs-lookup"><span data-stu-id="01ce3-266">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="01ce3-267">La primera vez que se llama al procedimiento en una instancia específica o en la propia clase o estructura</span><span class="sxs-lookup"><span data-stu-id="01ce3-267">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="01ce3-268">Cuando el programa detiene la ejecución</span><span class="sxs-lookup"><span data-stu-id="01ce3-268">When your program stops execution</span></span>|
|<span data-ttu-id="01ce3-269">En una clase o estructura, el procedimiento no es `Shared`</span><span class="sxs-lookup"><span data-stu-id="01ce3-269">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="01ce3-270">La primera vez que se llama al procedimiento en una instancia específica</span><span class="sxs-lookup"><span data-stu-id="01ce3-270">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="01ce3-271">Cuando se libera la instancia para la recolección de elementos no utilizados (GC)</span><span class="sxs-lookup"><span data-stu-id="01ce3-271">When the instance is released for garbage collection (GC)</span></span>|

## <a name="attributes-and-modifiers"></a><span data-ttu-id="01ce3-272">Atributos y modificadores</span><span class="sxs-lookup"><span data-stu-id="01ce3-272">Attributes and modifiers</span></span>

<span data-ttu-id="01ce3-273">Solo puede aplicar atributos a las variables de miembro, no a las variables locales.</span><span class="sxs-lookup"><span data-stu-id="01ce3-273">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="01ce3-274">Un atributo aporta información a los metadatos del ensamblado, lo que no es significativo para el almacenamiento temporal, como las variables locales.</span><span class="sxs-lookup"><span data-stu-id="01ce3-274">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>

<span data-ttu-id="01ce3-275">En el nivel de módulo, no se puede usar el `Static` modificador para declarar variables de miembro.</span><span class="sxs-lookup"><span data-stu-id="01ce3-275">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="01ce3-276">En el nivel de procedimiento, no puede usar `Shared` , `Shadows` , `ReadOnly` , `WithEvents` o cualquier modificador de acceso para declarar variables locales.</span><span class="sxs-lookup"><span data-stu-id="01ce3-276">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>

<span data-ttu-id="01ce3-277">Puede especificar qué código puede tener acceso a una variable proporcionando `accessmodifier` .</span><span class="sxs-lookup"><span data-stu-id="01ce3-277">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="01ce3-278">Las variables de miembro de clase y módulo (fuera de cualquier procedimiento) tienen como valor predeterminado el acceso privado y las variables miembro de estructura tienen como valor predeterminado el acceso público.</span><span class="sxs-lookup"><span data-stu-id="01ce3-278">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="01ce3-279">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="01ce3-279">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="01ce3-280">No se pueden usar modificadores de acceso en variables locales (dentro de un procedimiento).</span><span class="sxs-lookup"><span data-stu-id="01ce3-280">You cannot use access modifiers on local variables (inside a procedure).</span></span>

<span data-ttu-id="01ce3-281">Solo se puede especificar `WithEvents` en variables de miembro, no en variables locales dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="01ce3-281">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="01ce3-282">Si especifica `WithEvents` , el tipo de datos de la variable debe ser un tipo de clase específico, no `Object` .</span><span class="sxs-lookup"><span data-stu-id="01ce3-282">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="01ce3-283">No se puede declarar una matriz con `WithEvents` .</span><span class="sxs-lookup"><span data-stu-id="01ce3-283">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="01ce3-284">Para obtener más información sobre los eventos, vea [eventos](../../programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="01ce3-284">For more information about events, see [Events](../../programming-guide/language-features/events/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="01ce3-285">El código fuera de una clase, estructura o módulo debe calificar el nombre de una variable miembro con el nombre de esa clase, estructura o módulo.</span><span class="sxs-lookup"><span data-stu-id="01ce3-285">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="01ce3-286">El código fuera de un procedimiento o bloque no puede hacer referencia a ninguna variable local dentro de ese procedimiento o bloque.</span><span class="sxs-lookup"><span data-stu-id="01ce3-286">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>

## <a name="releasing-managed-resources"></a><span data-ttu-id="01ce3-287">Liberar recursos administrados</span><span class="sxs-lookup"><span data-stu-id="01ce3-287">Releasing managed resources</span></span>

<span data-ttu-id="01ce3-288">El recolector de elementos no utilizados de .NET Framework elimina los recursos administrados sin necesidad de codificación adicional por su parte.</span><span class="sxs-lookup"><span data-stu-id="01ce3-288">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="01ce3-289">Sin embargo, puede forzar la eliminación de un recurso administrado en lugar de esperar al recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="01ce3-289">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>

<span data-ttu-id="01ce3-290">Si una clase contiene un recurso especialmente valioso y escaso (como una conexión de base de datos o un identificador de archivo), es posible que no desee esperar hasta la siguiente recolección de elementos no utilizados para limpiar una instancia de clase que ya no está en uso.</span><span class="sxs-lookup"><span data-stu-id="01ce3-290">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="01ce3-291">Una clase puede implementar la <xref:System.IDisposable> interfaz para proporcionar una manera de liberar recursos antes de una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="01ce3-291">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="01ce3-292">Una clase que implementa esa interfaz expone un `Dispose` método al que se puede llamar para obligar a que se liberen recursos valiosos de inmediato.</span><span class="sxs-lookup"><span data-stu-id="01ce3-292">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>

<span data-ttu-id="01ce3-293">La `Using` instrucción automatiza el proceso de adquisición de un recurso, la ejecución de un conjunto de instrucciones y, a continuación, la eliminación del recurso.</span><span class="sxs-lookup"><span data-stu-id="01ce3-293">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="01ce3-294">Sin embargo, el recurso debe implementar la <xref:System.IDisposable> interfaz.</span><span class="sxs-lookup"><span data-stu-id="01ce3-294">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="01ce3-295">Para obtener más información, vea [using (instrucción](using-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="01ce3-295">For more information, see [Using Statement](using-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="01ce3-296">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01ce3-296">Example</span></span>

<span data-ttu-id="01ce3-297">En el siguiente ejemplo se declaran variables mediante la `Dim` instrucción con varias opciones.</span><span class="sxs-lookup"><span data-stu-id="01ce3-297">The following example declares variables by using the `Dim` statement with various options.</span></span>

[!code-vb[VbVbalrStatements#141](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#141)]

## <a name="example"></a><span data-ttu-id="01ce3-298">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01ce3-298">Example</span></span>

<span data-ttu-id="01ce3-299">En el ejemplo siguiente se enumeran los números primos entre 1 y 30.</span><span class="sxs-lookup"><span data-stu-id="01ce3-299">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="01ce3-300">El ámbito de las variables locales se describe en los comentarios de código.</span><span class="sxs-lookup"><span data-stu-id="01ce3-300">The scope of local variables is described in code comments.</span></span>

[!code-vb[VbVbalrStatements#142](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#142)]

## <a name="example"></a><span data-ttu-id="01ce3-301">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01ce3-301">Example</span></span>

<span data-ttu-id="01ce3-302">En el ejemplo siguiente, la `speedValue` variable se declara en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="01ce3-302">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="01ce3-303">La `Private` palabra clave se usa para declarar la variable.</span><span class="sxs-lookup"><span data-stu-id="01ce3-303">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="01ce3-304">Cualquier procedimiento de la clase puede tener acceso a la variable `Car` .</span><span class="sxs-lookup"><span data-stu-id="01ce3-304">The variable can be accessed by any procedure in the `Car` class.</span></span>

[!code-vb[VbVbalrStatements#144](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#144)]

[!code-vb[VbVbalrStatements#145](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class11.vb#145)]

## <a name="see-also"></a><span data-ttu-id="01ce3-305">Vea también</span><span class="sxs-lookup"><span data-stu-id="01ce3-305">See also</span></span>

- [<span data-ttu-id="01ce3-306">Instrucción Const</span><span class="sxs-lookup"><span data-stu-id="01ce3-306">Const Statement</span></span>](const-statement.md)
- [<span data-ttu-id="01ce3-307">Instrucción ReDim</span><span class="sxs-lookup"><span data-stu-id="01ce3-307">ReDim Statement</span></span>](redim-statement.md)
- [<span data-ttu-id="01ce3-308">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01ce3-308">Option Explicit Statement</span></span>](option-explicit-statement.md)
- [<span data-ttu-id="01ce3-309">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01ce3-309">Option Infer Statement</span></span>](option-infer-statement.md)
- [<span data-ttu-id="01ce3-310">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="01ce3-310">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="01ce3-311">Página Compilación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01ce3-311">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [<span data-ttu-id="01ce3-312">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="01ce3-312">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="01ce3-313">Matrices</span><span class="sxs-lookup"><span data-stu-id="01ce3-313">Arrays</span></span>](../../programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="01ce3-314">Inicializadores de objeto: tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="01ce3-314">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="01ce3-315">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="01ce3-315">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="01ce3-316">Inicializadores de objeto: tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="01ce3-316">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="01ce3-317">Procedimiento para declarar un objeto mediante un inicializador de objeto</span><span class="sxs-lookup"><span data-stu-id="01ce3-317">How to: Declare an Object by Using an Object Initializer</span></span>](../../programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
- [<span data-ttu-id="01ce3-318">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="01ce3-318">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
