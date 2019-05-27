---
title: Sintaxis utilizada por la propiedad DebugView (Visual Basic)
description: Describe la sintaxis especial utilizada por la propiedad DebugView para producir una representación de cadena de árboles de expresión
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 1b2a1164f02208cc7578820d8f8ed3bc145fb5b8
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196535"
---
# <a name="debugview-syntax"></a><span data-ttu-id="ab083-103">Sintaxis de `DebugView`</span><span class="sxs-lookup"><span data-stu-id="ab083-103">`DebugView` syntax</span></span> 

<span data-ttu-id="ab083-104">El `DebugView` propiedad (disponible solo al depurar) proporciona una representación de cadena de árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="ab083-104">The `DebugView` property (available only when debugging) provides a string rendering of expression trees.</span></span> <span data-ttu-id="ab083-105">La mayoría de la sintaxis es bastante fácil de entender; los casos especiales se describen en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="ab083-105">Most of the syntax is fairly straightforward to understand; the special cases are described in the following sections.</span></span>

<span data-ttu-id="ab083-106">Cada ejemplo va seguido de un bloque de comentario que contiene el `DebugView`.</span><span class="sxs-lookup"><span data-stu-id="ab083-106">Each example is followed by a comment block containing the `DebugView`.</span></span> 

## <a name="parameterexpression"></a><span data-ttu-id="ab083-107">ParameterExpression</span><span class="sxs-lookup"><span data-stu-id="ab083-107">ParameterExpression</span></span>

<span data-ttu-id="ab083-108">Los nombres de variable <xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> se muestran con un símbolo "$" al principio.</span><span class="sxs-lookup"><span data-stu-id="ab083-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="ab083-109">Si un parámetro no tiene un nombre, se le asigna un nombre generado automáticamente, como `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="ab083-109">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="ab083-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ab083-110">Examples</span></span>

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

## <a name="constantexpressions"></a><span data-ttu-id="ab083-111">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="ab083-111">ConstantExpressions</span></span>

<span data-ttu-id="ab083-112">Para los objetos <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> que representan valores enteros, cadenas y `null`, se muestra el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="ab083-112">For <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

<span data-ttu-id="ab083-113">Para algunos tipos numéricos, se agrega un sufijo para el valor:</span><span class="sxs-lookup"><span data-stu-id="ab083-113">For some numeric types, a suffix is added to the value:</span></span>

| <span data-ttu-id="ab083-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="ab083-114">Type</span></span> | <span data-ttu-id="ab083-115">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="ab083-115">Keyword</span></span> | <span data-ttu-id="ab083-116">Sufijo</span><span class="sxs-lookup"><span data-stu-id="ab083-116">Suffix</span></span> |  
|--|--|--|
| <xref:System.UInt32> | [<span data-ttu-id="ab083-117">UInteger</span><span class="sxs-lookup"><span data-stu-id="ab083-117">UInteger</span></span>](../../../language-reference/data-types/uinteger-data-type.md) | <span data-ttu-id="ab083-118">U</span><span class="sxs-lookup"><span data-stu-id="ab083-118">U</span></span> |
| <xref:System.Int64> | [<span data-ttu-id="ab083-119">Long</span><span class="sxs-lookup"><span data-stu-id="ab083-119">Long</span></span>](../../../language-reference/data-types/long-data-type.md) | <span data-ttu-id="ab083-120">L</span><span class="sxs-lookup"><span data-stu-id="ab083-120">L</span></span> |
| <xref:System.UInt64> | [<span data-ttu-id="ab083-121">ULong</span><span class="sxs-lookup"><span data-stu-id="ab083-121">ULong</span></span>](../../../language-reference/data-types/ulong-data-type.md) | <span data-ttu-id="ab083-122">UL</span><span class="sxs-lookup"><span data-stu-id="ab083-122">UL</span></span> |
| <xref:System.Double> | [<span data-ttu-id="ab083-123">Double</span><span class="sxs-lookup"><span data-stu-id="ab083-123">Double</span></span>](../../../language-reference/data-types/double-data-type.md) | <span data-ttu-id="ab083-124">D</span><span class="sxs-lookup"><span data-stu-id="ab083-124">D</span></span> |
| <xref:System.Single> | [<span data-ttu-id="ab083-125">Single</span><span class="sxs-lookup"><span data-stu-id="ab083-125">Single</span></span>](../../../language-reference/data-types/single-data-type.md) | <span data-ttu-id="ab083-126">F</span><span class="sxs-lookup"><span data-stu-id="ab083-126">F</span></span> | 
| <xref:System.Decimal> | [<span data-ttu-id="ab083-127">Decimal</span><span class="sxs-lookup"><span data-stu-id="ab083-127">Decimal</span></span>](../../../language-reference/data-types/decimal-data-type.md) | <span data-ttu-id="ab083-128">M</span><span class="sxs-lookup"><span data-stu-id="ab083-128">M</span></span> |

### <a name="examples"></a><span data-ttu-id="ab083-129">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ab083-129">Examples</span></span>

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

## <a name="blockexpression"></a><span data-ttu-id="ab083-130">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="ab083-130">BlockExpression</span></span>

<span data-ttu-id="ab083-131">Si el tipo de un <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> objeto difiere del tipo de la última expresión del bloque, se muestra el tipo dentro de corchetes angulares (`<` y `>`).</span><span class="sxs-lookup"><span data-stu-id="ab083-131">If the type of a <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> object differs from the type of the last expression in the block, the type is displayed within angle brackets (`<` and `>`).</span></span> <span data-ttu-id="ab083-132">De otro modo, el tipo del objeto <xref:System.Linq.Expressions.BlockExpression> no se muestra.</span><span class="sxs-lookup"><span data-stu-id="ab083-132">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="ab083-133">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ab083-133">Examples</span></span>

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

## <a name="lambdaexpression"></a><span data-ttu-id="ab083-134">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="ab083-134">LambdaExpression</span></span>

<span data-ttu-id="ab083-135">Los objetos <xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> se muestran junto con sus tipos delegados.</span><span class="sxs-lookup"><span data-stu-id="ab083-135"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="ab083-136">Si una expresión lambda no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="ab083-136">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="ab083-137">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ab083-137">Examples</span></span>

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

## <a name="labelexpression"></a><span data-ttu-id="ab083-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="ab083-138">LabelExpression</span></span>

<span data-ttu-id="ab083-139">Si especifica un valor predeterminado para el objeto <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType>, este valor se muestra antes del objeto <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ab083-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="ab083-140">El token `.Label` indica el inicio de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="ab083-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="ab083-141">El token `.LabelTarget` indica el destino al que se va a saltar.</span><span class="sxs-lookup"><span data-stu-id="ab083-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="ab083-142">Si una etiqueta no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="ab083-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="ab083-143">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ab083-143">Examples</span></span>

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

## <a name="checked-operators"></a><span data-ttu-id="ab083-144">Operadores activados</span><span class="sxs-lookup"><span data-stu-id="ab083-144">Checked Operators</span></span>

<span data-ttu-id="ab083-145">Operadores activados se muestran con el `#` símbolo delante del operador.</span><span class="sxs-lookup"><span data-stu-id="ab083-145">Checked operators are displayed with the `#` symbol in front of the operator.</span></span> <span data-ttu-id="ab083-146">Por ejemplo, el operador de adición activado se muestra como `#+`.</span><span class="sxs-lookup"><span data-stu-id="ab083-146">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="ab083-147">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ab083-147">Examples</span></span>

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