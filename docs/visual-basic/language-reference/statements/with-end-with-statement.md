---
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
ms.openlocfilehash: 50f3bd0c6e96254274b429794901e2e4ac719ad0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401386"
---
# <a name="withend-with-statement-visual-basic"></a><span data-ttu-id="34d23-102">With...End With (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34d23-102">With...End With Statement (Visual Basic)</span></span>

<span data-ttu-id="34d23-103">Ejecuta una serie de instrucciones que hacen referencia repetidamente a un único objeto o estructura, por lo que las instrucciones pueden utilizar una sintaxis simplificada al acceder a los miembros del objeto o estructura.</span><span class="sxs-lookup"><span data-stu-id="34d23-103">Executes a series of statements that repeatedly refer to a single object or structure so that the statements can use a simplified syntax when accessing members of the object or structure.</span></span>  <span data-ttu-id="34d23-104">Cuando use una estructura, sola podrá leer los valores de los miembros o invocar métodos, y recibirá un error si intenta asignar valores a los miembros de una estructura utilizada en una instrucción `With...End With`.</span><span class="sxs-lookup"><span data-stu-id="34d23-104">When using a structure, you can only read the values of members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>

## <a name="syntax"></a><span data-ttu-id="34d23-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34d23-105">Syntax</span></span>

```vb
With objectExpression
    [ statements ]
End With
```

## <a name="parts"></a><span data-ttu-id="34d23-106">Partes</span><span class="sxs-lookup"><span data-stu-id="34d23-106">Parts</span></span>

|<span data-ttu-id="34d23-107">Término</span><span class="sxs-lookup"><span data-stu-id="34d23-107">Term</span></span>|<span data-ttu-id="34d23-108">Definición</span><span class="sxs-lookup"><span data-stu-id="34d23-108">Definition</span></span>|
|---|---|
|`objectExpression`|<span data-ttu-id="34d23-109">Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="34d23-109">Required.</span></span> <span data-ttu-id="34d23-110">Una expresión que se evalúa como un objeto.</span><span class="sxs-lookup"><span data-stu-id="34d23-110">An expression that evaluates to an object.</span></span> <span data-ttu-id="34d23-111">La expresión puede ser arbitrariamente compleja y se evalúa solo una vez.</span><span class="sxs-lookup"><span data-stu-id="34d23-111">The expression may be arbitrarily complex and is evaluated only once.</span></span> <span data-ttu-id="34d23-112">La expresión se puede evaluar como cualquier tipo de datos, incluidos los tipos elementales.</span><span class="sxs-lookup"><span data-stu-id="34d23-112">The expression can evaluate to any data type, including elementary types.</span></span>|
|`statements`|<span data-ttu-id="34d23-113">Opcional.</span><span class="sxs-lookup"><span data-stu-id="34d23-113">Optional.</span></span> <span data-ttu-id="34d23-114">Una o varias instrucciones entre `With` y `End With` que pueden hacer referencia a los miembros de un objeto generado por la evaluación de `objectExpression`.</span><span class="sxs-lookup"><span data-stu-id="34d23-114">One or more statements between `With` and `End With` that may refer to members of an object that's produced by the evaluation of `objectExpression`.</span></span>|
|`End With`|<span data-ttu-id="34d23-115">Necesario.</span><span class="sxs-lookup"><span data-stu-id="34d23-115">Required.</span></span> <span data-ttu-id="34d23-116">Termina la definición del bloque `With`.</span><span class="sxs-lookup"><span data-stu-id="34d23-116">Terminates the definition of the `With` block.</span></span>|

## <a name="remarks"></a><span data-ttu-id="34d23-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="34d23-117">Remarks</span></span>

<span data-ttu-id="34d23-118">Con `With...End With`, puede ejecutar una serie de instrucciones en un objeto especificado sin necesidad especificar el nombre del objeto varias veces.</span><span class="sxs-lookup"><span data-stu-id="34d23-118">By using `With...End With`, you can perform a series of statements on a specified object without specifying the name of the object multiple times.</span></span> <span data-ttu-id="34d23-119">En un bloque de instrucciones `With`, puede especificar un miembro del objeto que comience por un punto, como si el objeto de la instrucción `With` lo precediera.</span><span class="sxs-lookup"><span data-stu-id="34d23-119">Within a `With` statement block, you can specify a member of the object starting with a period, as if the `With` statement object preceded it.</span></span>

