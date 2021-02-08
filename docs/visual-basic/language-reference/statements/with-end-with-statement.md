---
description: 'Más información sobre: con... End with (instrucción Visual Basic)'
title: Instrucción With...End With
ms.date: 07/20/2015
f1_keywords:
- vb.With
helpviewer_keywords:
- With keyword [Visual Basic]
- loop structures [Visual Basic], and With...End With statements
- execution [Visual Basic], on object
- instructions, repeating
- With...End With statements [Visual Basic]
- With statement [Visual Basic]
- With statement [Visual Basic], nesting
- objects [Visual Basic], accessing
- With block
- End keyword [Visual Basic], With...End With statements
ms.assetid: 340d5fbb-4f43-48ec-a024-80843c137817
ms.openlocfilehash: 86393d5dee7a03b2b8396b34b31326d1b0ea3c28
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787570"
---
# <a name="withend-with-statement-visual-basic"></a><span data-ttu-id="70688-103">With...End With (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70688-103">With...End With Statement (Visual Basic)</span></span>

<span data-ttu-id="70688-104">Ejecuta una serie de instrucciones que hacen referencia repetidamente a un único objeto o estructura, por lo que las instrucciones pueden utilizar una sintaxis simplificada al acceder a los miembros del objeto o estructura.</span><span class="sxs-lookup"><span data-stu-id="70688-104">Executes a series of statements that repeatedly refer to a single object or structure so that the statements can use a simplified syntax when accessing members of the object or structure.</span></span>  <span data-ttu-id="70688-105">Cuando use una estructura, sola podrá leer los valores de los miembros o invocar métodos, y recibirá un error si intenta asignar valores a los miembros de una estructura utilizada en una instrucción `With...End With`.</span><span class="sxs-lookup"><span data-stu-id="70688-105">When using a structure, you can only read the values of members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>

## <a name="syntax"></a><span data-ttu-id="70688-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70688-106">Syntax</span></span>

```vb
With objectExpression
    [ statements ]
End With
```

## <a name="parts"></a><span data-ttu-id="70688-107">Partes</span><span class="sxs-lookup"><span data-stu-id="70688-107">Parts</span></span>

|<span data-ttu-id="70688-108">Término</span><span class="sxs-lookup"><span data-stu-id="70688-108">Term</span></span>|<span data-ttu-id="70688-109">Definición</span><span class="sxs-lookup"><span data-stu-id="70688-109">Definition</span></span>|
|---|---|
|`objectExpression`|<span data-ttu-id="70688-110">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="70688-110">Required.</span></span> <span data-ttu-id="70688-111">Una expresión que se evalúa como un objeto.</span><span class="sxs-lookup"><span data-stu-id="70688-111">An expression that evaluates to an object.</span></span> <span data-ttu-id="70688-112">La expresión puede ser arbitrariamente compleja y se evalúa solo una vez.</span><span class="sxs-lookup"><span data-stu-id="70688-112">The expression may be arbitrarily complex and is evaluated only once.</span></span> <span data-ttu-id="70688-113">La expresión se puede evaluar como cualquier tipo de datos, incluidos los tipos elementales.</span><span class="sxs-lookup"><span data-stu-id="70688-113">The expression can evaluate to any data type, including elementary types.</span></span>|
|`statements`|<span data-ttu-id="70688-114">Opcional.</span><span class="sxs-lookup"><span data-stu-id="70688-114">Optional.</span></span> <span data-ttu-id="70688-115">Una o varias instrucciones entre `With` y `End With` que pueden hacer referencia a los miembros de un objeto generado por la evaluación de `objectExpression`.</span><span class="sxs-lookup"><span data-stu-id="70688-115">One or more statements between `With` and `End With` that may refer to members of an object that's produced by the evaluation of `objectExpression`.</span></span>|
|`End With`|<span data-ttu-id="70688-116">Necesario.</span><span class="sxs-lookup"><span data-stu-id="70688-116">Required.</span></span> <span data-ttu-id="70688-117">Termina la definición del bloque `With`.</span><span class="sxs-lookup"><span data-stu-id="70688-117">Terminates the definition of the `With` block.</span></span>|

## <a name="remarks"></a><span data-ttu-id="70688-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="70688-118">Remarks</span></span>

