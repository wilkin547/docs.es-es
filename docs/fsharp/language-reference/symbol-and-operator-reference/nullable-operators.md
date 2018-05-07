---
title: Operadores que aceptan valores NULL (F#)
description: 'Obtenga información acerca de los operadores que aceptan valores null que están disponibles en el lenguaje de programación de F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 63ad7da2d584b96eee8765b57fc671befbcbd38b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="nullable-operators"></a>Operadores que aceptan valores NULL

Operadores que aceptan valores NULL son operadores de aritmética o de comparación binarios que funcionan con tipos aritméticos que aceptan valores NULL en uno o ambos lados. Tipos que aceptan valores NULL surgen con frecuencia cuando se trabaja con datos de orígenes como bases de datos que permiten valores NULL en lugar de valores reales. Operadores que aceptan valores NULL se utilizan con frecuencia en las expresiones de consulta. Además de los operadores que aceptan valores NULL para aritméticas y de comparación, se pueden utilizar operadores de conversión para convertir entre tipos que aceptan valores NULL. También hay versiones que aceptan valores NULL de ciertos operadores de consulta.


## <a name="table-of-nullable-operators"></a>Tabla de operadores que aceptan valores null
En la tabla siguiente se enumera los operadores que aceptan valores NULL admitidos en el lenguaje F #.

|Que aceptan valores NULL a la izquierda|Que aceptan valores NULL a derecha|Ambos lados que aceptan valores null|
|---|---|---|
|[?>=](https://msdn.microsoft.com/library/94d29e32-a204-4f60-a527-6b0af86268f3)|[>=?](https://msdn.microsoft.com/library/0a255d8e-8cae-4160-ae61-243a5d96583f)|[?>=?](https://msdn.microsoft.com/library/3051a50f-d276-4c84-9d73-bf2efeddef94)|
|[?>](https://msdn.microsoft.com/library/62dc0021-1312-4ac3-be87-798b60b81bb6)|[>?](https://msdn.microsoft.com/library/0ad1284b-de48-4a04-83d8-b6f13c9c8936)|[?>?](https://msdn.microsoft.com/library/dc18b6fa-30c4-47b0-9057-794439378a05)|
|[?<=](https://msdn.microsoft.com/library/56fddf0a-e4ca-4891-a3be-fad1876be3b6)|[<=?](https://msdn.microsoft.com/library/02454a0f-30ca-4e77-ad84-ee7837461804)|[?<=?](https://msdn.microsoft.com/library/5c37c28c-0b57-4da5-be11-5a123f7e8ee4)|
|[?<](https://msdn.microsoft.com/library/b71897f0-6e29-4c58-b0a7-a5bfa6f88917)|[<?](https://msdn.microsoft.com/library/be9ea40f-a67f-4e98-8067-a14046752e8b)|[?<?](https://msdn.microsoft.com/library/6f1962c8-5605-468c-94ae-f379ae98e17d)|
|[?=](https://msdn.microsoft.com/library/5cdc8ff6-244b-49cf-9376-69ecf249fd7c)|[=?](https://msdn.microsoft.com/library/d2102894-6a51-475d-890a-735568c31f87)|[?=?](https://msdn.microsoft.com/library/5f793f29-1084-4570-b1c1-17c1b7ef764b)|
|[?<>](https://msdn.microsoft.com/library/3643a5a8-2ea5-4ad6-82c4-83927c3884a0)|[<>?](https://msdn.microsoft.com/library/3179aace-70c4-4911-9258-619592214976)|[?<>?](https://msdn.microsoft.com/library/5da813d8-ee75-45b8-9ef4-146dcb6d394d)|
|[?+](https://msdn.microsoft.com/library/2e8ddd05-b3f3-41b3-9d73-938d9e540f3f)|[+?](https://msdn.microsoft.com/library/74772ea8-f010-493e-bdb5-ba347f2fd4f1)|[?+?](https://msdn.microsoft.com/library/57f28137-0f42-43d2-92af-cad8c6c9d05f)|
|[?-](https://msdn.microsoft.com/library/f237a7a6-89f2-48b2-a2fe-f0b98a2bedc2)|[-?](https://msdn.microsoft.com/library/4a345c07-314a-48f1-b557-ce072583589c)|[?-?](https://msdn.microsoft.com/library/e0024142-1d2a-4607-a39c-1eb1e86fa25a)|
|[?*](https://msdn.microsoft.com/library/519da708-5ad6-4075-9d74-d00441cd6078)|[*?](https://msdn.microsoft.com/library/04c47870-de7b-480d-98a0-f47593b4ffac)|[?*?](https://msdn.microsoft.com/library/e57057ba-9c3a-40ec-8401-150c2b25f75b)|
|[?/](https://msdn.microsoft.com/library/add02a42-f556-40a7-a168-fbf2053322e3)|[/?](https://msdn.microsoft.com/library/1de07646-3778-476d-8c61-5d37495d463c)|[?/?](https://msdn.microsoft.com/library/b17be0ac-bf98-4590-861d-a4dd6c6fa535)|
|[?%](https://msdn.microsoft.com/library/44297bba-1bd9-4ed2-a848-f1e1e598db87)|[%?](https://msdn.microsoft.com/library/a4c178e5-eec4-42e8-847f-90b24fc609fe)|[?%?](https://msdn.microsoft.com/library/dd555f20-1be3-4b8d-81f1-bf1921e62fda)|

## <a name="remarks"></a>Comentarios
Los operadores que aceptan valores NULL se incluyen en el [NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007) módulo en el espacio de nombres [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d). El tipo de datos que aceptan valores NULL es `System.Nullable<'T>`.

En las expresiones de consulta, los tipos que aceptan valores NULL surgen al seleccionar los datos de un origen de datos que admita valores NULL en lugar de valores. En una base de datos de SQL Server, cada columna de datos de una tabla tiene un atributo que indica si se permite valores NULL. Si se permite valores NULL, los datos devueltos desde la base de datos pueden contener valores null que no se representan mediante un tipo de datos primitivos como `int`, `float`, y así sucesivamente. Por lo tanto, los datos se devuelven como un `System.Nullable<int>` en lugar de `int`, y `System.Nullable<float>` en lugar de `float`. Se puede obtener el valor real de un `System.Nullable<'T>` objeto mediante el uso de la `Value` propiedad y se puede determinar si un `System.Nullable<'T>` objeto tiene un valor mediante una llamada a la `HasValue` método. Otro método útil es el `System.Nullable<'T>.GetValueOrDefault` método, que le permite obtener el valor o un valor predeterminado del tipo adecuado. El valor predeterminado es algún tipo de valor "cero", como 0, 0.0, o `false`.

Tipos que aceptan valores NULL se pueden convertir a tipos primitivos no acepta valores NULL mediante los operadores de conversión habituales como `int` o `float`. También es posible convertir de un tipo que acepta valores NULL a otro tipo que acepta valores NULL mediante el uso de los operadores de conversión de tipos que aceptan valores NULL. Los operadores de conversión apropiado tienen el mismo nombre que los estándares, pero están en un módulo independiente, el [Nullable](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e) módulo en el [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d) espacio de nombres. Por lo general, este espacio de nombres se abra cuando se trabaja con expresiones de consulta. En ese caso, puede usar los operadores de conversión que acepta valores NULL agregando el prefijo `Nullable.` al operador de conversión apropiado, como se muestra en el código siguiente.

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn "%f" (float nullableFloat)
```

El resultado es `10.000000`

En los campos de datos que aceptan valores NULL, los operadores de consulta como `sumByNullable`, también existen para su uso en expresiones de consulta. Los operadores de consulta para los tipos que no aceptan valores NULL no son tipo compatible con tipos que aceptan valores NULL, por lo que debe usar la versión que acepta valores NULL del operador de consulta adecuada cuando se trabaja con valores de datos que aceptan valores NULL. Para obtener más información, consulte [expresiones de consulta](../query-expressions.md).

En el ejemplo siguiente se muestra el uso de operadores que aceptan valores NULL en una expresión de consulta de F #. La primera consulta muestra cómo escribir una consulta sin un operador que aceptan valores NULL. la segunda consulta muestra una consulta equivalente que usa un operador que aceptan valores NULL. Para el contexto completo, incluido cómo configurar la base de datos para usar este código de ejemplo, vea [Tutorial: obtener acceso a una base de datos SQL mediante proveedores de tipo](../../tutorials/type-providers/accessing-a-sql-database.md).

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
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
    for row in db.Table2 do
    // Use a nullable operator ?>
    where (row.TestData1 ?> 2)
    select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="see-also"></a>Vea también

[Proveedores de tipos](../../tutorials/type-providers/index.md)

[Expresiones de consulta](../query-expressions.md)
