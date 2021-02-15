---
description: 'Más información sobre: inferencia de tipo de local (Visual Basic)'
title: Inferencia de tipo de variable local
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: 50be8544229360287d2aef27f31360d7140640ac
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481706"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="157e3-103">Inferencia de tipo de variable local (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="157e3-103">Local Type Inference (Visual Basic)</span></span>

<span data-ttu-id="157e3-104">El compilador Visual Basic usa la *inferencia de tipos* para determinar los tipos de datos de las variables locales declaradas sin una `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="157e3-104">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="157e3-105">El compilador deduce el tipo de la variable a partir del tipo de la expresión de inicialización.</span><span class="sxs-lookup"><span data-stu-id="157e3-105">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="157e3-106">Esto le permite declarar variables sin indicar explícitamente un tipo, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="157e3-106">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="157e3-107">Como resultado de las declaraciones, `num1` y `num2` están fuertemente tipadas como enteros.</span><span class="sxs-lookup"><span data-stu-id="157e3-107">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="157e3-108">Si no desea que `num2` en el ejemplo anterior se escriba como `Integer` , puede especificar otro tipo mediante una declaración como `Dim num3 As Object = 3` o `Dim num4 As Double = 3` .</span><span class="sxs-lookup"><span data-stu-id="157e3-108">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>

> [!NOTE]
> <span data-ttu-id="157e3-109">La inferencia de tipos solo se puede usar para variables locales no estáticas; no se puede usar para determinar el tipo de campos de clase, propiedades o funciones.</span><span class="sxs-lookup"><span data-stu-id="157e3-109">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>

<span data-ttu-id="157e3-110">La inferencia de tipo local se aplica en el nivel de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="157e3-110">Local type inference applies at procedure level.</span></span> <span data-ttu-id="157e3-111">No se puede usar para declarar variables en el nivel de módulo (dentro de una clase, una estructura, un módulo o una interfaz, pero no dentro de un procedimiento o un bloque).</span><span class="sxs-lookup"><span data-stu-id="157e3-111">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="157e3-112">Si `num2` en el ejemplo anterior se tratara de un campo de una clase en lugar de una variable local en un procedimiento, la declaración produciría un error con `Option Strict` en y clasificaría `num2` como un `Object` con `Option Strict` OFF.</span><span class="sxs-lookup"><span data-stu-id="157e3-112">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="157e3-113">Del mismo modo, la inferencia de tipo local no se aplica a las variables de nivel de procedimiento declaradas como `Static` .</span><span class="sxs-lookup"><span data-stu-id="157e3-113">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>

## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="157e3-114">Inferencia de tipos frente a enlace en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="157e3-114">Type Inference vs. Late Binding</span></span>

<span data-ttu-id="157e3-115">El código que usa la inferencia de tipos es similar al código que se basa en el enlace en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="157e3-115">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="157e3-116">Sin embargo, la inferencia de tipos fuertemente tipa la variable en lugar de pasarla como `Object` .</span><span class="sxs-lookup"><span data-stu-id="157e3-116">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="157e3-117">El compilador usa un inicializador de variable para determinar el tipo de la variable en tiempo de compilación para generar código enlazado en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="157e3-117">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="157e3-118">En el ejemplo anterior, `num2` , como `num1` , se escribe como `Integer` .</span><span class="sxs-lookup"><span data-stu-id="157e3-118">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>

<span data-ttu-id="157e3-119">El comportamiento de las variables enlazadas en tiempo de compilación difiere del de las variables enlazadas en tiempo de ejecución, para las que solo se conoce el tipo en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="157e3-119">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="157e3-120">Conocer el tipo pronto permite al compilador identificar problemas antes de la ejecución, asignar la memoria con precisión y realizar otras optimizaciones.</span><span class="sxs-lookup"><span data-stu-id="157e3-120">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="157e3-121">El enlace temprano también habilita el Visual Basic entorno de desarrollo integrado (IDE) para proporcionar ayuda de IntelliSense acerca de los miembros de un objeto.</span><span class="sxs-lookup"><span data-stu-id="157e3-121">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="157e3-122">El enlace en tiempo de compilación también es preferible para el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="157e3-122">Early binding is also preferred for performance.</span></span> <span data-ttu-id="157e3-123">Esto se debe a que todos los datos almacenados en una variable enlazada en tiempo de ejecución deben ajustarse como de tipo `Object` y obtener acceso a los miembros del tipo en tiempo de ejecución hace que el programa sea más lento.</span><span class="sxs-lookup"><span data-stu-id="157e3-123">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>

## <a name="examples"></a><span data-ttu-id="157e3-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="157e3-124">Examples</span></span>

<span data-ttu-id="157e3-125">La inferencia de tipos se produce cuando se declara una variable local sin una `As` cláusula y se inicializa.</span><span class="sxs-lookup"><span data-stu-id="157e3-125">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="157e3-126">El compilador usa el tipo del valor inicial asignado como el tipo de la variable.</span><span class="sxs-lookup"><span data-stu-id="157e3-126">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="157e3-127">Por ejemplo, cada una de las siguientes líneas de código declara una variable de tipo `String` .</span><span class="sxs-lookup"><span data-stu-id="157e3-127">For example, each of the following lines of code declares a variable of type `String`.</span></span>

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

<span data-ttu-id="157e3-128">En el código siguiente se muestran dos formas equivalentes de crear una matriz de enteros.</span><span class="sxs-lookup"><span data-stu-id="157e3-128">The following code demonstrates two equivalent ways to create an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

<span data-ttu-id="157e3-129">Es conveniente usar la inferencia de tipos para determinar el tipo de una variable de control de bucle.</span><span class="sxs-lookup"><span data-stu-id="157e3-129">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="157e3-130">En el código siguiente, el compilador deduce que `number` es una `Integer` porque `someNumbers2` el ejemplo anterior es una matriz de enteros.</span><span class="sxs-lookup"><span data-stu-id="157e3-130">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

<span data-ttu-id="157e3-131">La inferencia de tipo local se puede usar en `Using` instrucciones para establecer el tipo del nombre del recurso, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="157e3-131">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

<span data-ttu-id="157e3-132">El tipo de una variable también se puede inferir a partir de los valores devueltos de las funciones, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="157e3-132">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="157e3-133">`pList1`Y `pList2` son matrices de procesos porque `Process.GetProcesses` devuelve una matriz de procesos.</span><span class="sxs-lookup"><span data-stu-id="157e3-133">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a><span data-ttu-id="157e3-134">Option Infer</span><span class="sxs-lookup"><span data-stu-id="157e3-134">Option Infer</span></span>

<span data-ttu-id="157e3-135">`Option Infer` permite especificar si se permite la inferencia de tipo de variable local en un archivo determinado.</span><span class="sxs-lookup"><span data-stu-id="157e3-135">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="157e3-136">Para habilitar o para bloquear la opción, escriba una de las siguientes instrucciones al principio del archivo.</span><span class="sxs-lookup"><span data-stu-id="157e3-136">To enable or to block the option, type one of the following statements at the start of the file.</span></span>

`Option Infer On`

`Option Infer Off`

<span data-ttu-id="157e3-137">Si no especifica un valor para `Option Infer` en el código, el valor predeterminado del compilador es `Option Infer On` .</span><span class="sxs-lookup"><span data-stu-id="157e3-137">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span>

<span data-ttu-id="157e3-138">Si el valor establecido para `Option Infer` en un archivo entra en conflicto con el valor establecido en el IDE o en la línea de comandos, el valor del archivo tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="157e3-138">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>

<span data-ttu-id="157e3-139">Para obtener más información, vea [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md) y [compilar Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="157e3-139">For more information, see [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>

## <a name="see-also"></a><span data-ttu-id="157e3-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="157e3-140">See also</span></span>

- [<span data-ttu-id="157e3-141">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="157e3-141">Anonymous Types</span></span>](../objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="157e3-142">Enlace en tiempo de compilación y en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="157e3-142">Early and Late Binding</span></span>](../early-late-binding/index.md)
- [<span data-ttu-id="157e3-143">Instrucción For Each...Next</span><span class="sxs-lookup"><span data-stu-id="157e3-143">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="157e3-144">Instrucción For...Next</span><span class="sxs-lookup"><span data-stu-id="157e3-144">For...Next Statement</span></span>](../../../language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="157e3-145">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="157e3-145">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="157e3-146">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="157e3-146">-optioninfer</span></span>](../../../reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="157e3-147">Introducción a LINQ en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="157e3-147">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