<span data-ttu-id="70688-119">Con `With...End With`, puede ejecutar una serie de instrucciones en un objeto especificado sin necesidad especificar el nombre del objeto varias veces.</span><span class="sxs-lookup"><span data-stu-id="70688-119">By using `With...End With`, you can perform a series of statements on a specified object without specifying the name of the object multiple times.</span></span> <span data-ttu-id="70688-120">En un bloque de instrucciones `With`, puede especificar un miembro del objeto que comience por un punto, como si el objeto de la instrucción `With` lo precediera.</span><span class="sxs-lookup"><span data-stu-id="70688-120">Within a `With` statement block, you can specify a member of the object starting with a period, as if the `With` statement object preceded it.</span></span>

<span data-ttu-id="70688-121">Por ejemplo, para cambiar varias propiedades de un único objeto, coloque las instrucciones de asignación de las propiedades dentro del bloque `With...End With` y haga referencia al objeto una vez, en lugar de hacerlo en cada una de las asignaciones de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="70688-121">For example, to change multiple properties on a single object, place the property assignment statements inside the `With...End With` block, referring to the object only once instead of once for each property assignment.</span></span>

<span data-ttu-id="70688-122">Si el código tiene acceso al mismo objeto en varias instrucciones, la instrucción `With` le brinda las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="70688-122">If your code accesses the same object in multiple statements, you gain the following benefits by using the `With` statement:</span></span>

- <span data-ttu-id="70688-123">No es necesario evaluar varias veces una expresión compleja ni asignar el resultado a una variable temporal para hacer referencia a sus miembros varias veces.</span><span class="sxs-lookup"><span data-stu-id="70688-123">You don't need to evaluate a complex expression multiple times or assign the result to a temporary variable to refer to its members multiple times.</span></span>

- <span data-ttu-id="70688-124">El código resulta más legible al eliminar expresiones de calificación repetitivas.</span><span class="sxs-lookup"><span data-stu-id="70688-124">You make your code more readable by eliminating repetitive qualifying expressions.</span></span>

<span data-ttu-id="70688-125">El tipo de datos de `objectExpression` puede ser cualquier tipo de clase o estructura, o incluso un tipo elemental de Visual Basic, como `Integer`.</span><span class="sxs-lookup"><span data-stu-id="70688-125">The data type of `objectExpression` can be any class or structure type or even a Visual Basic elementary type such as `Integer`.</span></span>  <span data-ttu-id="70688-126">Si `objectExpression` produce un valor que no es un objeto, solo podrá leer los valores de sus miembros o invocar métodos, y recibirá un error si intenta asignar valores a los miembros de una estructura utilizada en una instrucción `With...End With`.</span><span class="sxs-lookup"><span data-stu-id="70688-126">If `objectExpression` results in anything other than an object, you can only read the values of its members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>  <span data-ttu-id="70688-127">Este es el mismo error que obtendría si invocara un método que devolviera una estructura y accediera inmediatamente a un miembro del resultado de la función, como `GetAPoint().x = 1`, y le asignara un valor.</span><span class="sxs-lookup"><span data-stu-id="70688-127">This is the same error you would get if you invoked a method that returned a structure and immediately accessed and assigned a value to a member of the function’s result, such as `GetAPoint().x = 1`.</span></span>  <span data-ttu-id="70688-128">El problema en ambos casos es que la estructura solo existe en la pila de llamadas y no hay forma de que un miembro de la estructura modificada en estas situaciones pueda escribir en una ubicación de forma que cualquier otro código del programa pueda observar el cambio.</span><span class="sxs-lookup"><span data-stu-id="70688-128">The problem in both cases is that the structure exists only on the call stack, and there is no way a modified structure member in these situations can write to  a location such that any other code in the program can observe the change.</span></span>

<span data-ttu-id="70688-129">`objectExpression` se evalúa una vez, tras su entrada en el bloque.</span><span class="sxs-lookup"><span data-stu-id="70688-129">The `objectExpression` is evaluated once, upon entry into the block.</span></span> <span data-ttu-id="70688-130">No se puede reasignar `objectExpression` desde el interior del bloque `With`.</span><span class="sxs-lookup"><span data-stu-id="70688-130">You can't reassign the `objectExpression` from within the `With` block.</span></span>

