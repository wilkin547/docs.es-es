---
title: Variable de objeto o de bloque With no establecida
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 0264a4235a056c93edb703ec2ef70e7124e0df4e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873625"
---
# <a name="object-variable-or-with-block-variable-not-set"></a><span data-ttu-id="d12a4-102">Variable de objeto o de bloque With no establecida</span><span class="sxs-lookup"><span data-stu-id="d12a4-102">Object variable or With block variable not set</span></span>

<span data-ttu-id="d12a4-103">Se está haciendo referencia a una variable de objeto no válido.</span><span class="sxs-lookup"><span data-stu-id="d12a4-103">An invalid object variable is being referenced.</span></span>   <span data-ttu-id="d12a4-104">Este error puede producirse por varias razones:</span><span class="sxs-lookup"><span data-stu-id="d12a4-104">This error can occur for several reasons:</span></span>

- <span data-ttu-id="d12a4-105">Se declaró una variable sin especificar un tipo.</span><span class="sxs-lookup"><span data-stu-id="d12a4-105">A variable was declared without specifying a type.</span></span> <span data-ttu-id="d12a4-106">Si una variable se declara sin especificar un tipo, el valor predeterminado es Type `Object` .</span><span class="sxs-lookup"><span data-stu-id="d12a4-106">If a variable is declared without specifying a type, it defaults to type `Object`.</span></span>

    <span data-ttu-id="d12a4-107">Por ejemplo, una variable declarada con `Dim x` sería de tipo `Object;` una variable declarada con `Dim x As String` sería de tipo `String` .</span><span class="sxs-lookup"><span data-stu-id="d12a4-107">For example, a variable declared with `Dim x` would be of type `Object;` a variable declared with `Dim x As String` would be of type `String`.</span></span>

    > [!TIP]
    > <span data-ttu-id="d12a4-108">La `Option Strict` instrucción no permite tipos implícitos que generan un `Object` tipo.</span><span class="sxs-lookup"><span data-stu-id="d12a4-108">The `Option Strict` statement disallows implicit typing that results in an `Object` type.</span></span> <span data-ttu-id="d12a4-109">Si omite el tipo, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d12a4-109">If you omit the type, a compile-time error will occur.</span></span> <span data-ttu-id="d12a4-110">Vea [Option Strict (instrucción)](../statements/option-strict-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d12a4-110">See [Option Strict Statement](../statements/option-strict-statement.md).</span></span>

