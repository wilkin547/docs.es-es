---
title: Sintaxis usada por la propiedad DebugView
description: Describe la sintaxis especial usada por la propiedad DebugView para producir una representación de cadena de árboles de expresión
author: zspitz
ms.author: wiwagn
ms.date: 14/02/2021
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 8a4feac72c2cd79485f5733b16d65b52cc50ee6c
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "100584898"
---
# <a name="debugview-syntax"></a><span data-ttu-id="c2229-103">Sintaxis de **DebugView**</span><span class="sxs-lookup"><span data-stu-id="c2229-103">**DebugView** syntax</span></span>

<span data-ttu-id="c2229-104">La propiedad **DebugView** (disponible solo al depurar) proporciona una representación de cadena de los árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="c2229-104">The **DebugView** property (available only when debugging) provides a string rendering of expression trees.</span></span> <span data-ttu-id="c2229-105">La mayor parte de la sintaxis es bastante sencilla de entender; los casos especiales se describen en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="c2229-105">Most of the syntax is fairly straightforward to understand; the special cases are described in the following sections.</span></span>

<span data-ttu-id="c2229-106">Cada ejemplo va seguido de un bloque de comentario que contiene **DebugView**.</span><span class="sxs-lookup"><span data-stu-id="c2229-106">Each example is followed by a comment block containing the **DebugView**.</span></span>

## <a name="parameterexpression"></a><span data-ttu-id="c2229-107">ParameterExpression</span><span class="sxs-lookup"><span data-stu-id="c2229-107">ParameterExpression</span></span>

<span data-ttu-id="c2229-108">Los nombres de variable <xref:System.Linq.Expressions.ParameterExpression> se muestran con un símbolo "$" al principio.</span><span class="sxs-lookup"><span data-stu-id="c2229-108"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="c2229-109">Si un parámetro no tiene un nombre, se le asigna un nombre generado automáticamente, como `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="c2229-109">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="c2229-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c2229-110">Examples</span></span>

```vb
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")
'
'    $num
'

Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer))
'
'    $var1
'
```

## <a name="constantexpressions"></a><span data-ttu-id="c2229-111">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="c2229-111">ConstantExpressions</span></span>

<span data-ttu-id="c2229-112">Para los objetos <xref:System.Linq.Expressions.ConstantExpression> que representan valores enteros, cadenas y `null`, se muestra el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="c2229-112">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

<span data-ttu-id="c2229-113">En algunos tipos numéricos, se agrega un sufijo al valor:</span><span class="sxs-lookup"><span data-stu-id="c2229-113">For some numeric types, a suffix is added to the value:</span></span>

| <span data-ttu-id="c2229-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="c2229-114">Type</span></span> | <span data-ttu-id="c2229-115">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="c2229-115">Keyword</span></span> | <span data-ttu-id="c2229-116">Sufijo</span><span class="sxs-lookup"><span data-stu-id="c2229-116">Suffix</span></span> |
|--|--|--|
| <xref:System.UInt32?displayProperty=nameWithType> | [<span data-ttu-id="c2229-117">UInteger</span><span class="sxs-lookup"><span data-stu-id="c2229-117">UInteger</span></span>](../../../language-reference/data-types/uinteger-data-type.md) | <span data-ttu-id="c2229-118">U</span><span class="sxs-lookup"><span data-stu-id="c2229-118">U</span></span> |
| <xref:System.Int64?displayProperty=nameWithType> | [<span data-ttu-id="c2229-119">Long</span><span class="sxs-lookup"><span data-stu-id="c2229-119">Long</span></span>](../../../language-reference/data-types/long-data-type.md) | <span data-ttu-id="c2229-120">L</span><span class="sxs-lookup"><span data-stu-id="c2229-120">L</span></span> |
| <xref:System.UInt64?displayProperty=nameWithType> | [<span data-ttu-id="c2229-121">ULong</span><span class="sxs-lookup"><span data-stu-id="c2229-121">ULong</span></span>](../../../language-reference/data-types/ulong-data-type.md) | <span data-ttu-id="c2229-122">UL</span><span class="sxs-lookup"><span data-stu-id="c2229-122">UL</span></span> |
| <xref:System.Double?displayProperty=nameWithType> | [<span data-ttu-id="c2229-123">Double</span><span class="sxs-lookup"><span data-stu-id="c2229-123">Double</span></span>](../../../language-reference/data-types/double-data-type.md) | <span data-ttu-id="c2229-124">D</span><span class="sxs-lookup"><span data-stu-id="c2229-124">D</span></span> |
| <xref:System.Single?displayProperty=nameWithType> | [<span data-ttu-id="c2229-125">Single</span><span class="sxs-lookup"><span data-stu-id="c2229-125">Single</span></span>](../../../language-reference/data-types/single-data-type.md) | <span data-ttu-id="c2229-126">F</span><span class="sxs-lookup"><span data-stu-id="c2229-126">F</span></span> |
| <xref:System.Decimal?displayProperty=nameWithType> | [<span data-ttu-id="c2229-127">Decimal</span><span class="sxs-lookup"><span data-stu-id="c2229-127">Decimal</span></span>](../../../language-reference/data-types/decimal-data-type.md) | <span data-ttu-id="c2229-128">M</span><span class="sxs-lookup"><span data-stu-id="c2229-128">M</span></span> |

### <a name="examples"></a><span data-ttu-id="c2229-129">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c2229-129">Examples</span></span>

```vb
Dim num as Integer = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10
'