<span data-ttu-id="70688-131">En un bloque `With`, solo de puede acceder a los métodos y propiedades del objeto especificado sin calificarlos.</span><span class="sxs-lookup"><span data-stu-id="70688-131">Within a `With` block, you can access the methods and properties of only the specified object without qualifying them.</span></span> <span data-ttu-id="70688-132">Se pueden usar métodos y propiedades de otros objetos, pero es necesario calificarlos con los nombres de objeto.</span><span class="sxs-lookup"><span data-stu-id="70688-132">You can use methods and properties of other objects, but you must qualify them with their object names.</span></span>

<span data-ttu-id="70688-133">Puede incluir una instrucción `With...End With` dentro de otra.</span><span class="sxs-lookup"><span data-stu-id="70688-133">You can place one `With...End With` statement within another.</span></span> <span data-ttu-id="70688-134">Las instrucciones `With...End With` anidadas pueden resultar confusas si los objetos a los que se hace referencia no están claros por el contexto.</span><span class="sxs-lookup"><span data-stu-id="70688-134">Nested `With...End With` statements may be confusing if the objects that are being referred to aren't clear from context.</span></span> <span data-ttu-id="70688-135">Debe proporcionar una referencia completa a un objeto que esté en un bloque `With` externo cuando se haga referencia al objeto desde dentro de un bloque `With` interno.</span><span class="sxs-lookup"><span data-stu-id="70688-135">You must provide a fully qualified reference to an object that's in an outer `With` block when the object is referenced from within an inner `With` block.</span></span>

<span data-ttu-id="70688-136">No se pueden crear bifurcaciones en un bloque de instrucciones `With` desde fuera del bloque.</span><span class="sxs-lookup"><span data-stu-id="70688-136">You can't branch into a `With` statement block from outside the block.</span></span>

<span data-ttu-id="70688-137">A menos que el bloque contenga un bucle, las instrucciones se ejecutan una sola vez.</span><span class="sxs-lookup"><span data-stu-id="70688-137">Unless the block contains a loop, the statements run only once.</span></span> <span data-ttu-id="70688-138">Puede anidar diferentes tipos de estructuras de control.</span><span class="sxs-lookup"><span data-stu-id="70688-138">You can nest different kinds of control structures.</span></span> <span data-ttu-id="70688-139">Para obtener más información, vea [estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="70688-139">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

> [!NOTE]
> <span data-ttu-id="70688-140">La palabra clave `With` también se puede usar en inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="70688-140">You can use the `With` keyword in object initializers also.</span></span> <span data-ttu-id="70688-141">Para obtener más información y ejemplos, vea [inicializadores de objeto: tipos con nombre y anónimos](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) y [tipos anónimos](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="70688-141">For more information and examples, see [Object Initializers: Named and Anonymous Types](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) and [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>
>
> <span data-ttu-id="70688-142">Si usa un bloque `With` solo para inicializar las propiedades o campos de un objeto del que acaba de crear instancias, considere la posibilidad de utilizar en su lugar un inicializador de objetos.</span><span class="sxs-lookup"><span data-stu-id="70688-142">If you're using a `With` block only to initialize the properties or fields of an object that you've just instantiated, consider using an object initializer instead.</span></span>

## <a name="example"></a><span data-ttu-id="70688-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="70688-143">Example</span></span>

<span data-ttu-id="70688-144">En el ejemplo siguiente, cada bloque `With` ejecuta una serie de instrucciones en un único objeto.</span><span class="sxs-lookup"><span data-stu-id="70688-144">In the following example, each `With` block executes a series of statements on a single object.</span></span>

[!code-vb[VbVbalrWithStatement#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#2)]

## <a name="example"></a><span data-ttu-id="70688-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="70688-145">Example</span></span>

<span data-ttu-id="70688-146">En el ejemplo siguiente se anidan las instrucciones `With…End With`.</span><span class="sxs-lookup"><span data-stu-id="70688-146">The following example nests `With…End With` statements.</span></span> <span data-ttu-id="70688-147">En la instrucción `With` anidada, la sintaxis hace referencia al objeto interno.</span><span class="sxs-lookup"><span data-stu-id="70688-147">Within the nested `With` statement, the syntax refers to the inner object.</span></span>

[!code-vb[VbVbalrWithStatement#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="70688-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="70688-148">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="70688-149">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="70688-149">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="70688-150">Inicializadores de objeto: tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="70688-150">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="70688-151">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="70688-151">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