<span data-ttu-id="34d23-120">Por ejemplo, para cambiar varias propiedades de un único objeto, coloque las instrucciones de asignación de las propiedades dentro del bloque `With...End With` y haga referencia al objeto una vez, en lugar de hacerlo en cada una de las asignaciones de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="34d23-120">For example, to change multiple properties on a single object, place the property assignment statements inside the `With...End With` block, referring to the object only once instead of once for each property assignment.</span></span>

<span data-ttu-id="34d23-121">Si el código tiene acceso al mismo objeto en varias instrucciones, la instrucción `With` le brinda las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="34d23-121">If your code accesses the same object in multiple statements, you gain the following benefits by using the `With` statement:</span></span>

- <span data-ttu-id="34d23-122">No es necesario evaluar varias veces una expresión compleja ni asignar el resultado a una variable temporal para hacer referencia a sus miembros varias veces.</span><span class="sxs-lookup"><span data-stu-id="34d23-122">You don't need to evaluate a complex expression multiple times or assign the result to a temporary variable to refer to its members multiple times.</span></span>

- <span data-ttu-id="34d23-123">El código resulta más legible al eliminar expresiones de calificación repetitivas.</span><span class="sxs-lookup"><span data-stu-id="34d23-123">You make your code more readable by eliminating repetitive qualifying expressions.</span></span>

<span data-ttu-id="34d23-124">El tipo de datos de `objectExpression` puede ser cualquier tipo de clase o estructura, o incluso un tipo elemental de Visual Basic, como `Integer`.</span><span class="sxs-lookup"><span data-stu-id="34d23-124">The data type of `objectExpression` can be any class or structure type or even a Visual Basic elementary type such as `Integer`.</span></span>  <span data-ttu-id="34d23-125">Si `objectExpression` produce un valor que no es un objeto, solo podrá leer los valores de sus miembros o invocar métodos, y recibirá un error si intenta asignar valores a los miembros de una estructura utilizada en una instrucción `With...End With`.</span><span class="sxs-lookup"><span data-stu-id="34d23-125">If `objectExpression` results in anything other than an object, you can only read the values of its members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>  <span data-ttu-id="34d23-126">Este es el mismo error que obtendría si invocara un método que devolviera una estructura y accediera inmediatamente a un miembro del resultado de la función, como `GetAPoint().x = 1`, y le asignara un valor.</span><span class="sxs-lookup"><span data-stu-id="34d23-126">This is the same error you would get if you invoked a method that returned a structure and immediately accessed and assigned a value to a member of the function’s result, such as `GetAPoint().x = 1`.</span></span>  <span data-ttu-id="34d23-127">El problema en ambos casos es que la estructura solo existe en la pila de llamadas y no hay forma de que un miembro de la estructura modificada en estas situaciones pueda escribir en una ubicación de forma que cualquier otro código del programa pueda observar el cambio.</span><span class="sxs-lookup"><span data-stu-id="34d23-127">The problem in both cases is that the structure exists only on the call stack, and there is no way a modified structure member in these situations can write to  a location such that any other code in the program can observe the change.</span></span>

<span data-ttu-id="34d23-128">`objectExpression` se evalúa una vez, tras su entrada en el bloque.</span><span class="sxs-lookup"><span data-stu-id="34d23-128">The `objectExpression` is evaluated once, upon entry into the block.</span></span> <span data-ttu-id="34d23-129">No se puede reasignar `objectExpression` desde el interior del bloque `With`.</span><span class="sxs-lookup"><span data-stu-id="34d23-129">You can't reassign the `objectExpression` from within the `With` block.</span></span>

<span data-ttu-id="34d23-130">En un bloque `With`, solo de puede acceder a los métodos y propiedades del objeto especificado sin calificarlos.</span><span class="sxs-lookup"><span data-stu-id="34d23-130">Within a `With` block, you can access the methods and properties of only the specified object without qualifying them.</span></span> <span data-ttu-id="34d23-131">Se pueden usar métodos y propiedades de otros objetos, pero es necesario calificarlos con los nombres de objeto.</span><span class="sxs-lookup"><span data-stu-id="34d23-131">You can use methods and properties of other objects, but you must qualify them with their object names.</span></span>