Dim num As Double = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10D
'
```

## <a name="blockexpression"></a><span data-ttu-id="c2229-130">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="c2229-130">BlockExpression</span></span>

<span data-ttu-id="c2229-131">Si el tipo de un objeto <xref:System.Linq.Expressions.BlockExpression> difiere del tipo de la última expresión del bloque, el tipo se muestra entre corchetes angulares (`<` y `>`).</span><span class="sxs-lookup"><span data-stu-id="c2229-131">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed within angle brackets (`<` and `>`).</span></span> <span data-ttu-id="c2229-132">De otro modo, el tipo del objeto <xref:System.Linq.Expressions.BlockExpression> no se muestra.</span><span class="sxs-lookup"><span data-stu-id="c2229-132">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="c2229-133">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c2229-133">Examples</span></span>

```vb
Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
'
'    .Block() {
'        "test"
'    }
'

Dim block As BlockExpression = Expression.Block(
    GetType(Object),
    Expression.Constant("test")
)
'
'    .Block<System.Object>() {
'        "test"
'    }
'
```

## <a name="lambdaexpression"></a><span data-ttu-id="c2229-134">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="c2229-134">LambdaExpression</span></span>

<span data-ttu-id="c2229-135">Los objetos <xref:System.Linq.Expressions.LambdaExpression> se muestran junto con sus tipos delegados.</span><span class="sxs-lookup"><span data-stu-id="c2229-135"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="c2229-136">Si una expresión lambda no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="c2229-136">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="c2229-137">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c2229-137">Examples</span></span>

```vb
Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1)
)
'
'    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
'        1
'    }
'

Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1),
    "SampleLambda",
    Nothing
)
'
'    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
'        1
'    }
'
```

## <a name="labelexpression"></a><span data-ttu-id="c2229-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="c2229-138">LabelExpression</span></span>

<span data-ttu-id="c2229-139">Si especifica un valor predeterminado para el objeto <xref:System.Linq.Expressions.LabelExpression>, este valor se muestra antes del objeto <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="c2229-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="c2229-140">El token `.Label` indica el inicio de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="c2229-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="c2229-141">El token `.LabelTarget` indica el destino al que se va a saltar.</span><span class="sxs-lookup"><span data-stu-id="c2229-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="c2229-142">Si una etiqueta no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="c2229-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="c2229-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c2229-143">Examples</span></span>

```vb
Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
)
'
'    .Block() {
'        .Goto SampleLabel { 0 };
'        .Label
'            -1
'        .LabelTarget SampleLabel:
'    }
'

Dim target As LabelTarget = Expression.Label()
Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target),
    Expression.Label(target)
)
'
'    .Block() {
'        .Goto #Label1 { };
'        .Label
'        .LabelTarget #Label1:
'    }
'
```

## <a name="checked-operators"></a><span data-ttu-id="c2229-144">Operadores activados</span><span class="sxs-lookup"><span data-stu-id="c2229-144">Checked Operators</span></span>

<span data-ttu-id="c2229-145">Los operadores activados se muestran con el símbolo `#` delante del operador.</span><span class="sxs-lookup"><span data-stu-id="c2229-145">Checked operators are displayed with the `#` symbol in front of the operator.</span></span> <span data-ttu-id="c2229-146">Por ejemplo, el operador de adición activado se muestra como `#+`.</span><span class="sxs-lookup"><span data-stu-id="c2229-146">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="c2229-147">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c2229-147">Examples</span></span>

```vb
Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1),
    Expression.Constant(2)
)
'
'     1 #+ 2
'

Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0),
    GetType(Integer)
)
'
'    #(System.Int32)10D
'
```
