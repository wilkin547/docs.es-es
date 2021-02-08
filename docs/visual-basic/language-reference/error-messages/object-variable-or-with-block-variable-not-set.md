---
description: 'Más información acerca de: variable de objeto o con variable de bloque no establecida'
title: Variable de objeto o de bloque With no establecida
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: a20655c2219aa5b90015e025a38ea9dd02894a6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795578"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="aa163-103">Variable de objeto o de bloque With no establecida</span><span class="sxs-lookup"><span data-stu-id="aa163-103">Object variable or With block variable not set</span></span>

<span data-ttu-id="aa163-104">Se está haciendo referencia a una variable de objeto no válido.</span><span class="sxs-lookup"><span data-stu-id="aa163-104">An invalid object variable is being referenced.</span></span> <span data-ttu-id="aa163-105">Este error puede producirse por varias razones:</span><span class="sxs-lookup"><span data-stu-id="aa163-105">This error can occur for several reasons:</span></span>

- <span data-ttu-id="aa163-106">Se declaró una variable sin especificar un tipo.</span><span class="sxs-lookup"><span data-stu-id="aa163-106">A variable was declared without specifying a type.</span></span> <span data-ttu-id="aa163-107">Si una variable se declara sin especificar un tipo, el valor predeterminado es Type `Object` .</span><span class="sxs-lookup"><span data-stu-id="aa163-107">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>

    <span data-ttu-id="aa163-108">Por ejemplo, una variable declarada con `Dim x` sería de tipo `Object;` una variable declarada con `Dim x As String` sería de tipo `String` .</span><span class="sxs-lookup"><span data-stu-id="aa163-108">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>

    > [!TIP]
    > <span data-ttu-id="aa163-109">La `Option Strict` instrucción no permite tipos implícitos que generan un `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="aa163-109">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="aa163-110">Si omite el tipo, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="aa163-110">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="aa163-111">Vea [Option Strict (instrucción)](../statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="aa163-111">See [Option Strict Statement](../statements/option-strict-statement.md).</span></span>

- <span data-ttu-id="aa163-112">Está intentando hacer referencia a un objeto que se ha establecido en `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="aa163-112">You are attempting to reference an object that has been set to `Nothing`.</span></span>

- <span data-ttu-id="aa163-113">Está intentando obtener acceso a un elemento de una variable de matriz que no se ha declarado correctamente.</span><span class="sxs-lookup"><span data-stu-id="aa163-113">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>

    <span data-ttu-id="aa163-114">Por ejemplo, una matriz declarada como `products() As String` desencadenará el error si se intenta hacer referencia a un elemento de la matriz `products(3) = "Widget"` .</span><span class="sxs-lookup"><span data-stu-id="aa163-114">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="aa163-115">La matriz no tiene elementos y se trata como un objeto.</span><span class="sxs-lookup"><span data-stu-id="aa163-115">The array has no elements and is treated as an object.</span></span>

- <span data-ttu-id="aa163-116">Está intentando obtener acceso al código dentro de un `With...End With` bloque antes de que se haya inicializado el bloque.</span><span class="sxs-lookup"><span data-stu-id="aa163-116">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="aa163-117">Un `With...End With` bloque se debe inicializar ejecutando el punto de `With` entrada de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="aa163-117">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>

> [!NOTE]
> <span data-ttu-id="aa163-118">En versiones anteriores de Visual Basic o VBA, este error también se desencadenaba asignando un valor a una variable sin usar la `Set` palabra clave ( `x = "name"` en lugar de `Set x = "name"` ).</span><span class="sxs-lookup"><span data-stu-id="aa163-118">In earlier versions of Visual Basic or VBA, this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="aa163-119">La `Set` palabra clave ya no es válida en Visual Basic .net.</span><span class="sxs-lookup"><span data-stu-id="aa163-119">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="aa163-120">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="aa163-120">To correct this error</span></span>

1. <span data-ttu-id="aa163-121">Establezca `Option Strict` en agregando `On` el código siguiente al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="aa163-121">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>

    ```vb
    Option Strict On
    ```

    <span data-ttu-id="aa163-122">Al ejecutar el proyecto, aparecerá un error del compilador en el **lista de errores** para cualquier variable que se especificó sin un tipo.</span><span class="sxs-lookup"><span data-stu-id="aa163-122">When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.</span></span>

2. <span data-ttu-id="aa163-123">Si no desea habilitar `Option Strict` , busque en el código las variables que se especificaron sin un tipo ( `Dim x` en lugar de `Dim x As String` ) y agregue el tipo previsto a la declaración.</span><span class="sxs-lookup"><span data-stu-id="aa163-123">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>

3. <span data-ttu-id="aa163-124">Asegúrese de que no hace referencia a una variable de objeto que se ha establecido en `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="aa163-124">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="aa163-125">Busque en el código la palabra clave `Nothing` y revise el código para que el objeto no se establezca en `Nothing` hasta que se haya hecho referencia a él.</span><span class="sxs-lookup"><span data-stu-id="aa163-125">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>

4. <span data-ttu-id="aa163-126">Asegúrese de que las variables de matriz se dimensionan antes de tener acceso a ellas.</span><span class="sxs-lookup"><span data-stu-id="aa163-126">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="aa163-127">Puede asignar una dimensión la primera vez que cree la matriz ( `Dim x(5) As String` en lugar de `Dim x() As String` ), o bien use la `ReDim` palabra clave para establecer las dimensiones de la matriz antes de tener acceso a ella por primera vez.</span><span class="sxs-lookup"><span data-stu-id="aa163-127">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>

5. <span data-ttu-id="aa163-128">Asegúrese de que el `With` bloque se inicializa ejecutando el punto de `With` entrada de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="aa163-128">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa163-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa163-129">See also</span></span>

- [<span data-ttu-id="aa163-130">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="aa163-130">Object Variable Declaration</span></span>](../../programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="aa163-131">Instrucción ReDim</span><span class="sxs-lookup"><span data-stu-id="aa163-131">ReDim Statement</span></span>](../statements/redim-statement.md)
- [<span data-ttu-id="aa163-132">Instrucción With...End With</span><span class="sxs-lookup"><span data-stu-id="aa163-132">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
