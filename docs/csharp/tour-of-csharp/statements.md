---
title: 'Instrucciones de C#: un paseo por el lenguaje C#'
description: Las acciones de un programa de C# se crean mediante instrucciones.
keywords: .NET, csharp, instrucciones, sintaxis
author: BillWagner
ms.author: wiwagn
ms.date: 11/06/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 5409c379-5622-4fae-88b5-1654276ea8d4
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 99ec2489daf89926da9b8c4e148965412826a8a6
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="statements"></a><span data-ttu-id="987d7-104">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="987d7-104">Statements</span></span>

<span data-ttu-id="987d7-105">Las acciones de un programa se expresan mediante *instrucciones*.</span><span class="sxs-lookup"><span data-stu-id="987d7-105">The actions of a program are expressed using *statements*.</span></span> <span data-ttu-id="987d7-106">C# admite varios tipos de instrucciones diferentes, varias de las cuales se definen en términos de instrucciones insertadas.</span><span class="sxs-lookup"><span data-stu-id="987d7-106">C# supports several different kinds of statements, a number of which are defined in terms of embedded statements.</span></span>

<span data-ttu-id="987d7-107">Un *bloque* permite que se escriban varias instrucciones en contextos donde se permite una única instrucción.</span><span class="sxs-lookup"><span data-stu-id="987d7-107">A *block* permits multiple statements to be written in contexts where a single statement is allowed.</span></span> <span data-ttu-id="987d7-108">Un bloque se compone de una lista de instrucciones escritas entre los delimitadores `{` y `}`.</span><span class="sxs-lookup"><span data-stu-id="987d7-108">A block consists of a list of statements written between the delimiters `{` and `}`.</span></span>

<span data-ttu-id="987d7-109">Las *instrucciones de declaración* se usan para declarar variables locales y constantes.</span><span class="sxs-lookup"><span data-stu-id="987d7-109">*Declaration statements* are used to declare local variables and constants.</span></span>

<span data-ttu-id="987d7-110">Las *instrucciones de expresión* se usan para evaluar expresiones.</span><span class="sxs-lookup"><span data-stu-id="987d7-110">*Expression statements* are used to evaluate expressions.</span></span> <span data-ttu-id="987d7-111">Las expresiones que pueden usarse como instrucciones incluyen invocaciones de método, asignaciones de objetos mediante el operador `new`, asignaciones mediante `=` y los operadores de asignación compuestos, operaciones de incremento y decremento mediante los operadores `++` y `--` y expresiones `await`.</span><span class="sxs-lookup"><span data-stu-id="987d7-111">Expressions that can be used as statements include method invocations, object allocations using the `new` operator, assignments using `=` and the compound assignment operators, increment and decrement operations using the `++` and `--` operators and `await` expressions.</span></span>

<span data-ttu-id="987d7-112">Las *instrucciones de selección* se usan para seleccionar una de varias instrucciones posibles para su ejecución en función del valor de alguna expresión.</span><span class="sxs-lookup"><span data-stu-id="987d7-112">*Selection statements* are used to select one of a number of possible statements for execution based on the value of some expression.</span></span> <span data-ttu-id="987d7-113">En este grupo están las instrucciones `if` y `switch`.</span><span class="sxs-lookup"><span data-stu-id="987d7-113">In this group are the `if` and `switch` statements.</span></span>

<span data-ttu-id="987d7-114">Las *instrucciones de iteración* se usan para ejecutar una instrucción insertada de forma repetida.</span><span class="sxs-lookup"><span data-stu-id="987d7-114">*Iteration statements* are used to execute repeatedly an embedded statement.</span></span> <span data-ttu-id="987d7-115">En este grupo están las instrucciones `while`, `do`, `for` y `foreach`.</span><span class="sxs-lookup"><span data-stu-id="987d7-115">In this group are the `while`, `do`, `for`, and `foreach` statements.</span></span>

<span data-ttu-id="987d7-116">Las *instrucciones de salto* se usan para transferir el control.</span><span class="sxs-lookup"><span data-stu-id="987d7-116">*Jump statements* are used to transfer control.</span></span> <span data-ttu-id="987d7-117">En este grupo están las instrucciones `break`, `continue`, `goto`, `throw`, `return` y `yield`.</span><span class="sxs-lookup"><span data-stu-id="987d7-117">In this group are the `break`, `continue`, `goto`, `throw`, `return`, and `yield` statements.</span></span>

