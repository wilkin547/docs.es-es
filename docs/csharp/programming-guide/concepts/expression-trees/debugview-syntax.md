---
title: Sintaxis que utiliza la propiedad DebugView (C#)
description: Describe la sintaxis especial usada por la propiedad DebugView para producir una representación de cadena de árboles de expresión
author: zspitz
ms.author: wiwagn
ms.date: 02/14/2021
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 278fc66f9f8cf7671b956126cec10c4464a5b81c
ms.sourcegitcommit: 456b3cd82a87b453fa737b4661295070d1b6d684
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "100639394"
---
# <a name="debugview-syntax"></a><span data-ttu-id="24e63-103">Sintaxis de **DebugView**</span><span class="sxs-lookup"><span data-stu-id="24e63-103">**DebugView** syntax</span></span>

<span data-ttu-id="24e63-104">La propiedad **DebugView** (disponible solo durante la depuración) proporciona una representación de cadenas de árboles de expresión.</span><span class="sxs-lookup"><span data-stu-id="24e63-104">The **DebugView** property (available only when debugging) provides a string rendering of expression trees.</span></span> <span data-ttu-id="24e63-105">La mayor parte de la sintaxis es bastante sencilla de entender; los casos especiales se describen en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="24e63-105">Most of the syntax is fairly straightforward to understand; the special cases are described in the following sections.</span></span>

<span data-ttu-id="24e63-106">Cada ejemplo va seguido de un comentario del bloque, que contiene **DebugView**.</span><span class="sxs-lookup"><span data-stu-id="24e63-106">Each example is followed by a block comment, containing the **DebugView**.</span></span>

## <a name="parameterexpression"></a><span data-ttu-id="24e63-107">ParameterExpression</span><span class="sxs-lookup"><span data-stu-id="24e63-107">ParameterExpression</span></span>

<span data-ttu-id="24e63-108">los nombres de variable <xref:System.Linq.Expressions.ParameterExpression> se muestran con un símbolo `$` al principio.</span><span class="sxs-lookup"><span data-stu-id="24e63-108"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a `$` symbol at the beginning.</span></span>

<span data-ttu-id="24e63-109">Si un parámetro no tiene un nombre, se le asigna un nombre generado automáticamente, como `$var1` o `$var2`.</span><span class="sxs-lookup"><span data-stu-id="24e63-109">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="24e63-110">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="24e63-110">Examples</span></span>

```csharp
ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");
/*
    $num
*/

ParameterExpression numParam =  Expression.Parameter(typeof(int));
/*
    $var1
*/
```

## <a name="constantexpression"></a><span data-ttu-id="24e63-111">ConstantExpression</span><span class="sxs-lookup"><span data-stu-id="24e63-111">ConstantExpression</span></span>

<span data-ttu-id="24e63-112">Para los objetos <xref:System.Linq.Expressions.ConstantExpression> que representan valores enteros, cadenas y `null`, se muestra el valor de la constante.</span><span class="sxs-lookup"><span data-stu-id="24e63-112">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

<span data-ttu-id="24e63-113">Para los tipos numéricos que tienen sufijos estándar como literales de C#, el sufijo se agrega al valor.</span><span class="sxs-lookup"><span data-stu-id="24e63-113">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="24e63-114">En la tabla siguiente se muestran los sufijos asociados a varios tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="24e63-114">The following table shows the suffixes associated with various numeric types.</span></span>

| <span data-ttu-id="24e63-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="24e63-115">Type</span></span> | <span data-ttu-id="24e63-116">Palabra clave</span><span class="sxs-lookup"><span data-stu-id="24e63-116">Keyword</span></span> | <span data-ttu-id="24e63-117">Sufijo</span><span class="sxs-lookup"><span data-stu-id="24e63-117">Suffix</span></span> |
|--|--|--|
| <xref:System.UInt32?displayProperty=nameWithType> | [<span data-ttu-id="24e63-118">uint</span><span class="sxs-lookup"><span data-stu-id="24e63-118">uint</span></span>](../../../language-reference/builtin-types/integral-numeric-types.md) | <span data-ttu-id="24e63-119">U</span><span class="sxs-lookup"><span data-stu-id="24e63-119">U</span></span> |
| <xref:System.Int64?displayProperty=nameWithType> | [<span data-ttu-id="24e63-120">long</span><span class="sxs-lookup"><span data-stu-id="24e63-120">long</span></span>](../../../language-reference/builtin-types/integral-numeric-types.md) | <span data-ttu-id="24e63-121">L</span><span class="sxs-lookup"><span data-stu-id="24e63-121">L</span></span> |
| <xref:System.UInt64?displayProperty=nameWithType> | [<span data-ttu-id="24e63-122">ulong</span><span class="sxs-lookup"><span data-stu-id="24e63-122">ulong</span></span>](../../../language-reference/builtin-types/integral-numeric-types.md) | <span data-ttu-id="24e63-123">UL</span><span class="sxs-lookup"><span data-stu-id="24e63-123">UL</span></span> |
| <xref:System.Double?displayProperty=nameWithType> | [<span data-ttu-id="24e63-124">double</span><span class="sxs-lookup"><span data-stu-id="24e63-124">double</span></span>](../../../language-reference/builtin-types/floating-point-numeric-types.md) | <span data-ttu-id="24e63-125">D</span><span class="sxs-lookup"><span data-stu-id="24e63-125">D</span></span> |
| <xref:System.Single?displayProperty=nameWithType> | [<span data-ttu-id="24e63-126">float</span><span class="sxs-lookup"><span data-stu-id="24e63-126">float</span></span>](../../../language-reference/builtin-types/floating-point-numeric-types.md) | <span data-ttu-id="24e63-127">F</span><span class="sxs-lookup"><span data-stu-id="24e63-127">F</span></span> |
| <xref:System.Decimal?displayProperty=nameWithType> | [<span data-ttu-id="24e63-128">decimal</span><span class="sxs-lookup"><span data-stu-id="24e63-128">decimal</span></span>](../../../language-reference/builtin-types/floating-point-numeric-types.md) | <span data-ttu-id="24e63-129">M</span><span class="sxs-lookup"><span data-stu-id="24e63-129">M</span></span> |

### <a name="examples"></a><span data-ttu-id="24e63-130">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="24e63-130">Examples</span></span>

```csharp
int num = 10;
ConstantExpression expr = Expression.Constant(num);
/*
    10
*/

double num = 10;
ConstantExpression expr = Expression.Constant(num);
/*
    10D
*/
```

## <a name="blockexpression"></a><span data-ttu-id="24e63-131">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="24e63-131">BlockExpression</span></span>

<span data-ttu-id="24e63-132">Si el tipo de un objeto <xref:System.Linq.Expressions.BlockExpression> difiere del tipo de la última expresión del bloque, el tipo se muestra entre corchetes angulares (`<` y `>`).</span><span class="sxs-lookup"><span data-stu-id="24e63-132">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed within angle brackets (`<` and `>`).</span></span> <span data-ttu-id="24e63-133">De otro modo, el tipo del objeto <xref:System.Linq.Expressions.BlockExpression> no se muestra.</span><span class="sxs-lookup"><span data-stu-id="24e63-133">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="24e63-134">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="24e63-134">Examples</span></span>

```csharp
BlockExpression block = Expression.Block(Expression.Constant("test"));
/*
    .Block() {
        "test"
    }
*/

BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));
/*
    .Block<System.Object>() {
        "test"
    }
*/
```

## <a name="lambdaexpression"></a><span data-ttu-id="24e63-135">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="24e63-135">LambdaExpression</span></span>

<span data-ttu-id="24e63-136">Los objetos <xref:System.Linq.Expressions.LambdaExpression> se muestran junto con sus tipos delegados.</span><span class="sxs-lookup"><span data-stu-id="24e63-136"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="24e63-137">Si una expresión lambda no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Lambda1` o `#Lambda2`.</span><span class="sxs-lookup"><span data-stu-id="24e63-137">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="24e63-138">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="24e63-138">Examples</span></span>

```csharp
LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));
/*
    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
        1
    }
*/

LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);
/*
    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
        1
    }
*/
```

## <a name="labelexpression"></a><span data-ttu-id="24e63-139">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="24e63-139">LabelExpression</span></span>

<span data-ttu-id="24e63-140">Si especifica un valor predeterminado para el objeto <xref:System.Linq.Expressions.LabelExpression>, este valor se muestra antes del objeto <xref:System.Linq.Expressions.LabelTarget>.</span><span class="sxs-lookup"><span data-stu-id="24e63-140">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="24e63-141">El token `.Label` indica el inicio de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="24e63-141">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="24e63-142">El token `.LabelTarget` indica el destino al que se va a saltar.</span><span class="sxs-lookup"><span data-stu-id="24e63-142">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="24e63-143">Si una etiqueta no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Label1` o `#Label2`.</span><span class="sxs-lookup"><span data-stu-id="24e63-143">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="24e63-144">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="24e63-144">Examples</span></span>

```csharp
LabelTarget target = Expression.Label(typeof(int), "SampleLabel");
BlockExpression block = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
);
/*
    .Block() {
        .Goto SampleLabel { 0 };
        .Label
            -1
        .LabelTarget SampleLabel:
    }
*/

LabelTarget target = Expression.Label();
BlockExpression block = Expression.Block(
    Expression.Goto(target),
    Expression.Label(target)
);
/*
    .Block() {
        .Goto #Label1 { };
        .Label
        .LabelTarget #Label1:
    }
*/
```

## <a name="checked-operators"></a><span data-ttu-id="24e63-145">Operadores activados</span><span class="sxs-lookup"><span data-stu-id="24e63-145">Checked Operators</span></span>

<span data-ttu-id="24e63-146">Los operadores activados se muestran con el símbolo `#` delante del operador.</span><span class="sxs-lookup"><span data-stu-id="24e63-146">Checked operators are displayed with the `#` symbol in front of the operator.</span></span> <span data-ttu-id="24e63-147">Por ejemplo, el operador de adición activado se muestra como `#+`.</span><span class="sxs-lookup"><span data-stu-id="24e63-147">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="24e63-148">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="24e63-148">Examples</span></span>

```csharp
Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));
/*
    1 #+ 2
*/

Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));
/*
    #(System.Int32)10D
*/
```
