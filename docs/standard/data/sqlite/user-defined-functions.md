---
title: Funciones definidas por el usuario
ms.date: 12/13/2019
description: Aprenda a crear funciones escalares y de agregado definidas por el usuario.
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450415"
---
# <a name="user-defined-functions"></a>Funciones definidas por el usuario

La mayoría de las bases de datos tienen un dialecto de procedimientos de SQL que puede usar para definir sus propias funciones. Sin embargo, SQLite se ejecuta en proceso con la aplicación. En lugar de tener que aprender un nuevo dialecto de SQL, puede usar simplemente el lenguaje de programación de la aplicación.

## <a name="scalar-functions"></a>Funciones escalares

Las funciones escalares devuelven un único valor escalar para cada fila de una consulta. Defina nuevas funciones escalares e invalide las integradas mediante <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.

Vea [tipos de datos](types.md) para obtener una lista de parámetros admitidos y tipos de valor devueltos para el argumento `func`.

Especificar el `state` argumento pasará ese valor a cada invocación de la función. Úselo para evitar cierres.

Especifique `isDeterministic` si la función es determinista para permitir que SQLite use optimizaciones adicionales al compilar las consultas.

En el ejemplo siguiente se muestra cómo agregar una función escalar para calcular el radio de un cilindro.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a>Operadores

Las funciones escalares correspondientes implementan los siguientes operadores de SQLite. Al definir estas funciones escalares en la aplicación, se invalidará el comportamiento de estos operadores.

| "??"          | Función      |
| ----------------- | ------------- |
| X GLOB Y          | Glob (Y, X)    |
| X LIKE Y          | like (Y, X)    |
| X LIKE Y ESCAPE Z | like (Y, X, Z) |
| X COINCIDE Y         | coincidencia (Y, X)   |
| X REGEXP Y        | RegExp (Y, X)  |

En el ejemplo siguiente se muestra cómo definir la función RegExp para habilitar su operador correspondiente. SQLite no incluye una implementación predeterminada de la función RegExp.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a>Funciones de agregado

Las funciones de agregado devuelven un único valor agregado para todas las filas de una consulta. Defina e invalide las funciones de agregado mediante <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.

El argumento `seed` especifica el estado inicial del contexto. Úselo también para evitar cierres.

El argumento `func` se invoca una vez por cada fila. Use el contexto para acumular un resultado final. Devuelve el contexto. Este patrón permite que el contexto sea un tipo de valor o inmutable.

Si no se especifica ningún `resultSelector`, el estado final del contexto se utiliza como resultado. Esto puede simplificar la definición de funciones como SUM y Count que solo necesitan incrementar un número cada fila y devolverlo.

Especifique `resultSelector` para calcular el resultado final del contexto después de recorrer en iteración todas las filas.

Vea [tipos de datos](types.md) para obtener una lista de los tipos de parámetro admitidos para el argumento `func` y los tipos de valor devueltos para `resultSelector`.

Si la función es determinista, especifique `isDeterministic` para permitir que SQLite use optimizaciones adicionales al compilar las consultas.

En el ejemplo siguiente se define una función de agregado para calcular la desviación estándar de una columna.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a>Errores de

Si una función definida por el usuario produce una excepción, el mensaje se devuelve a SQLite. SQLite producirá un error y Microsoft. Data. SQLite producirá un SqliteException. Para obtener más información, vea [errores de base de datos](database-errors.md).

De forma predeterminada, el código de error de SQLite de error se SQLITE_ERROR (o 1). Sin embargo, puede cambiarlo iniciando una <xref:Microsoft.Data.Sqlite.SqliteException> en la función con el <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> deseado especificado.

## <a name="debugging"></a>Depuración

SQLite llama directamente a su implementación. Esto le permite agregar puntos de interrupción que se desencadenan mientras SQLite está evaluando consultas. La experiencia completa de depuración de .NET está disponible para ayudarle a crear funciones definidas por el usuario.

## <a name="see-also"></a>Vea también

* [Tipos de datos](types.md)
* [Funciones principales de SQLite](https://www.sqlite.org/lang_corefunc.html)
* [Funciones de agregado de SQLite](https://www.sqlite.org/lang_aggfunc.html)
