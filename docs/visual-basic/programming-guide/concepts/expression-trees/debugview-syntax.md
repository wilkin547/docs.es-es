---
title: Sintaxis usada por la propiedad DebugView
description: Describe la sintaxis especial usada por la propiedad DebugView para producir una representación de cadena de árboles de expresión
author: zspitz
ms.author: wiwagn
ms.date: 02/14/2021
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 1b6d117bb1ce0cb13344c72be3b55742c443448f
ms.sourcegitcommit: 456b3cd82a87b453fa737b4661295070d1b6d684
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "100639194"
---
# <a name="debugview-syntax"></a>Sintaxis de **DebugView**

La propiedad **DebugView** (disponible solo al depurar) proporciona una representación de cadena de los árboles de expresión. La mayor parte de la sintaxis es bastante sencilla de entender; los casos especiales se describen en las siguientes secciones.

Cada ejemplo va seguido de un bloque de comentario que contiene **DebugView**.

## <a name="parameterexpression"></a>ParameterExpression

Los nombres de variable <xref:System.Linq.Expressions.ParameterExpression> se muestran con un símbolo "$" al principio.

Si un parámetro no tiene un nombre, se le asigna un nombre generado automáticamente, como `$var1` o `$var2`.

### <a name="examples"></a>Ejemplos

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

## <a name="constantexpressions"></a>ConstantExpressions

Para los objetos <xref:System.Linq.Expressions.ConstantExpression> que representan valores enteros, cadenas y `null`, se muestra el valor de la constante.

En algunos tipos numéricos, se agrega un sufijo al valor:

| Tipo | Palabra clave | Sufijo |
|--|--|--|
| <xref:System.UInt32?displayProperty=nameWithType> | [UInteger](../../../language-reference/data-types/uinteger-data-type.md) | U |
| <xref:System.Int64?displayProperty=nameWithType> | [Long](../../../language-reference/data-types/long-data-type.md) | L |
| <xref:System.UInt64?displayProperty=nameWithType> | [ULong](../../../language-reference/data-types/ulong-data-type.md) | UL |
| <xref:System.Double?displayProperty=nameWithType> | [Double](../../../language-reference/data-types/double-data-type.md) | D |
| <xref:System.Single?displayProperty=nameWithType> | [Single](../../../language-reference/data-types/single-data-type.md) | F |
| <xref:System.Decimal?displayProperty=nameWithType> | [Decimal](../../../language-reference/data-types/decimal-data-type.md) | M |

### <a name="examples"></a>Ejemplos

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

## <a name="blockexpression"></a>BlockExpression

Si el tipo de un objeto <xref:System.Linq.Expressions.BlockExpression> difiere del tipo de la última expresión del bloque, el tipo se muestra entre corchetes angulares (`<` y `>`). De otro modo, el tipo del objeto <xref:System.Linq.Expressions.BlockExpression> no se muestra.

### <a name="examples"></a>Ejemplos

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

## <a name="lambdaexpression"></a>LambdaExpression

Los objetos <xref:System.Linq.Expressions.LambdaExpression> se muestran junto con sus tipos delegados.

Si una expresión lambda no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Lambda1` o `#Lambda2`.

### <a name="examples"></a>Ejemplos

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

## <a name="labelexpression"></a>LabelExpression

Si especifica un valor predeterminado para el objeto <xref:System.Linq.Expressions.LabelExpression>, este valor se muestra antes del objeto <xref:System.Linq.Expressions.LabelTarget>.

El token `.Label` indica el inicio de la etiqueta. El token `.LabelTarget` indica el destino al que se va a saltar.

Si una etiqueta no tiene un nombre, se le asigna un nombre generado automáticamente, como `#Label1` o `#Label2`.

### <a name="examples"></a>Ejemplos

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

## <a name="checked-operators"></a>Operadores activados

Los operadores activados se muestran con el símbolo `#` delante del operador. Por ejemplo, el operador de adición activado se muestra como `#+`.

### <a name="examples"></a>Ejemplos

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
