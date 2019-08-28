---
title: Variable de objeto o de bloque With no establecida
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 07c215d373e4ac1cbadf82a48b8cb3d90efdbdb4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040551"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="e1117-102">Variable de objeto o de bloque With no establecida</span><span class="sxs-lookup"><span data-stu-id="e1117-102">Object variable or With block variable not set</span></span>
<span data-ttu-id="e1117-103">Se está haciendo referencia a una variable de objeto no válido.</span><span class="sxs-lookup"><span data-stu-id="e1117-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="e1117-104">Este error puede producirse por varias razones:</span><span class="sxs-lookup"><span data-stu-id="e1117-104">This error can occur for several reasons:</span></span>

- <span data-ttu-id="e1117-105">Se declaró una variable sin especificar un tipo.</span><span class="sxs-lookup"><span data-stu-id="e1117-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="e1117-106">Si una variable se declara sin especificar un tipo, el valor predeterminado es Type `Object`.</span><span class="sxs-lookup"><span data-stu-id="e1117-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>

    <span data-ttu-id="e1117-107">Por ejemplo, una `Dim x` variable declarada con sería de tipo `Object;` una variable declarada con `Dim x As String` sería `String`de tipo.</span><span class="sxs-lookup"><span data-stu-id="e1117-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>

    > [!TIP]
    > <span data-ttu-id="e1117-108">La `Option Strict` instrucción no permite tipos implícitos que generan un `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="e1117-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="e1117-109">Si omite el tipo, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="e1117-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="e1117-110">Consulte [Option Strict (instrucción](../../../visual-basic/language-reference/statements/option-strict-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="e1117-110">See [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>

- <span data-ttu-id="e1117-111">Está intentando hacer referencia a un objeto que se ha establecido en `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="e1117-111">You are attempting to reference an object that has been set to `Nothing`.</span></span>

- <span data-ttu-id="e1117-112">Está intentando obtener acceso a un elemento de una variable de matriz que no se ha declarado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e1117-112">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>

    <span data-ttu-id="e1117-113">Por ejemplo, una matriz declarada como `products() As String` desencadenará el error si se intenta hacer referencia a un elemento de la matriz. `products(3) = "Widget"`</span><span class="sxs-lookup"><span data-stu-id="e1117-113">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="e1117-114">La matriz no tiene elementos y se trata como un objeto.</span><span class="sxs-lookup"><span data-stu-id="e1117-114">The array has no elements and is treated as an object.</span></span>

- <span data-ttu-id="e1117-115">Está intentando obtener acceso al código dentro de `With...End With` un bloque antes de que se haya inicializado el bloque.</span><span class="sxs-lookup"><span data-stu-id="e1117-115">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="e1117-116">Un `With...End With` bloque se debe inicializar ejecutando el punto de `With` entrada de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="e1117-116">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>

> [!NOTE]
> <span data-ttu-id="e1117-117">En versiones anteriores de Visual Basic o VBA, este error también se desencadenaba asignando un valor a una variable sin usar la `Set` palabra clave (`x = "name"` en lugar de `Set x = "name"`).</span><span class="sxs-lookup"><span data-stu-id="e1117-117">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="e1117-118">La `Set` palabra clave ya no es válida en Visual Basic .net.</span><span class="sxs-lookup"><span data-stu-id="e1117-118">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e1117-119">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e1117-119">To correct this error</span></span>

1. <span data-ttu-id="e1117-120">Establezca `Option Strict` en`On` agregando el código siguiente al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="e1117-120">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>

    ```vb
    Option Strict On
    ```

    <span data-ttu-id="e1117-121">Al ejecutar el proyecto, aparecerá un error del compilador en el **lista de errores** para cualquier variable que se especificó sin un tipo.</span><span class="sxs-lookup"><span data-stu-id="e1117-121">When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.</span></span>

2. <span data-ttu-id="e1117-122">Si no desea habilitar `Option Strict`, busque en el código las variables que se especificaron sin un tipo (`Dim x` en lugar de `Dim x As String`) y agregue el tipo previsto a la declaración.</span><span class="sxs-lookup"><span data-stu-id="e1117-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>

3. <span data-ttu-id="e1117-123">Asegúrese de que no hace referencia a una variable de objeto que se ha `Nothing`establecido en.</span><span class="sxs-lookup"><span data-stu-id="e1117-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="e1117-124">Busque en el código la palabra `Nothing`clave y revise el código para que el objeto no se establezca en `Nothing` hasta que se haya hecho referencia a él.</span><span class="sxs-lookup"><span data-stu-id="e1117-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>

4. <span data-ttu-id="e1117-125">Asegúrese de que las variables de matriz se dimensionan antes de tener acceso a ellas.</span><span class="sxs-lookup"><span data-stu-id="e1117-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="e1117-126">Puede asignar una dimensión la primera vez que cree la matriz (`Dim x(5) As String` en lugar de `Dim x() As String`), o bien use la `ReDim` palabra clave para establecer las dimensiones de la matriz antes de tener acceso a ella por primera vez.</span><span class="sxs-lookup"><span data-stu-id="e1117-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>

5. <span data-ttu-id="e1117-127">Asegúrese de que `With` el bloque se inicializa ejecutando el punto de `With` entrada de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="e1117-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1117-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1117-128">See also</span></span>

- [<span data-ttu-id="e1117-129">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="e1117-129">Object Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="e1117-130">ReDim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e1117-130">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)
- [<span data-ttu-id="e1117-131">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="e1117-131">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