<span data-ttu-id="987d7-118">La instrucción `try`... `catch` se usa para detectar excepciones que se producen durante la ejecución de un bloque, y la instrucción `try`... `finally` se usa para especificar el código de finalización que siempre se ejecuta, tanto si se ha producido una excepción como si no.</span><span class="sxs-lookup"><span data-stu-id="987d7-118">The `try`...`catch` statement is used to catch exceptions that occur during execution of a block, and the `try`...`finally` statement is used to specify finalization code that is always executed, whether an exception occurred or not.</span></span>

<span data-ttu-id="987d7-119">Las instrucciones `checked` y `unchecked` sirven para controlar el contexto de comprobación de desbordamiento para conversiones y operaciones aritméticas de tipo integral.</span><span class="sxs-lookup"><span data-stu-id="987d7-119">The `checked` and `unchecked` statements are used to control the overflow-checking context for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="987d7-120">La instrucción `lock` se usa para obtener el bloqueo de exclusión mutua para un objeto determinado, ejecutar una instrucción y, luego, liberar el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="987d7-120">The `lock` statement is used to obtain the mutual-exclusion lock for a given object, execute a statement, and then release the lock.</span></span>

<span data-ttu-id="987d7-121">La instrucción `using` se usa para obtener un recurso, ejecutar una instrucción y, luego, eliminar dicho recurso.</span><span class="sxs-lookup"><span data-stu-id="987d7-121">The `using` statement is used to obtain a resource, execute a statement, and then dispose of that resource.</span></span>

<span data-ttu-id="987d7-122">A continuación se enumeran los tipos de instrucciones que se pueden usar y se proporciona un ejemplo de cada una.</span><span class="sxs-lookup"><span data-stu-id="987d7-122">The following lists the kinds of statements that can be used, and provides an example for each.</span></span>

