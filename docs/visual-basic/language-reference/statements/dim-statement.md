---
title: "Instrucción Dim (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "72"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a428f8be7b62600ca8fffd3160039c1de911e34e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="dim-statement-visual-basic"></a><span data-ttu-id="8c708-102">Instrucción Dim (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c708-102">Dim Statement (Visual Basic)</span></span>
<span data-ttu-id="8c708-103">Declara y asigna espacio de almacenamiento para una o más variables.</span><span class="sxs-lookup"><span data-stu-id="8c708-103">Declares and allocates storage space for one or more variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c708-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c708-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] [[ Shared ] [ Shadows ] | [ Static ]] [ ReadOnly ]   
Dim [ WithEvents ] variablelist  
```  
  
## <a name="parts"></a><span data-ttu-id="8c708-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="8c708-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="8c708-106">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8c708-106">Optional.</span></span> <span data-ttu-id="8c708-107">Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="8c708-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8c708-108">Optional.</span></span> <span data-ttu-id="8c708-109">Puede ser uno de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="8c708-109">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="8c708-110">Public</span><span class="sxs-lookup"><span data-stu-id="8c708-110">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="8c708-111">Protected</span><span class="sxs-lookup"><span data-stu-id="8c708-111">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="8c708-112">Friend</span><span class="sxs-lookup"><span data-stu-id="8c708-112">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="8c708-113">Private</span><span class="sxs-lookup"><span data-stu-id="8c708-113">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="8c708-114">Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-114">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `Shared`  
  
     <span data-ttu-id="8c708-115">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8c708-115">Optional.</span></span> <span data-ttu-id="8c708-116">Vea [compartido](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-116">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="8c708-117">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8c708-117">Optional.</span></span> <span data-ttu-id="8c708-118">Vea [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-118">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `Static`  
  
     <span data-ttu-id="8c708-119">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8c708-119">Optional.</span></span> <span data-ttu-id="8c708-120">Vea [estático](../../../visual-basic/language-reference/modifiers/static.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-120">See [Static](../../../visual-basic/language-reference/modifiers/static.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="8c708-121">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8c708-121">Optional.</span></span> <span data-ttu-id="8c708-122">Vea [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-122">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WithEvents`  
  
     <span data-ttu-id="8c708-123">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8c708-123">Optional.</span></span> <span data-ttu-id="8c708-124">Especifica que se trata de variables de objeto que hacen referencia a instancias de una clase que puede provocar eventos.</span><span class="sxs-lookup"><span data-stu-id="8c708-124">Specifies that these are object variables that refer to instances of a class that can raise events.</span></span> <span data-ttu-id="8c708-125">Vea [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-125">See [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md).</span></span>  
  
