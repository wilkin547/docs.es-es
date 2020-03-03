---
title: 'Instrucciones de C#: un paseo por el lenguaje C#'
description: Las acciones de un programa de C# se crean mediante instrucciones.
ms.date: 02/27/2020
ms.assetid: 5409c379-5622-4fae-88b5-1654276ea8d4
ms.openlocfilehash: ced13b1bfd17977acb98bf33c0a477161cf08a93
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159109"
---
# <a name="statements"></a><span data-ttu-id="a37c8-103">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="a37c8-103">Statements</span></span>

<span data-ttu-id="a37c8-104">Las acciones de un programa se expresan mediante *instrucciones*.</span><span class="sxs-lookup"><span data-stu-id="a37c8-104">The actions of a program are expressed using *statements*.</span></span> <span data-ttu-id="a37c8-105">C# admite varios tipos de instrucciones diferentes, varias de las cuales se definen en términos de instrucciones insertadas.</span><span class="sxs-lookup"><span data-stu-id="a37c8-105">C# supports several different kinds of statements, a number of which are defined in terms of embedded statements.</span></span>

<span data-ttu-id="a37c8-106">Un *bloque* permite que se escriban varias instrucciones en contextos donde se permite una única instrucción.</span><span class="sxs-lookup"><span data-stu-id="a37c8-106">A *block* permits multiple statements to be written in contexts where a single statement is allowed.</span></span> <span data-ttu-id="a37c8-107">Un bloque se compone de una lista de instrucciones escritas entre los delimitadores `{` y `}`.</span><span class="sxs-lookup"><span data-stu-id="a37c8-107">A block consists of a list of statements written between the delimiters `{` and `}`.</span></span>

<span data-ttu-id="a37c8-108">Las *instrucciones de declaración* se usan para declarar variables locales y constantes.</span><span class="sxs-lookup"><span data-stu-id="a37c8-108">*Declaration statements* are used to declare local variables and constants.</span></span>

<span data-ttu-id="a37c8-109">Las *instrucciones de expresión* se usan para evaluar expresiones.</span><span class="sxs-lookup"><span data-stu-id="a37c8-109">*Expression statements* are used to evaluate expressions.</span></span> <span data-ttu-id="a37c8-110">Las expresiones que pueden usarse como instrucciones incluyen invocaciones de método, asignaciones de objetos mediante el operador `new`, asignaciones mediante `=` y los operadores de asignación compuestos, operaciones de incremento y decremento mediante los operadores `++` y `--` y expresiones `await`.</span><span class="sxs-lookup"><span data-stu-id="a37c8-110">Expressions that can be used as statements include method invocations, object allocations using the `new` operator, assignments using `=` and the compound assignment operators, increment and decrement operations using the `++` and `--` operators and `await` expressions.</span></span>

<span data-ttu-id="a37c8-111">Las *instrucciones de selección* se usan para seleccionar una de varias instrucciones posibles para su ejecución en función del valor de alguna expresión.</span><span class="sxs-lookup"><span data-stu-id="a37c8-111">*Selection statements* are used to select one of a number of possible statements for execution based on the value of some expression.</span></span> <span data-ttu-id="a37c8-112">Este grupo contiene las instrucciones `if` y `switch`.</span><span class="sxs-lookup"><span data-stu-id="a37c8-112">This group contains the `if` and `switch` statements.</span></span>

<span data-ttu-id="a37c8-113">Las *instrucciones de iteración* se usan para ejecutar una instrucción insertada de forma repetida.</span><span class="sxs-lookup"><span data-stu-id="a37c8-113">*Iteration statements* are used to execute repeatedly an embedded statement.</span></span> <span data-ttu-id="a37c8-114">Este grupo contiene las instrucciones `while`, `do`, `for` y `foreach`.</span><span class="sxs-lookup"><span data-stu-id="a37c8-114">This group contains the `while`, `do`, `for`, and `foreach` statements.</span></span>

<span data-ttu-id="a37c8-115">Las *instrucciones de salto* se usan para transferir el control.</span><span class="sxs-lookup"><span data-stu-id="a37c8-115">*Jump statements* are used to transfer control.</span></span> <span data-ttu-id="a37c8-116">Este grupo contiene las instrucciones `break`, `continue`, `goto`, `throw`, `return` y `yield`.</span><span class="sxs-lookup"><span data-stu-id="a37c8-116">This group contains the `break`, `continue`, `goto`, `throw`, `return`, and `yield` statements.</span></span>

<span data-ttu-id="a37c8-117">La instrucción `try`... `catch` se usa para detectar excepciones que se producen durante la ejecución de un bloque, y la instrucción `try`... `finally` se usa para especificar el código de finalización que siempre se ejecuta, tanto si se ha producido una excepción como si no.</span><span class="sxs-lookup"><span data-stu-id="a37c8-117">The `try`...`catch` statement is used to catch exceptions that occur during execution of a block, and the `try`...`finally` statement is used to specify finalization code that is always executed, whether an exception occurred or not.</span></span>