* <span data-ttu-id="987d7-123">Declaración de variable local:</span><span class="sxs-lookup"><span data-stu-id="987d7-123">Local variable declaration:</span></span>

 <span data-ttu-id="987d7-124">[!code-csharp[Declarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]</span><span class="sxs-lookup"><span data-stu-id="987d7-124">[!code-csharp[Declarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]</span></span>

* <span data-ttu-id="987d7-125">Declaración de constante local:</span><span class="sxs-lookup"><span data-stu-id="987d7-125">Local constant declaration:</span></span>

 <span data-ttu-id="987d7-126">[!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]</span><span class="sxs-lookup"><span data-stu-id="987d7-126">[!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]</span></span>

* <span data-ttu-id="987d7-127">Instrucción de expresión:</span><span class="sxs-lookup"><span data-stu-id="987d7-127">Expression statement:</span></span>

 <span data-ttu-id="987d7-128">[!code-csharp[Expressions](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]</span><span class="sxs-lookup"><span data-stu-id="987d7-128">[!code-csharp[Expressions](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]</span></span>

* <span data-ttu-id="987d7-129">Instrucción `if`:</span><span class="sxs-lookup"><span data-stu-id="987d7-129">`if` statement:</span></span>

 <span data-ttu-id="987d7-130">[!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]</span><span class="sxs-lookup"><span data-stu-id="987d7-130">[!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]</span></span>

* <span data-ttu-id="987d7-131">Instrucción `switch`:</span><span class="sxs-lookup"><span data-stu-id="987d7-131">`switch` statement:</span></span>

 <span data-ttu-id="987d7-132">[!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]</span><span class="sxs-lookup"><span data-stu-id="987d7-132">[!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]</span></span>

* <span data-ttu-id="987d7-133">Instrucción `while`:</span><span class="sxs-lookup"><span data-stu-id="987d7-133">`while` statement:</span></span>

 <span data-ttu-id="987d7-134">[!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]</span><span class="sxs-lookup"><span data-stu-id="987d7-134">[!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]</span></span>

* <span data-ttu-id="987d7-135">Instrucción `do`:</span><span class="sxs-lookup"><span data-stu-id="987d7-135">`do` statement:</span></span>

 <span data-ttu-id="987d7-136">[!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]</span><span class="sxs-lookup"><span data-stu-id="987d7-136">[!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]</span></span>

* <span data-ttu-id="987d7-137">Instrucción `for`:</span><span class="sxs-lookup"><span data-stu-id="987d7-137">`for` statement:</span></span>

 <span data-ttu-id="987d7-138">[!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]</span><span class="sxs-lookup"><span data-stu-id="987d7-138">[!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]</span></span>

* <span data-ttu-id="987d7-139">Instrucción `foreach`:</span><span class="sxs-lookup"><span data-stu-id="987d7-139">`foreach` statement:</span></span>

 <span data-ttu-id="987d7-140">[!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]</span><span class="sxs-lookup"><span data-stu-id="987d7-140">[!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]</span></span>

* <span data-ttu-id="987d7-141">Instrucción `break`:</span><span class="sxs-lookup"><span data-stu-id="987d7-141">`break` statement:</span></span>

 <span data-ttu-id="987d7-142">[!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]</span><span class="sxs-lookup"><span data-stu-id="987d7-142">[!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]</span></span>

* <span data-ttu-id="987d7-143">Instrucción `continue`:</span><span class="sxs-lookup"><span data-stu-id="987d7-143">`continue` statement:</span></span>

 <span data-ttu-id="987d7-144">[!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]</span><span class="sxs-lookup"><span data-stu-id="987d7-144">[!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]</span></span>

* <span data-ttu-id="987d7-145">Instrucción `goto`:</span><span class="sxs-lookup"><span data-stu-id="987d7-145">`goto` statement:</span></span>

 <span data-ttu-id="987d7-146">[!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]</span><span class="sxs-lookup"><span data-stu-id="987d7-146">[!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]</span></span>

* <span data-ttu-id="987d7-147">Instrucción `return`:</span><span class="sxs-lookup"><span data-stu-id="987d7-147">`return` statement:</span></span>

 <span data-ttu-id="987d7-148">[!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]</span><span class="sxs-lookup"><span data-stu-id="987d7-148">[!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]</span></span>

* <span data-ttu-id="987d7-149">Instrucción `yield`:</span><span class="sxs-lookup"><span data-stu-id="987d7-149">`yield` statement:</span></span>

 <span data-ttu-id="987d7-150">[!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]</span><span class="sxs-lookup"><span data-stu-id="987d7-150">[!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]</span></span>

* <span data-ttu-id="987d7-151">Instrucciones `throw` e instrucciones `try`:</span><span class="sxs-lookup"><span data-stu-id="987d7-151">`throw` statements and `try` statements:</span></span>

 <span data-ttu-id="987d7-152">[!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]</span><span class="sxs-lookup"><span data-stu-id="987d7-152">[!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]</span></span>

* <span data-ttu-id="987d7-153">Instrucciones `checked` y `unchecked`:</span><span class="sxs-lookup"><span data-stu-id="987d7-153">`checked` and `unchecked` statements:</span></span>

 <span data-ttu-id="987d7-154">[!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]</span><span class="sxs-lookup"><span data-stu-id="987d7-154">[!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]</span></span>

* <span data-ttu-id="987d7-155">Instrucción `lock`:</span><span class="sxs-lookup"><span data-stu-id="987d7-155">`lock` statement:</span></span>

 <span data-ttu-id="987d7-156">[!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]</span><span class="sxs-lookup"><span data-stu-id="987d7-156">[!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]</span></span>

* <span data-ttu-id="987d7-157">Instrucción `using`:</span><span class="sxs-lookup"><span data-stu-id="987d7-157">`using` statement:</span></span>

 <span data-ttu-id="987d7-158">[!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]</span><span class="sxs-lookup"><span data-stu-id="987d7-158">[!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="987d7-159">[Anterior](expressions.md)
[Siguiente](classes-and-objects.md)</span><span class="sxs-lookup"><span data-stu-id="987d7-159">[Previous](expressions.md)
[Next](classes-and-objects.md)</span></span>

