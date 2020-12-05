---
title: Operadores que aceptan valores NULL
description: 'Obtenga información sobre los operadores que aceptan valores NULL que están disponibles en el lenguaje de programación F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 9ac6afc2c3f4277ee6e93b1ccb3d21f892926b4b
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740372"
---
# <a name="nullable-operators"></a>Operadores que aceptan valores NULL

Los operadores que aceptan valores NULL son operadores aritméticos o de comparación binarios que funcionan con tipos aritméticos que aceptan valores NULL en uno o ambos lados. Los tipos que aceptan valores NULL se producen con frecuencia cuando se trabaja con datos de orígenes como bases de datos que permiten valores NULL en lugar de valores reales. Los operadores que aceptan valores NULL se utilizan con frecuencia en expresiones de consulta. Además de los operadores que aceptan valores NULL para operaciones aritméticas y de comparación, los operadores de conversión se pueden usar para realizar conversiones entre tipos que aceptan valores NULL. También hay versiones que aceptan valores NULL de ciertos operadores de consulta.

## <a name="table-of-nullable-operators"></a>Tabla de operadores que aceptan valores NULL

En la tabla siguiente se enumeran los operadores que aceptan valores NULL que se admiten en el lenguaje F #.

|Acepta valores NULL a la izquierda|Acepta valores NULL a la derecha|Ambos lados aceptan valores NULL|
|---|---|---|
|[? >=](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E=%20))|[>=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3E=?%20))|[? >=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E=?%20))|
|[? >](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E%20))|[ ¿>?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3E?%20))|[? >?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E?%20))|
|[? <=](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C=%20))|[<=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3C=?%20))|[? <=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C=?%20))|
|[? <](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C%20))|[ ¿<?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3C?%20))|[? <?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C?%20))|
|[?=](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?=%20))|[=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20=?%20))|[?=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?=?%20))|
|[? <>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C%3E%20))|[ ¿<>?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3C%3E?%20))|[? <>?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C%3E?%20))|
|[?+](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?+%20))|[+?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20+?%20))|[?+?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?+?%20))|
|[?-](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?-%20))|[-?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20-?%20))|[?-?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?-?%20))|
|[?*](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?*%20))|[*?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20*?%20))|[?*?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?*?%20))|
|[?/](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?/%20))|[/?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20/?%20))|[?/?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?/?%20))|
|[?%](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%%20))|[%?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%?%20))|[?%?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%?%20))|

## <a name="remarks"></a>Comentarios

Los operadores que aceptan valores NULL se incluyen en el módulo [NullableOperators](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html) en el espacio de nombres [FSharp. Linq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq.html). El tipo de los datos que aceptan valores NULL es `System.Nullable<'T>` .

En las expresiones de consulta, los tipos que aceptan valores NULL se producen cuando se seleccionan datos de un origen de datos que permite valores NULL en lugar de valores. En una base de datos de SQL Server, cada columna de datos de una tabla tiene un atributo que indica si se permiten valores NULL. Si se permiten valores NULL, los datos devueltos por la base de datos pueden contener valores NULL que no pueden representarse mediante un tipo de datos primitivo como `int` , `float` , etc. Por lo tanto, los datos se devuelven como `System.Nullable<int>` en lugar de `int` , y `System.Nullable<float>` en lugar de `float` . El valor real se puede obtener de un `System.Nullable<'T>` objeto mediante la `Value` propiedad, y se puede determinar si un `System.Nullable<'T>` objeto tiene un valor llamando al `HasValue` método. Otro método útil es el `System.Nullable<'T>.GetValueOrDefault` método, que permite obtener el valor o un valor predeterminado del tipo adecuado. El valor predeterminado es alguna forma de valor "cero", como 0, 0,0 o `false` .

Los tipos que aceptan valores NULL se pueden convertir en tipos primitivos que no aceptan valores NULL mediante los operadores de conversión habituales, como `int` o `float` . También es posible convertir de un tipo que acepta valores NULL a otro tipo que acepta valores NULL mediante los operadores de conversión para tipos que aceptan valores NULL. Los operadores de conversión adecuados tienen el mismo nombre que los estándar, pero se encuentran en un módulo independiente, el módulo que [acepta valores NULL](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullablemodule.html) en el espacio de nombres [FSharp. Linq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq.html) . Normalmente, se abre este espacio de nombres cuando se trabaja con expresiones de consulta. En ese caso, puede usar los operadores de conversión que aceptan valores NULL agregando el prefijo `Nullable.` al operador de conversión adecuado, tal y como se muestra en el código siguiente.

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn $"%f{float nullableFloat}"
```

La salida es `10.000000`.

Los operadores de consulta en campos de datos que aceptan valores NULL, como `sumByNullable` , también existen para su uso en expresiones de consulta. Los operadores de consulta para tipos que no aceptan valores NULL no son compatibles con tipos que aceptan valores NULL, por lo que debe usar la versión que acepta valores NULL del operador de consulta adecuado cuando se trabaja con valores de datos que aceptan valores NULL. Para obtener más información, vea [expresiones de consulta](../query-expressions.md).

En el ejemplo siguiente se muestra el uso de operadores que aceptan valores NULL en una expresión de consulta de F #. La primera consulta muestra cómo se escribiría una consulta sin un operador que acepta valores NULL; la segunda consulta muestra una consulta equivalente que utiliza un operador que acepta valores NULL. En el contexto completo, incluido cómo configurar la base de datos para usar este código de ejemplo, vea [Tutorial: acceso a un SQL Database mediante proveedores de tipos](../../tutorials/type-providers/index.md).

```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq

[<Generate>]
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">

let db = dbSchema.GetDataContext()

query {
    for row in db.Table2 do
    where (row.TestData1.HasValue && row.TestData1.Value > 2)
    select row
} |> Seq.iter (fun row -> printfn $"%d{row.TestData1.Value} %s{row.Name}")

query {
    for row in db.Table2 do
    // Use a nullable operator ?>
    where (row.TestData1 ?> 2)
    select row
} |> Seq.iter (fun row -> printfn "%d{row.TestData1.GetValueOrDefault()} %s{row.Name}")
```

## <a name="see-also"></a>Consulte también

- [Proveedores de tipos](../../tutorials/type-providers/index.md)
- [Expresiones de consulta](../query-expressions.md)