- <span data-ttu-id="d12a4-111">Está intentando hacer referencia a un objeto que se ha establecido en `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="d12a4-111">You are attempting to reference an object that has been set to `Nothing`.</span></span>

- <span data-ttu-id="d12a4-112">Está intentando obtener acceso a un elemento de una variable de matriz que no se ha declarado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d12a4-112">You are attempting to access an element of an array variable that wasn't properly declared.</span></span>

    <span data-ttu-id="d12a4-113">Por ejemplo, una matriz declarada como `products() As String` desencadenará el error si se intenta hacer referencia a un elemento de la matriz `products(3) = "Widget"` .</span><span class="sxs-lookup"><span data-stu-id="d12a4-113">For example, an array declared as `products() As String` will trigger the error if you try to reference an element of the array `products(3) = "Widget"`.</span></span> <span data-ttu-id="d12a4-114">La matriz no tiene elementos y se trata como un objeto.</span><span class="sxs-lookup"><span data-stu-id="d12a4-114">The array has no elements and is treated as an object.</span></span>

- <span data-ttu-id="d12a4-115">Está intentando obtener acceso al código dentro de un `With...End With` bloque antes de que se haya inicializado el bloque.</span><span class="sxs-lookup"><span data-stu-id="d12a4-115">You are attempting to access code within a `With...End With` block before the block has been initialized.</span></span>   <span data-ttu-id="d12a4-116">Un `With...End With` bloque se debe inicializar ejecutando el punto de `With` entrada de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="d12a4-116">A `With...End With` block must be initialized by executing the `With` statement entry point.</span></span>

> [!NOTE]
> <span data-ttu-id="d12a4-117">En versiones anteriores de Visual Basic o VBA, este error también se desencadenaba asignando un valor a una variable sin usar la `Set` palabra clave ( `x = "name"` en lugar de `Set x = "name"` ).</span><span class="sxs-lookup"><span data-stu-id="d12a4-117">In earlier versions of Visual Basic or VBA this error was also triggered by assigning a value to a variable without using the `Set` keyword (`x = "name"` instead of `Set x = "name"`).</span></span> <span data-ttu-id="d12a4-118">La `Set` palabra clave ya no es válida en Visual Basic .net.</span><span class="sxs-lookup"><span data-stu-id="d12a4-118">The `Set` keyword is no longer valid in Visual Basic .Net.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="d12a4-119">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="d12a4-119">To correct this error</span></span>

1. <span data-ttu-id="d12a4-120">Establezca `Option Strict` en agregando `On` el código siguiente al principio del archivo:</span><span class="sxs-lookup"><span data-stu-id="d12a4-120">Set `Option Strict` to `On` by adding the following code to the beginning of the file:</span></span>

    ```vb
    Option Strict On
    ```

    <span data-ttu-id="d12a4-121">Al ejecutar el proyecto, aparecerá un error del compilador en el **lista de errores** para cualquier variable que se especificó sin un tipo.</span><span class="sxs-lookup"><span data-stu-id="d12a4-121">When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.</span></span>

2. <span data-ttu-id="d12a4-122">Si no desea habilitar `Option Strict` , busque en el código las variables que se especificaron sin un tipo ( `Dim x` en lugar de `Dim x As String` ) y agregue el tipo previsto a la declaración.</span><span class="sxs-lookup"><span data-stu-id="d12a4-122">If you don't want to enable `Option Strict`, search your code for any variables that were specified without a type (`Dim x` instead of `Dim x As String`) and add the intended type to the declaration.</span></span>

3. <span data-ttu-id="d12a4-123">Asegúrese de que no hace referencia a una variable de objeto que se ha establecido en `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="d12a4-123">Make sure you aren't referring to  an object variable that has been set to `Nothing`.</span></span>  <span data-ttu-id="d12a4-124">Busque en el código la palabra clave `Nothing` y revise el código para que el objeto no se establezca en `Nothing` hasta que se haya hecho referencia a él.</span><span class="sxs-lookup"><span data-stu-id="d12a4-124">Search your code for the keyword `Nothing`, and revise your code so that the object isn't set to `Nothing` until after you have referenced it.</span></span>

4. <span data-ttu-id="d12a4-125">Asegúrese de que las variables de matriz se dimensionan antes de tener acceso a ellas.</span><span class="sxs-lookup"><span data-stu-id="d12a4-125">Make sure that any array  variables are dimensioned before you access them.</span></span> <span data-ttu-id="d12a4-126">Puede asignar una dimensión la primera vez que cree la matriz ( `Dim x(5) As String` en lugar de `Dim x() As String` ), o bien use la `ReDim` palabra clave para establecer las dimensiones de la matriz antes de tener acceso a ella por primera vez.</span><span class="sxs-lookup"><span data-stu-id="d12a4-126">You can either assign a dimension when you first create the array (`Dim x(5) As String` instead of `Dim x() As String`), or use the `ReDim` keyword to set the dimensions of the array before you first access it.</span></span>

5. <span data-ttu-id="d12a4-127">Asegúrese de que el `With` bloque se inicializa ejecutando el punto de `With` entrada de la instrucción.</span><span class="sxs-lookup"><span data-stu-id="d12a4-127">Make sure your `With` block is initialized by executing the `With` statement entry point.</span></span>

## <a name="see-also"></a><span data-ttu-id="d12a4-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d12a4-128">See also</span></span>

- [<span data-ttu-id="d12a4-129">Declaración de variables de objeto</span><span class="sxs-lookup"><span data-stu-id="d12a4-129">Object Variable Declaration</span></span>](../../programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="d12a4-130">Instrucción ReDim</span><span class="sxs-lookup"><span data-stu-id="d12a4-130">ReDim Statement</span></span>](../statements/redim-statement.md)
- [<span data-ttu-id="d12a4-131">Instrucción With...End With</span><span class="sxs-lookup"><span data-stu-id="d12a4-131">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