<span data-ttu-id="a37c8-118">Las instrucciones `checked` y `unchecked` sirven para controlar el contexto de comprobación de desbordamiento para conversiones y operaciones aritméticas de tipo integral.</span><span class="sxs-lookup"><span data-stu-id="a37c8-118">The `checked` and `unchecked` statements are used to control the overflow-checking context for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="a37c8-119">La instrucción `lock` se usa para obtener el bloqueo de exclusión mutua para un objeto determinado, ejecutar una instrucción y, luego, liberar el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a37c8-119">The `lock` statement is used to obtain the mutual-exclusion lock for a given object, execute a statement, and then release the lock.</span></span>

<span data-ttu-id="a37c8-120">La instrucción `using` se usa para obtener un recurso, ejecutar una instrucción y, luego, eliminar dicho recurso.</span><span class="sxs-lookup"><span data-stu-id="a37c8-120">The `using` statement is used to obtain a resource, execute a statement, and then dispose of that resource.</span></span>

<span data-ttu-id="a37c8-121">A continuación se enumeran los tipos de instrucciones que se pueden usar y se proporciona un ejemplo de cada una.</span><span class="sxs-lookup"><span data-stu-id="a37c8-121">The following lists the kinds of statements that can be used, and provides an example for each.</span></span>

* <span data-ttu-id="a37c8-122">Declaración de variable local:</span><span class="sxs-lookup"><span data-stu-id="a37c8-122">Local variable declaration:</span></span>

 [!code-csharp[Declarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L9-L15)]

* <span data-ttu-id="a37c8-123">Declaración de constante local:</span><span class="sxs-lookup"><span data-stu-id="a37c8-123">Local constant declaration:</span></span>

 [!code-csharp[ConstantDeclarations](../../../samples/snippets/csharp/tour/statements/Program.cs#L17-L22)]

* <span data-ttu-id="a37c8-124">Instrucción de expresión:</span><span class="sxs-lookup"><span data-stu-id="a37c8-124">Expression statement:</span></span>

 [!code-csharp[Expressions](../../../samples/snippets/csharp/tour/statements/Program.cs#L24-L31)]

* <span data-ttu-id="a37c8-125">Instrucción `if`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-125">`if` statement:</span></span>

 [!code-csharp[IfStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L33-L43)]

* <span data-ttu-id="a37c8-126">Instrucción `switch`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-126">`switch` statement:</span></span>

 [!code-csharp[SwitchStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L45-L60)]

* <span data-ttu-id="a37c8-127">Instrucción `while`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-127">`while` statement:</span></span>

 [!code-csharp[WhileStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L62-L70)]

* <span data-ttu-id="a37c8-128">Instrucción `do`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-128">`do` statement:</span></span>

 [!code-csharp[DoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L72-L81)]

* <span data-ttu-id="a37c8-129">Instrucción `for`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-129">`for` statement:</span></span>

 [!code-csharp[ForStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L83-L89)]

* <span data-ttu-id="a37c8-130">Instrucción `foreach`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-130">`foreach` statement:</span></span>

 [!code-csharp[ForEachStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L91-L97)]

* <span data-ttu-id="a37c8-131">Instrucción `break`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-131">`break` statement:</span></span>

 [!code-csharp[BreakStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L99-L108)]

* <span data-ttu-id="a37c8-132">Instrucción `continue`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-132">`continue` statement:</span></span>

 [!code-csharp[ContinueStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L110-L118)]

* <span data-ttu-id="a37c8-133">Instrucción `goto`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-133">`goto` statement:</span></span>

 [!code-csharp[GotoStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L120-L129)]

* <span data-ttu-id="a37c8-134">Instrucción `return`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-134">`return` statement:</span></span>

 [!code-csharp[ReturnStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L131-L139)]

* <span data-ttu-id="a37c8-135">Instrucción `yield`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-135">`yield` statement:</span></span>

 [!code-csharp[YieldStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L141-L155)]

* <span data-ttu-id="a37c8-136">Instrucciones `throw` e instrucciones `try`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-136">`throw` statements and `try` statements:</span></span>

 [!code-csharp[TryThrow](../../../samples/snippets/csharp/tour/statements/Program.cs#L157-L183)]

* <span data-ttu-id="a37c8-137">Instrucciones `checked` y `unchecked`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-137">`checked` and `unchecked` statements:</span></span>

 [!code-csharp[CheckedUncheckedStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L185-L196)]

* <span data-ttu-id="a37c8-138">Instrucción `lock`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-138">`lock` statement:</span></span>

 [!code-csharp[LockStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L257-L273)]

* <span data-ttu-id="a37c8-139">Instrucción `using`:</span><span class="sxs-lookup"><span data-stu-id="a37c8-139">`using` statement:</span></span>

 [!code-csharp[UsingStatement](../../../samples/snippets/csharp/tour/statements/Program.cs#L198-L206)]

>[!div class="step-by-step"]
><span data-ttu-id="a37c8-140">[Anterior](expressions.md)
>[Siguiente](classes-and-objects.md)</span><span class="sxs-lookup"><span data-stu-id="a37c8-140">[Previous](expressions.md)
[Next](classes-and-objects.md)</span></span>