-   `variablelist`  
  
     <span data-ttu-id="8c708-126">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8c708-126">Required.</span></span> <span data-ttu-id="8c708-127">Lista de variables que se declaran en esta instrucción.</span><span class="sxs-lookup"><span data-stu-id="8c708-127">List of variables being declared in this statement.</span></span>  
  
     `variable [ , variable ... ]`  
  
     <span data-ttu-id="8c708-128">Cada `variable` tiene la sintaxis y las partes siguientes:</span><span class="sxs-lookup"><span data-stu-id="8c708-128">Each `variable` has the following syntax and parts:</span></span>  
  
     <span data-ttu-id="8c708-129">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span><span class="sxs-lookup"><span data-stu-id="8c708-129">`variablename [ ( [ boundslist ] ) ] [ As [ New ] datatype [ With`{`[ .propertyname = propinitializer [ , ... ] ] } ] ] [ = initializer ]`</span></span>  
  
    |<span data-ttu-id="8c708-130">Parte</span><span class="sxs-lookup"><span data-stu-id="8c708-130">Part</span></span>|<span data-ttu-id="8c708-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c708-131">Description</span></span>|  
    |---|---|  
    |`variablename`|<span data-ttu-id="8c708-132">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="8c708-132">Required.</span></span> <span data-ttu-id="8c708-133">Nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="8c708-133">Name of the variable.</span></span> <span data-ttu-id="8c708-134">Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-134">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>|  
    |`boundslist`|<span data-ttu-id="8c708-135">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8c708-135">Optional.</span></span> <span data-ttu-id="8c708-136">Lista de límites de cada dimensión de una variable de matriz.</span><span class="sxs-lookup"><span data-stu-id="8c708-136">List of bounds of each dimension of an array variable.</span></span>|  
    |`New`|<span data-ttu-id="8c708-137">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8c708-137">Optional.</span></span> <span data-ttu-id="8c708-138">Crea una nueva instancia de la clase cuando la `Dim` instrucción se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="8c708-138">Creates a new instance of the class when the `Dim` statement runs.</span></span>|  
    |`datatype`|<span data-ttu-id="8c708-139">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8c708-139">Optional.</span></span> <span data-ttu-id="8c708-140">Tipo de datos de la variable.</span><span class="sxs-lookup"><span data-stu-id="8c708-140">Data type of the variable.</span></span>|  
    |`With`|<span data-ttu-id="8c708-141">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8c708-141">Optional.</span></span> <span data-ttu-id="8c708-142">Presenta la lista de inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="8c708-142">Introduces the object initializer list.</span></span>|  
    |`propertyname`|<span data-ttu-id="8c708-143">Opcional.</span><span class="sxs-lookup"><span data-stu-id="8c708-143">Optional.</span></span> <span data-ttu-id="8c708-144">El nombre de una propiedad en la clase que se está realizando una instancia de.</span><span class="sxs-lookup"><span data-stu-id="8c708-144">The name of a property in the class you are making an instance of.</span></span>|  
    |`propinitializer`|<span data-ttu-id="8c708-145">Necesario después `propertyname` =.</span><span class="sxs-lookup"><span data-stu-id="8c708-145">Required after `propertyname` =.</span></span> <span data-ttu-id="8c708-146">La expresión que se evalúa y se asigna al nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="8c708-146">The expression that is evaluated and assigned to the property name.</span></span>|  
    |`initializer`|<span data-ttu-id="8c708-147">Opcional si `New` no se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="8c708-147">Optional if `New` is not specified.</span></span> <span data-ttu-id="8c708-148">Expresión que se evalúa y se asigna a la variable cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="8c708-148">Expression that is evaluated and assigned to the variable when it is created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c708-149">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c708-149">Remarks</span></span>  
 <span data-ttu-id="8c708-150">El compilador de Visual Basic utiliza la `Dim` instrucción para determinar el tipo de datos de la variable y otra información, como qué código puede tener acceso a la variable.</span><span class="sxs-lookup"><span data-stu-id="8c708-150">The Visual Basic compiler uses the `Dim` statement to determine the variable's data type and other information, such as what code can access the variable.</span></span> <span data-ttu-id="8c708-151">En el ejemplo siguiente se declara una variable que contenga una `Integer` valor.</span><span class="sxs-lookup"><span data-stu-id="8c708-151">The following example declares a variable to hold an `Integer` value.</span></span>  
  
```vb  
Dim numberOfStudents As Integer  
```  
  
 <span data-ttu-id="8c708-152">Puede especificar cualquier tipo de datos o el nombre de una estructura, clase, interfaz o enumeración.</span><span class="sxs-lookup"><span data-stu-id="8c708-152">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
```vb  
Dim finished As Boolean  
Dim monitorBox As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="8c708-153">Para un tipo de referencia, utilice el `New` palabra clave para crear una nueva instancia de la clase o estructura que se especifica por el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="8c708-153">For a reference type, you use the `New` keyword to create a new instance of the class or structure that is specified by the data type.</span></span> <span data-ttu-id="8c708-154">Si utiliza `New`, no utiliza una expresión de inicializador.</span><span class="sxs-lookup"><span data-stu-id="8c708-154">If you use `New`, you do not use an initializer expression.</span></span> <span data-ttu-id="8c708-155">En su lugar, que proporcione los argumentos, si es necesarios, al constructor de la clase desde el que está creando la variable.</span><span class="sxs-lookup"><span data-stu-id="8c708-155">Instead, you supply arguments, if they are required, to the constructor of the class from which you are creating the variable.</span></span>  
  
```vb  
Dim bottomLabel As New System.Windows.Forms.Label  
```  
  
 <span data-ttu-id="8c708-156">Puede declarar una variable en una clase, estructura, procedimiento, bloque o módulo.</span><span class="sxs-lookup"><span data-stu-id="8c708-156">You can declare a variable in a procedure, block, class, structure, or module.</span></span> <span data-ttu-id="8c708-157">No se puede declarar una variable en un archivo de código fuente, el espacio de nombres o la interfaz.</span><span class="sxs-lookup"><span data-stu-id="8c708-157">You cannot declare a variable in a source file, namespace, or interface.</span></span> <span data-ttu-id="8c708-158">Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).</span><span class="sxs-lookup"><span data-stu-id="8c708-158">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="8c708-159">Una variable que se declara en el nivel de módulo, fuera de cualquier procedimiento, es un *variable miembro* o *campo*.</span><span class="sxs-lookup"><span data-stu-id="8c708-159">A variable that is declared at module level, outside any procedure, is a *member variable* or *field*.</span></span> <span data-ttu-id="8c708-160">Las variables de miembro están en ámbito a lo largo de su clase, estructura o módulo.</span><span class="sxs-lookup"><span data-stu-id="8c708-160">Member variables are in scope throughout their class, structure, or module.</span></span> <span data-ttu-id="8c708-161">Una variable que se declara en el nivel de procedimiento es un *variable local*.</span><span class="sxs-lookup"><span data-stu-id="8c708-161">A variable that is declared at procedure level is a *local variable*.</span></span> <span data-ttu-id="8c708-162">Las variables locales están en ámbito solo dentro de su procedimiento o bloque.</span><span class="sxs-lookup"><span data-stu-id="8c708-162">Local variables are in scope only within their procedure or block.</span></span>  
  
 <span data-ttu-id="8c708-163">Los modificadores de acceso siguientes se usan para declarar variables fuera de un procedimiento: `Public`, `Protected`, `Friend`, `Protected Friend`, y `Private`.</span><span class="sxs-lookup"><span data-stu-id="8c708-163">The following access modifiers are used to declare variables outside a procedure: `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private`.</span></span> <span data-ttu-id="8c708-164">Para obtener más información, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-164">For more information, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="8c708-165">El `Dim` palabra clave es opcional y normalmente se omite si se especifica cualquiera de los siguientes modificadores: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, o `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="8c708-165">The `Dim` keyword is optional and usually omitted if you specify any of the following modifiers: `Public`, `Protected`, `Friend`, `Protected Friend`, `Private`, `Shared`, `Shadows`, `Static`, `ReadOnly`, or `WithEvents`.</span></span>  
  
```vb  
Public maximumAllowed As Double  
Protected Friend currentUserName As String  
Private salary As Decimal  
Static runningTotal As Integer  
```  
  
 <span data-ttu-id="8c708-166">Si `Option Explicit` es on (valor predeterminado), el compilador requiere una declaración para cada variable que se utiliza.</span><span class="sxs-lookup"><span data-stu-id="8c708-166">If `Option Explicit` is on (the default), the compiler requires a declaration for every variable you use.</span></span> <span data-ttu-id="8c708-167">Para obtener más información, consulte [instrucción Option Explicit](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-167">For more information, see [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md).</span></span>  
  
## <a name="specifying-an-initial-value"></a><span data-ttu-id="8c708-168">Especificar un valor inicial</span><span class="sxs-lookup"><span data-stu-id="8c708-168">Specifying an Initial Value</span></span>  
 <span data-ttu-id="8c708-169">Puede asignar un valor a una variable cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="8c708-169">You can assign a value to a variable when it is created.</span></span> <span data-ttu-id="8c708-170">Para un tipo de valor, utilice un *inicializador* para proporcionar una expresión que se asignará a la variable.</span><span class="sxs-lookup"><span data-stu-id="8c708-170">For a value type, you use an *initializer* to supply an expression to be assigned to the variable.</span></span> <span data-ttu-id="8c708-171">La expresión debe evaluarse como una constante que se puede calcular en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="8c708-171">The expression must evaluate to a constant that can be calculated at compile time.</span></span>  
  
```vb  
Dim quantity As Integer = 10  
Dim message As String = "Just started"  
```  
  
 <span data-ttu-id="8c708-172">Si se especifica un inicializador y no se especifica un tipo de datos en un `As` cláusula, *inferencia de tipo* se usa para inferir el tipo de datos desde el inicializador.</span><span class="sxs-lookup"><span data-stu-id="8c708-172">If an initializer is specified and a data type is not specified in an `As` clause, *type inference* is used to infer the data type from the initializer.</span></span> <span data-ttu-id="8c708-173">En el ejemplo siguiente, ambos `num1` y `num2` están fuertemente tipados como enteros.</span><span class="sxs-lookup"><span data-stu-id="8c708-173">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span> <span data-ttu-id="8c708-174">En la segunda declaración, inferencia de tipo deduce el tipo del valor 3.</span><span class="sxs-lookup"><span data-stu-id="8c708-174">In the second declaration, type inference infers the type from the value 3.</span></span>  
  
```vb  
' Use explicit typing.  
Dim num1 As Integer = 3  
  
' Use local type inference.  
Dim num2 = 3  
```  
  
 <span data-ttu-id="8c708-175">Inferencia de tipo se aplica en el nivel de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8c708-175">Type inference applies at the procedure level.</span></span> <span data-ttu-id="8c708-176">No se aplica fuera de un procedimiento en una clase, estructura, módulo o interfaz.</span><span class="sxs-lookup"><span data-stu-id="8c708-176">It does not apply outside a procedure in a class, structure, module, or interface.</span></span> <span data-ttu-id="8c708-177">Para obtener más información acerca de la inferencia de tipo, consulte [Option Infer instrucción](../../../visual-basic/language-reference/statements/option-infer-statement.md) y [inferencia de tipo Local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-177">For more information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="8c708-178">Para obtener información sobre lo que ocurre cuando no se especifica un tipo de datos o un inicializador, consulte [valores y tipos de datos predeterminados](../../../visual-basic/language-reference/statements/dim-statement.md#default) más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="8c708-178">For information about what happens when a data type or initializer is not specified, see [Default Data Types and Values](../../../visual-basic/language-reference/statements/dim-statement.md#default) later in this topic.</span></span>  
  
 <span data-ttu-id="8c708-179">Puede usar un *inicializador de objeto* para declarar instancias de tipos con nombre y anónimos.</span><span class="sxs-lookup"><span data-stu-id="8c708-179">You can use an *object initializer* to declare instances of named and anonymous types.</span></span> <span data-ttu-id="8c708-180">El código siguiente crea una instancia de un `Student` clase y usa un inicializador de objeto para inicializar las propiedades.</span><span class="sxs-lookup"><span data-stu-id="8c708-180">The following code creates an instance of a `Student` class and uses an object initializer to initialize properties.</span></span>  
  
```vb  
Dim student1 As New Student With {.First = "Michael",   
                                  .Last = "Tucker"}  
```  
  
 <span data-ttu-id="8c708-181">Para obtener más información sobre los inicializadores de objeto, vea [Cómo: declarar un objeto usando un inicializador de objeto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [inicializadores de objeto: tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), y [tipos anónimos ](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-181">For more information about object initializers, see [How to: Declare an Object by Using an Object Initializer](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md), [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md), and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="declaring-multiple-variables"></a><span data-ttu-id="8c708-182">Declarar varias Variables</span><span class="sxs-lookup"><span data-stu-id="8c708-182">Declaring Multiple Variables</span></span>  
 <span data-ttu-id="8c708-183">Puede declarar varias variables en una instrucción de declaración, especificando el nombre de variable para cada uno de ellos y después de cada nombre de matriz con paréntesis.</span><span class="sxs-lookup"><span data-stu-id="8c708-183">You can declare several variables in one declaration statement, specifying the variable name for each one, and following each array name with parentheses.</span></span> <span data-ttu-id="8c708-184">Las variables se separan con comas.</span><span class="sxs-lookup"><span data-stu-id="8c708-184">Multiple variables are separated by commas.</span></span>  
  
```vb  
Dim lastTime, nextTime, allTimes() As Date  
```  
  
 <span data-ttu-id="8c708-185">Si se declara más de una variable con una `As` cláusula, no puede proporcionar un inicializador para el grupo de variables.</span><span class="sxs-lookup"><span data-stu-id="8c708-185">If you declare more than one variable with one `As` clause, you cannot supply an initializer for that group of variables.</span></span>  
  
 <span data-ttu-id="8c708-186">Puede especificar los tipos de datos diferentes para distintas variables mediante otro `As` cláusula para cada variable que se declara.</span><span class="sxs-lookup"><span data-stu-id="8c708-186">You can specify different data types for different variables by using a separate `As` clause for each variable you declare.</span></span> <span data-ttu-id="8c708-187">Cada variable toma el tipo de datos especificado en la primera `As` cláusula encontró después de su `variablename` parte.</span><span class="sxs-lookup"><span data-stu-id="8c708-187">Each variable takes the data type specified in the first `As` clause encountered after its `variablename` part.</span></span>  
  
```vb  
Dim a, b, c As Single, x, y As Double, i As Integer  
' a, b, and c are all Single; x and y are both Double  
```  
  
## <a name="arrays"></a><span data-ttu-id="8c708-188">Matrices</span><span class="sxs-lookup"><span data-stu-id="8c708-188">Arrays</span></span>  
 <span data-ttu-id="8c708-189">Puede declarar una variable que contenga una *matriz*, que puede contener varios valores.</span><span class="sxs-lookup"><span data-stu-id="8c708-189">You can declare a variable to hold an *array*, which can hold multiple values.</span></span> <span data-ttu-id="8c708-190">Para especificar que una variable contiene una matriz, siga su `variablename` inmediatamente con paréntesis.</span><span class="sxs-lookup"><span data-stu-id="8c708-190">To specify that a variable holds an array, follow its `variablename` immediately with parentheses.</span></span> <span data-ttu-id="8c708-191">Para obtener más información acerca de las matrices, vea [matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-191">For more information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="8c708-192">Puede especificar los límites inferior y superior de cada dimensión de una matriz.</span><span class="sxs-lookup"><span data-stu-id="8c708-192">You can specify the lower and upper bound of each dimension of an array.</span></span> <span data-ttu-id="8c708-193">Para hacerlo, incluya un `boundslist` dentro de los paréntesis.</span><span class="sxs-lookup"><span data-stu-id="8c708-193">To do this, include a `boundslist` inside the parentheses.</span></span> <span data-ttu-id="8c708-194">Para cada dimensión, el `boundslist` especifica el límite superior y, opcionalmente, el límite inferior.</span><span class="sxs-lookup"><span data-stu-id="8c708-194">For each dimension, the `boundslist` specifies the upper bound and optionally the lower bound.</span></span> <span data-ttu-id="8c708-195">El límite inferior es siempre cero, si se especifica o no.</span><span class="sxs-lookup"><span data-stu-id="8c708-195">The lower bound is always zero, whether you specify it or not.</span></span> <span data-ttu-id="8c708-196">Cada índice puede variar de cero a su valor de límite superior.</span><span class="sxs-lookup"><span data-stu-id="8c708-196">Each index can vary from zero through its upper bound value.</span></span>  
  
 <span data-ttu-id="8c708-197">Las dos instrucciones siguientes son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="8c708-197">The following two statements are equivalent.</span></span> <span data-ttu-id="8c708-198">Cada instrucción declara una matriz de 21 `Integer` elementos.</span><span class="sxs-lookup"><span data-stu-id="8c708-198">Each statement declares an array of 21 `Integer` elements.</span></span> <span data-ttu-id="8c708-199">Cuando tiene acceso a la matriz, el índice puede variar entre 0 y 20.</span><span class="sxs-lookup"><span data-stu-id="8c708-199">When you access the array, the index can vary from 0 through 20.</span></span>  
  
```vb  
Dim totals(20) As Integer  
Dim totals(0 To 20) As Integer  
```  
  
 <span data-ttu-id="8c708-200">La siguiente instrucción declara una matriz bidimensional de tipo `Double`.</span><span class="sxs-lookup"><span data-stu-id="8c708-200">The following statement declares a two-dimensional array of type `Double`.</span></span> <span data-ttu-id="8c708-201">La matriz tiene 4 filas (3 + 1) de 6 columnas (5 + 1) cada una.</span><span class="sxs-lookup"><span data-stu-id="8c708-201">The array has 4 rows (3 + 1) of 6 columns (5 + 1) each.</span></span> <span data-ttu-id="8c708-202">Tenga en cuenta que un límite superior representa el mayor valor posible para el índice, no la longitud de la dimensión.</span><span class="sxs-lookup"><span data-stu-id="8c708-202">Note that an upper bound represents the highest possible value for the index, not the length of the dimension.</span></span> <span data-ttu-id="8c708-203">La longitud de la dimensión es el límite superior más uno.</span><span class="sxs-lookup"><span data-stu-id="8c708-203">The length of the dimension is the upper bound plus one.</span></span>  
  
```vb  
Dim matrix2(3, 5) As Double  
```  
  
 <span data-ttu-id="8c708-204">Una matriz puede tener de 1 a 32 dimensiones.</span><span class="sxs-lookup"><span data-stu-id="8c708-204">An array can have from 1 to 32 dimensions.</span></span>  
  
 <span data-ttu-id="8c708-205">Puede dejar en blanco en una declaración de matriz de todos los límites.</span><span class="sxs-lookup"><span data-stu-id="8c708-205">You can leave all the bounds blank in an array declaration.</span></span> <span data-ttu-id="8c708-206">Si lo hace, la matriz tiene el número de dimensiones especificadas, pero no está inicializado.</span><span class="sxs-lookup"><span data-stu-id="8c708-206">If you do this, the array has the number of dimensions you specify, but it is uninitialized.</span></span> <span data-ttu-id="8c708-207">Tiene un valor de `Nothing` hasta que se inicialicen al menos algunos de sus elementos.</span><span class="sxs-lookup"><span data-stu-id="8c708-207">It has a value of `Nothing` until you initialize at least some of its elements.</span></span> <span data-ttu-id="8c708-208">El `Dim` instrucción debe especificar límites para todas las dimensiones o para ninguna dimensión.</span><span class="sxs-lookup"><span data-stu-id="8c708-208">The `Dim` statement must specify bounds either for all dimensions or for no dimensions.</span></span>  
  
```vb  
' Declare an array with blank array bounds.  
Dim messages() As String  
' Initialize the array.  
ReDim messages(4)  
```  
  
 <span data-ttu-id="8c708-209">Si la matriz tiene más de una dimensión, debe incluir comas entre paréntesis para indicar el número de dimensiones.</span><span class="sxs-lookup"><span data-stu-id="8c708-209">If the array has more than one dimension, you must include commas between the parentheses to indicate the number of dimensions.</span></span>  
  
```vb  
Dim oneDimension(), twoDimensions(,), threeDimensions(,,) As Byte  
```  
  
 <span data-ttu-id="8c708-210">Puede declarar un *matriz de longitud cero* declarando una de las dimensiones de la matriz sea -1.</span><span class="sxs-lookup"><span data-stu-id="8c708-210">You can declare a *zero-length array* by declaring one of the array's dimensions to be -1.</span></span> <span data-ttu-id="8c708-211">Una variable que contiene una matriz de longitud cero no tiene el valor `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="8c708-211">A variable that holds a zero-length array does not have the value `Nothing`.</span></span> <span data-ttu-id="8c708-212">Matrices de longitud cero son necesarios para determinadas funciones de common language runtime.</span><span class="sxs-lookup"><span data-stu-id="8c708-212">Zero-length arrays are required by certain common language runtime functions.</span></span> <span data-ttu-id="8c708-213">Si intenta tener acceso a dicha matriz, se produce una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8c708-213">If you try to access such an array, a runtime exception occurs.</span></span> <span data-ttu-id="8c708-214">Para obtener más información, consulte [matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-214">For more information, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="8c708-215">Puede inicializar los valores de una matriz mediante un literal de matriz.</span><span class="sxs-lookup"><span data-stu-id="8c708-215">You can initialize the values of an array by using an array literal.</span></span> <span data-ttu-id="8c708-216">Para ello, incluya los valores de inicialización con llaves (`{}`).</span><span class="sxs-lookup"><span data-stu-id="8c708-216">To do this, surround the initialization values with braces (`{}`).</span></span>  
  
```vb  
Dim longArray() As Long = {0, 1, 2, 3}  
```  
  
 <span data-ttu-id="8c708-217">Para las matrices multidimensionales, la inicialización de cada dimensión se encierra entre llaves en la dimensión exterior.</span><span class="sxs-lookup"><span data-stu-id="8c708-217">For multidimensional arrays, the initialization for each separate dimension is enclosed in braces in the outer dimension.</span></span> <span data-ttu-id="8c708-218">Los elementos se especifican en orden de importancia de filas.</span><span class="sxs-lookup"><span data-stu-id="8c708-218">The elements are specified in row-major order.</span></span>  
  
```vb  
Dim twoDimensions(,) As Integer = {{0, 1, 2}, {10, 11, 12}}  
```  
  
 <span data-ttu-id="8c708-219">Para obtener más información sobre los literales de matriz, vea [matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-219">For more information about array literals, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
##  <span data-ttu-id="8c708-220"><a name="default"></a>Tipos de datos predeterminados y valores</span><span class="sxs-lookup"><span data-stu-id="8c708-220"><a name="default"></a> Default Data Types and Values</span></span>  
 <span data-ttu-id="8c708-221">En la tabla siguiente se describen los resultados de diversas combinaciones resultantes de especificar el tipo de datos y el inicializador en una instrucción `Dim`.</span><span class="sxs-lookup"><span data-stu-id="8c708-221">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="8c708-222">¿Tipo de datos especificado?</span><span class="sxs-lookup"><span data-stu-id="8c708-222">Data type specified?</span></span>|<span data-ttu-id="8c708-223">¿Inicializador especificado?</span><span class="sxs-lookup"><span data-stu-id="8c708-223">Initializer specified?</span></span>|<span data-ttu-id="8c708-224">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c708-224">Example</span></span>|<span data-ttu-id="8c708-225">Resultado</span><span class="sxs-lookup"><span data-stu-id="8c708-225">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="8c708-226">No</span><span class="sxs-lookup"><span data-stu-id="8c708-226">No</span></span>|<span data-ttu-id="8c708-227">No</span><span class="sxs-lookup"><span data-stu-id="8c708-227">No</span></span>|`Dim qty`|<span data-ttu-id="8c708-228">Si [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) es off (valor predeterminado), la variable se establece en `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="8c708-228">If [Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="8c708-229">Si `Option Strict` está activado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="8c708-229">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="8c708-230">No</span><span class="sxs-lookup"><span data-stu-id="8c708-230">No</span></span>|<span data-ttu-id="8c708-231">Sí</span><span class="sxs-lookup"><span data-stu-id="8c708-231">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="8c708-232">Si [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) es on (valor predeterminado), escriba la variable toma los datos del inicializador.</span><span class="sxs-lookup"><span data-stu-id="8c708-232">If [Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="8c708-233">Vea [inferencia de tipo Local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-233">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="8c708-234">Si `Option Infer` está desactivado y `Option Strict` está desactivado, la variable toma el tipo de datos de `Object`.</span><span class="sxs-lookup"><span data-stu-id="8c708-234">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="8c708-235">Si `Option Infer` está desactivado y `Option Strict` está activado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="8c708-235">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="8c708-236">Sí</span><span class="sxs-lookup"><span data-stu-id="8c708-236">Yes</span></span>|<span data-ttu-id="8c708-237">No</span><span class="sxs-lookup"><span data-stu-id="8c708-237">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="8c708-238">La variable se inicializa con el valor predeterminado del tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="8c708-238">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="8c708-239">Vea la tabla más adelante en esta sección.</span><span class="sxs-lookup"><span data-stu-id="8c708-239">See the table later in this section.</span></span>|  
|<span data-ttu-id="8c708-240">Sí</span><span class="sxs-lookup"><span data-stu-id="8c708-240">Yes</span></span>|<span data-ttu-id="8c708-241">Sí</span><span class="sxs-lookup"><span data-stu-id="8c708-241">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="8c708-242">Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="8c708-242">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
 <span data-ttu-id="8c708-243">Si especifica un tipo de datos pero no especifica un inicializador, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] inicializa la variable en el valor predeterminado para su tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="8c708-243">If you specify a data type but do not specify an initializer, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] initializes the variable to the default value for its data type.</span></span> <span data-ttu-id="8c708-244">En la tabla siguiente muestra el valor predeterminado de los valores de inicialización.</span><span class="sxs-lookup"><span data-stu-id="8c708-244">The following table shows the default initialization values.</span></span>  
  
|<span data-ttu-id="8c708-245">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="8c708-245">Data type</span></span>|<span data-ttu-id="8c708-246">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="8c708-246">Default value</span></span>|  
|---|---|  
|<span data-ttu-id="8c708-247">Todos los tipos numéricos (incluidos `Byte` y `SByte`)</span><span class="sxs-lookup"><span data-stu-id="8c708-247">All numeric types (including `Byte` and `SByte`)</span></span>|<span data-ttu-id="8c708-248">0</span><span class="sxs-lookup"><span data-stu-id="8c708-248">0</span></span>|  
|`Char`|<span data-ttu-id="8c708-249">0 binario</span><span class="sxs-lookup"><span data-stu-id="8c708-249">Binary 0</span></span>|  
|<span data-ttu-id="8c708-250">Todos los tipos de referencia (incluidos `Object`, `String`y todas las matrices)</span><span class="sxs-lookup"><span data-stu-id="8c708-250">All reference types (including `Object`, `String`, and all arrays)</span></span>|`Nothing`|  
|`Boolean`|`False`|  
|`Date`|<span data-ttu-id="8c708-251">12:00 A.M. del 1 de enero del año 1 (01/01/0001 12:00:00 A.M.)</span><span class="sxs-lookup"><span data-stu-id="8c708-251">12:00 AM of January 1 of the year 1 (01/01/0001 12:00:00 AM)</span></span>|  
  
 <span data-ttu-id="8c708-252">Cada elemento de una estructura se inicializa como si fuera una variable independiente.</span><span class="sxs-lookup"><span data-stu-id="8c708-252">Each element of a structure is initialized as if it were a separate variable.</span></span> <span data-ttu-id="8c708-253">Si se declara la longitud de una matriz pero no se inicializan sus elementos, cada elemento se inicializa como si fuera una variable independiente.</span><span class="sxs-lookup"><span data-stu-id="8c708-253">If you declare the length of an array but do not initialize its elements, each element is initialized as if it were a separate variable.</span></span>  
  
## <a name="static-local-variable-lifetime"></a><span data-ttu-id="8c708-254">Duración de la Variable Local estática</span><span class="sxs-lookup"><span data-stu-id="8c708-254">Static Local Variable Lifetime</span></span>  
 <span data-ttu-id="8c708-255">Un `Static` variable local tiene una duración más larga que el procedimiento en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="8c708-255">A `Static` local variable has a longer lifetime than that of the procedure in which it is declared.</span></span> <span data-ttu-id="8c708-256">Dependen de los límites de duración de la variable donde se declara el procedimiento y si es `Shared`.</span><span class="sxs-lookup"><span data-stu-id="8c708-256">The boundaries of the variable's lifetime depend on where the procedure is declared and whether it is `Shared`.</span></span>  
  
|<span data-ttu-id="8c708-257">Declaración de procedimiento</span><span class="sxs-lookup"><span data-stu-id="8c708-257">Procedure declaration</span></span>|<span data-ttu-id="8c708-258">Variable inicializada</span><span class="sxs-lookup"><span data-stu-id="8c708-258">Variable initialized</span></span>|<span data-ttu-id="8c708-259">Detiene la variable existente</span><span class="sxs-lookup"><span data-stu-id="8c708-259">Variable stops existing</span></span>|  
|---|---|---|  
|<span data-ttu-id="8c708-260">En un módulo</span><span class="sxs-lookup"><span data-stu-id="8c708-260">In a module</span></span>|<span data-ttu-id="8c708-261">La primera vez que se llama al procedimiento</span><span class="sxs-lookup"><span data-stu-id="8c708-261">The first time the procedure is called</span></span>|<span data-ttu-id="8c708-262">Cuando detiene la ejecución del programa</span><span class="sxs-lookup"><span data-stu-id="8c708-262">When your program stops execution</span></span>|  
|<span data-ttu-id="8c708-263">En una clase o estructura, el procedimiento es`Shared`</span><span class="sxs-lookup"><span data-stu-id="8c708-263">In a class or structure, procedure is `Shared`</span></span>|<span data-ttu-id="8c708-264">La primera vez que se llama al procedimiento en una instancia específica o en la propia clase o estructura</span><span class="sxs-lookup"><span data-stu-id="8c708-264">The first time the procedure is called either on a specific instance or on the class or structure itself</span></span>|<span data-ttu-id="8c708-265">Cuando detiene la ejecución del programa</span><span class="sxs-lookup"><span data-stu-id="8c708-265">When your program stops execution</span></span>|  
|<span data-ttu-id="8c708-266">En una clase o estructura, no es el procedimiento`Shared`</span><span class="sxs-lookup"><span data-stu-id="8c708-266">In a class or structure, procedure isn't `Shared`</span></span>|<span data-ttu-id="8c708-267">La primera vez que se llama al procedimiento en una instancia específica</span><span class="sxs-lookup"><span data-stu-id="8c708-267">The first time the procedure is called on a specific instance</span></span>|<span data-ttu-id="8c708-268">Cuando se libera la instancia para la recopilación de elementos no utilizados (GC)</span><span class="sxs-lookup"><span data-stu-id="8c708-268">When the instance is released for garbage collection (GC)</span></span>|  
  
## <a name="attributes-and-modifiers"></a><span data-ttu-id="8c708-269">Los atributos y modificadores</span><span class="sxs-lookup"><span data-stu-id="8c708-269">Attributes and Modifiers</span></span>  
 <span data-ttu-id="8c708-270">Puede aplicar atributos solo a variables de miembro, no a las variables locales.</span><span class="sxs-lookup"><span data-stu-id="8c708-270">You can apply attributes only to member variables, not to local variables.</span></span> <span data-ttu-id="8c708-271">Un atributo proporciona información a los metadatos del ensamblado, que no son significativos para el almacenamiento temporal como las variables locales.</span><span class="sxs-lookup"><span data-stu-id="8c708-271">An attribute contributes information to the assembly's metadata, which is not meaningful for temporary storage such as local variables.</span></span>  
  
 <span data-ttu-id="8c708-272">En el nivel de módulo, no puede usar el `Static` modificador para declarar las variables de miembro.</span><span class="sxs-lookup"><span data-stu-id="8c708-272">At module level, you cannot use the `Static` modifier to declare member variables.</span></span> <span data-ttu-id="8c708-273">En el nivel de procedimiento, no puede usar `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, o cualquier acceso modificadores para declarar variables locales.</span><span class="sxs-lookup"><span data-stu-id="8c708-273">At procedure level, you cannot use `Shared`, `Shadows`, `ReadOnly`, `WithEvents`, or any access modifiers to declare local variables.</span></span>  
  
 <span data-ttu-id="8c708-274">Puede especificar qué código puede tener acceso a una variable proporcionando un `accessmodifier`.</span><span class="sxs-lookup"><span data-stu-id="8c708-274">You can specify what code can access a variable by supplying an `accessmodifier`.</span></span> <span data-ttu-id="8c708-275">Clase y módulo predeterminado de variables (fuera de cualquier procedimiento) miembro a acceso privado y predeterminada de las variables de miembro de estructura para acceso público.</span><span class="sxs-lookup"><span data-stu-id="8c708-275">Class and module member variables (outside any procedure) default to private access, and structure member variables default to public access.</span></span> <span data-ttu-id="8c708-276">Los niveles de acceso se pueden ajustar con los modificadores de acceso.</span><span class="sxs-lookup"><span data-stu-id="8c708-276">You can adjust their access levels with the access modifiers.</span></span> <span data-ttu-id="8c708-277">No puede usar los modificadores de acceso en variables locales (dentro de un procedimiento).</span><span class="sxs-lookup"><span data-stu-id="8c708-277">You cannot use access modifiers on local variables (inside a procedure).</span></span>  
  
 <span data-ttu-id="8c708-278">Puede especificar `WithEvents` solo en variables de miembro, no en variables locales dentro de un procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8c708-278">You can specify `WithEvents` only on member variables, not on local variables inside a procedure.</span></span> <span data-ttu-id="8c708-279">Si especifica `WithEvents`, el tipo de datos de la variable debe ser un tipo de clase concreto, no `Object`.</span><span class="sxs-lookup"><span data-stu-id="8c708-279">If you specify `WithEvents`, the data type of the variable must be a specific class type, not `Object`.</span></span> <span data-ttu-id="8c708-280">No se puede declarar una matriz con `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="8c708-280">You cannot declare an array with `WithEvents`.</span></span> <span data-ttu-id="8c708-281">Para obtener más información acerca de los eventos, vea [eventos](../../../visual-basic/programming-guide/language-features/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-281">For more information about events, see [Events](../../../visual-basic/programming-guide/language-features/events/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c708-282">Código fuera de una clase, estructura o módulo debe calificar el nombre de la variable de miembro con el nombre de esa clase, estructura o módulo.</span><span class="sxs-lookup"><span data-stu-id="8c708-282">Code outside a class, structure, or module must qualify a member variable's name with the name of that class, structure, or module.</span></span> <span data-ttu-id="8c708-283">El código fuera de que un procedimiento o bloque no puede hacer referencia a cualquier variable local dentro de ese procedimiento o bloque.</span><span class="sxs-lookup"><span data-stu-id="8c708-283">Code outside a procedure or block cannot refer to any local variables within that procedure or block.</span></span>  
  
## <a name="releasing-managed-resources"></a><span data-ttu-id="8c708-284">Liberar los recursos administrados</span><span class="sxs-lookup"><span data-stu-id="8c708-284">Releasing Managed Resources</span></span>  
 <span data-ttu-id="8c708-285">El recolector de elementos no utilizados de .NET Framework se deshace de los recursos administrados sin necesidad de código adicional por su parte.</span><span class="sxs-lookup"><span data-stu-id="8c708-285">The .NET Framework garbage collector disposes of managed resources without any extra coding on your part.</span></span> <span data-ttu-id="8c708-286">Sin embargo, puede forzar la eliminación de un recurso administrado en lugar de esperar el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8c708-286">However, you can force the disposal of a managed resource instead of waiting for the garbage collector.</span></span>  
  
 <span data-ttu-id="8c708-287">Si una clase se bloquea en un recurso especialmente valioso y escaso (por ejemplo, un identificador de conexión o el archivo de base de datos), no puede esperar hasta la siguiente recolección para limpiar una instancia de clase que ya no está en uso.</span><span class="sxs-lookup"><span data-stu-id="8c708-287">If a class holds onto a particularly valuable and scarce resource (such as a database connection or file handle), you might not want to wait until the next garbage collection to clean up a class instance that's no longer in use.</span></span> <span data-ttu-id="8c708-288">Una clase puede implementar la <xref:System.IDisposable> interfaz para proporcionar una manera para liberar los recursos antes de una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8c708-288">A class may implement the <xref:System.IDisposable> interface to provide a way to release resources before a garbage collection.</span></span> <span data-ttu-id="8c708-289">Una clase que implementa esa interfaz expone un `Dispose` método que se puede llamar para forzar valiosos recursos se libera inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="8c708-289">A class that implements that interface exposes a `Dispose` method that can be called to force valuable resources to be released immediately.</span></span>  
  
 <span data-ttu-id="8c708-290">El `Using` instrucción automatiza el proceso de adquisición de un recurso, ejecutar un conjunto de instrucciones y, a continuación, elimine el recurso.</span><span class="sxs-lookup"><span data-stu-id="8c708-290">The `Using` statement automates the process of acquiring a resource, executing a set of statements, and then disposing of the resource.</span></span> <span data-ttu-id="8c708-291">Sin embargo, debe implementar el recurso de la <xref:System.IDisposable> interfaz.</span><span class="sxs-lookup"><span data-stu-id="8c708-291">However, the resource must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="8c708-292">Para obtener más información, vea [Using (Instrucción)](../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8c708-292">For more information, see [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c708-293">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c708-293">Example</span></span>  
 <span data-ttu-id="8c708-294">En el ejemplo siguiente se declara variables mediante el `Dim` instrucción con varias opciones.</span><span class="sxs-lookup"><span data-stu-id="8c708-294">The following example declares variables by using the `Dim` statement with various options.</span></span>  
  
 [!code-vb[VbVbalrStatements#141](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="8c708-295">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c708-295">Example</span></span>  
 <span data-ttu-id="8c708-296">En el ejemplo siguiente se enumeran los números primos entre 1 y 30.</span><span class="sxs-lookup"><span data-stu-id="8c708-296">The following example lists the prime numbers between 1 and 30.</span></span> <span data-ttu-id="8c708-297">El ámbito de las variables locales se describe en los comentarios del código.</span><span class="sxs-lookup"><span data-stu-id="8c708-297">The scope of local variables is described in code comments.</span></span>  
  
 [!code-vb[VbVbalrStatements#142](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="8c708-298">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8c708-298">Example</span></span>  
 <span data-ttu-id="8c708-299">En el ejemplo siguiente, la `speedValue` variable se declara en el nivel de clase.</span><span class="sxs-lookup"><span data-stu-id="8c708-299">In the following example, the `speedValue` variable is declared at the class level.</span></span> <span data-ttu-id="8c708-300">El `Private` palabra clave se utiliza para declarar la variable.</span><span class="sxs-lookup"><span data-stu-id="8c708-300">The `Private` keyword is used to declare the variable.</span></span> <span data-ttu-id="8c708-301">La variable puede tener acceso a todos los procedimientos en el `Car` clase.</span><span class="sxs-lookup"><span data-stu-id="8c708-301">The variable can be accessed by any procedure in the `Car` class.</span></span>  
  
 [!code-vb[VbVbalrStatements#144](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_3.vb)]  
  
 [!code-vb[VbVbalrStatements#145](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/dim-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8c708-302">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c708-302">See Also</span></span>  
 [<span data-ttu-id="8c708-303">Const (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8c708-303">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="8c708-304">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8c708-304">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="8c708-305">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8c708-305">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="8c708-306">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8c708-306">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="8c708-307">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8c708-307">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="8c708-308">Página Compilación, Diseñador de proyectos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c708-308">Compile Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)  
 [<span data-ttu-id="8c708-309">Declaración de variables</span><span class="sxs-lookup"><span data-stu-id="8c708-309">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="8c708-310">Matrices</span><span class="sxs-lookup"><span data-stu-id="8c708-310">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="8c708-311">Inicializadores de objeto: Tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="8c708-311">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="8c708-312">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="8c708-312">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [<span data-ttu-id="8c708-313">Inicializadores de objeto: Tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="8c708-313">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="8c708-314">Declarar un objeto usando un inicializador de objeto</span><span class="sxs-lookup"><span data-stu-id="8c708-314">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)  
 [<span data-ttu-id="8c708-315">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="8c708-315">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
