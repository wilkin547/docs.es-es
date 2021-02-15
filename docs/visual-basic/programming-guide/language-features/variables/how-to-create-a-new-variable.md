---
description: 'Más información acerca de cómo: crear una nueva variable (Visual Basic)'
title: Procedimiento para crear una variable
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: b473a247bc5b4d9c1d65f4721ecba3621b232e27
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481966"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="41c4c-103">Cómo: Crear una nueva variable (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41c4c-103">How to: Create a New Variable (Visual Basic)</span></span>

<span data-ttu-id="41c4c-104">Cree una variable con una [instrucción Dim](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="41c4c-104">You create a variable with a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span>

### <a name="to-create-a-new-variable"></a><span data-ttu-id="41c4c-105">Para crear una nueva variable</span><span class="sxs-lookup"><span data-stu-id="41c4c-105">To create a new variable</span></span>

1. <span data-ttu-id="41c4c-106">Declare la variable en una `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="41c4c-106">Declare the variable in a `Dim` statement.</span></span>

    ```vb
    Dim newCustomer
    ```

2. <span data-ttu-id="41c4c-107">Incluye especificaciones para las características de la variable, como [Private](../../../language-reference/modifiers/private.md), [static](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md)o [WithEvents](../../../language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="41c4c-107">Include specifications for the variable's characteristics, such as [Private](../../../language-reference/modifiers/private.md), [Static](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md), or [WithEvents](../../../language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="41c4c-108">Para obtener más información, vea características de los [elementos declarados](../declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="41c4c-108">For more information, see [Declared Element Characteristics](../declared-elements/declared-element-characteristics.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

    <span data-ttu-id="41c4c-109">No necesita la `Dim` palabra clave si utiliza otras palabras clave en la declaración.</span><span class="sxs-lookup"><span data-stu-id="41c4c-109">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>

3. <span data-ttu-id="41c4c-110">Siga las especificaciones con el nombre de la variable, que debe seguir Visual Basic reglas y convenciones.</span><span class="sxs-lookup"><span data-stu-id="41c4c-110">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="41c4c-111">Para obtener más información, vea [nombres de elementos declarados](../declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="41c4c-111">For more information, see [Declared Element Names](../declared-elements/declared-element-names.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

4. <span data-ttu-id="41c4c-112">Siga el nombre con la cláusula [as](../../../language-reference/statements/as-clause.md) para especificar el tipo de datos de la variable.</span><span class="sxs-lookup"><span data-stu-id="41c4c-112">Follow the name with the [As](../../../language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>

    ```vb
    Public Static newCustomer As Customer
    ```

    <span data-ttu-id="41c4c-113">Si no se especifica el tipo de datos, se usa el valor predeterminado: `Object` .</span><span class="sxs-lookup"><span data-stu-id="41c4c-113">If you do not specify the data type, it uses the default: `Object`.</span></span>

5. <span data-ttu-id="41c4c-114">Siga la `As` cláusula con un signo igual ( `=` ) y siga el signo igual con el valor inicial de la variable.</span><span class="sxs-lookup"><span data-stu-id="41c4c-114">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>

    <span data-ttu-id="41c4c-115">Visual Basic asigna el valor especificado a la variable cada vez que se ejecuta la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="41c4c-115">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="41c4c-116">Si no especifica un valor inicial, Visual Basic asigna el valor inicial predeterminado para el tipo de datos de la variable cuando entra por primera vez en el código que contiene la `Dim` instrucción.</span><span class="sxs-lookup"><span data-stu-id="41c4c-116">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>

    <span data-ttu-id="41c4c-117">Si la variable es un tipo de referencia, puede crear una instancia de su clase incluyendo la palabra clave [New Operator](../../../language-reference/operators/new-operator.md) en la `As` cláusula.</span><span class="sxs-lookup"><span data-stu-id="41c4c-117">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="41c4c-118">Si no usa `New` , el valor inicial de la variable es [Nothing](../../../language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="41c4c-118">If you do not use `New`, the initial value of the variable is [Nothing](../../../language-reference/nothing.md).</span></span>

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a><span data-ttu-id="41c4c-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41c4c-119">See also</span></span>

- [<span data-ttu-id="41c4c-120">Variables</span><span class="sxs-lookup"><span data-stu-id="41c4c-120">Variables</span></span>](index.md)
- [<span data-ttu-id="41c4c-121">Declaración de variable</span><span class="sxs-lookup"><span data-stu-id="41c4c-121">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="41c4c-122">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="41c4c-122">Declared Element Names</span></span>](../declared-elements/declared-element-names.md)
- [<span data-ttu-id="41c4c-123">Características de los elementos declarados</span><span class="sxs-lookup"><span data-stu-id="41c4c-123">Declared Element Characteristics</span></span>](../declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="41c4c-124">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="41c4c-124">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="41c4c-125">Instrucciones</span><span class="sxs-lookup"><span data-stu-id="41c4c-125">Statements</span></span>](../../../language-reference/statements/index.md)
- [<span data-ttu-id="41c4c-126">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="41c4c-126">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="41c4c-127">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="41c4c-127">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)