<span data-ttu-id="34d23-132">Puede incluir una instrucción `With...End With` dentro de otra.</span><span class="sxs-lookup"><span data-stu-id="34d23-132">You can place one `With...End With` statement within another.</span></span> <span data-ttu-id="34d23-133">Las instrucciones `With...End With` anidadas pueden resultar confusas si los objetos a los que se hace referencia no están claros por el contexto.</span><span class="sxs-lookup"><span data-stu-id="34d23-133">Nested `With...End With` statements may be confusing if the objects that are being referred to aren't clear from context.</span></span> <span data-ttu-id="34d23-134">Debe proporcionar una referencia completa a un objeto que esté en un bloque `With` externo cuando se haga referencia al objeto desde dentro de un bloque `With` interno.</span><span class="sxs-lookup"><span data-stu-id="34d23-134">You must provide a fully qualified reference to an object that's in an outer `With` block when the object is referenced from within an inner `With` block.</span></span>

<span data-ttu-id="34d23-135">No se pueden crear bifurcaciones en un bloque de instrucciones `With` desde fuera del bloque.</span><span class="sxs-lookup"><span data-stu-id="34d23-135">You can't branch into a `With` statement block from outside the block.</span></span>

<span data-ttu-id="34d23-136">A menos que el bloque contenga un bucle, las instrucciones se ejecutan una sola vez.</span><span class="sxs-lookup"><span data-stu-id="34d23-136">Unless the block contains a loop, the statements run only once.</span></span> <span data-ttu-id="34d23-137">Puede anidar diferentes tipos de estructuras de control.</span><span class="sxs-lookup"><span data-stu-id="34d23-137">You can nest different kinds of control structures.</span></span> <span data-ttu-id="34d23-138">Para obtener más información, vea [estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span><span class="sxs-lookup"><span data-stu-id="34d23-138">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

> [!NOTE]
> <span data-ttu-id="34d23-139">La palabra clave `With` también se puede usar en inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="34d23-139">You can use the `With` keyword in object initializers also.</span></span> <span data-ttu-id="34d23-140">Para obtener más información y ejemplos, vea [inicializadores de objeto: tipos con nombre y anónimos](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) y [tipos anónimos](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="34d23-140">For more information and examples, see [Object Initializers: Named and Anonymous Types](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) and [Anonymous Types](../../programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>
>
> <span data-ttu-id="34d23-141">Si usa un bloque `With` solo para inicializar las propiedades o campos de un objeto del que acaba de crear instancias, considere la posibilidad de utilizar en su lugar un inicializador de objetos.</span><span class="sxs-lookup"><span data-stu-id="34d23-141">If you're using a `With` block only to initialize the properties or fields of an object that you've just instantiated, consider using an object initializer instead.</span></span>

## <a name="example"></a><span data-ttu-id="34d23-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34d23-142">Example</span></span>

<span data-ttu-id="34d23-143">En el ejemplo siguiente, cada bloque `With` ejecuta una serie de instrucciones en un único objeto.</span><span class="sxs-lookup"><span data-stu-id="34d23-143">In the following example, each `With` block executes a series of statements on a single object.</span></span>

[!code-vb[VbVbalrWithStatement#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#2)]

## <a name="example"></a><span data-ttu-id="34d23-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34d23-144">Example</span></span>

<span data-ttu-id="34d23-145">En el ejemplo siguiente se anidan las instrucciones `With…End With`.</span><span class="sxs-lookup"><span data-stu-id="34d23-145">The following example nests `With…End With` statements.</span></span> <span data-ttu-id="34d23-146">En la instrucción `With` anidada, la sintaxis hace referencia al objeto interno.</span><span class="sxs-lookup"><span data-stu-id="34d23-146">Within the nested `With` statement, the syntax refers to the inner object.</span></span>

[!code-vb[VbVbalrWithStatement#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="34d23-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34d23-147">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="34d23-148">Estructuras de control anidadas</span><span class="sxs-lookup"><span data-stu-id="34d23-148">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="34d23-149">Inicializadores de objeto: tipos con nombre y anónimos</span><span class="sxs-lookup"><span data-stu-id="34d23-149">Object Initializers: Named and Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="34d23-150">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="34d23-150">Anonymous Types</span></span>](../../programming-guide/language-features/objects-and-classes/anonymous-types.md)
