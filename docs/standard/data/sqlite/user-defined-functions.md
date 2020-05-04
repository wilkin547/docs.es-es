---
title: Funciones definidas por el usuario
ms.date: 12/13/2019
description: Obtenga información sobre cómo crear funciones escalares y de agregado definidas por el usuario.
ms.openlocfilehash: 9ee3fbac73215353c8dc82199203b0d25e580cdb
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450415"
---
# <a name="user-defined-functions"></a>Funciones definidas por el usuario

La mayoría de las bases de datos tienen un dialecto de procedimientos de SQL que puede usar para definir sus propias funciones. SQLite, en cambio, se ejecuta en el mismo proceso que la aplicación. Así, en lugar de tener que aprender un nuevo dialecto de SQL, se puede usar simplemente el lenguaje de programación de la aplicación en cuestión.

## <a name="scalar-functions"></a>Funciones escalares

Las funciones escalares devuelven un único valor escalar por cada fila de una consulta. Use <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A> para definir nuevas funciones escalares e invalidar las que estén integradas.

Vea [Tipos de datos](types.md) para obtener una lista de los tipos de parámetro y de valor devuelto admitidos en el argumento `func`.

Si se especifica el argumento `state`, ese valor se pasará a cada invocación de la función. Recurra a este método para evitar cierres.

Si la función es determinista, especifique `isDeterministic` para permitir que SQLite use más optimizaciones al compilar consultas.

En el siguiente ejemplo se muestra cómo agregar una función escalar para calcular el radio de un cilindro.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a>Operadores

Los siguientes operadores de SQLite se implementan a través de las funciones escalares correspondientes. Al definir estas funciones escalares en la aplicación, el comportamiento de estos operadores se invalidará.

| Operador          | Función      |
| ----------------- | ------------- |
| X GLOB Y          | glob(Y, X)    |
| X LIKE Y          | like(Y, X)    |
| X LIKE Y ESCAPE Z | like(Y, X, Z) |
| X MATCH Y         | match(Y, X)   |
| X REGEXP Y        | regexp(Y, X)  |

En el siguiente ejemplo se muestra cómo definir la función RegExp para habilitar su operador correspondiente. SQLite no incluye una implementación predeterminada de la función RegExp.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a>Funciones de agregado

Las funciones de agregado devuelven un único valor agregado para todas las filas de una consulta. Use <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A> para definir e invalidar funciones de agregado.

El argumento `seed` especifica el estado inicial del contexto. Recurra a este método también para evitar cierres.

El argumento `func` se invoca una vez por cada fila. Use el contexto para acumular un resultado final. Devuelva el contexto. Este patrón permite que el contexto sea un tipo de valor o inmutable.

Si no se especifica ningún elemento `resultSelector`, se usa como resultado el estado final del contexto. Esto puede simplificar la definición de funciones como SUM y COUNT, donde solo es necesario aumentar un número cada fila y devolver el valor correspondiente.

Especifique `resultSelector` para calcular el resultado final del contexto después de recorrer en iteración todas las filas.

Vea [Tipos de datos](types.md) para obtener una lista de los tipos de parámetro del argumento `func` y los tipos devueltos de `resultSelector`.

Si la función es determinista, especifique `isDeterministic` para permitir que SQLite use más optimizaciones al compilar consultas.

En el siguiente ejemplo se define una función de agregado para calcular la desviación estándar de una columna.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a>Errores

Si una función definida por el usuario produce una excepción, el mensaje se devuelve a SQLite. Tras ello, SQLite producirá un error y Microsoft.Data.Sqlite producirá una excepción SqliteException. Para más información, vea [Errores de base de datos](database-errors.md).

El código de error del error de SQLite será de forma predeterminada SQLITE_ERROR (o 1), pero se puede cambiar produciendo una excepción <xref:Microsoft.Data.Sqlite.SqliteException> en la función con el elemento <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> deseado especificado.

## <a name="debugging"></a>Depuración

SQLite llama directamente a su implementación, lo que le permite agregar puntos de interrupción que se desencadenan mientras SQLite está evaluando consultas. La experiencia de depuración completa de .NET está disponible para ayudarle a crear funciones definidas por el usuario.

## <a name="see-also"></a>Vea también

* [Tipos de datos](types.md)
* [Funciones principales de SQLite](https://www.sqlite.org/lang_corefunc.html)
* [Funciones de agregado de SQLite](https://www.sqlite.org/lang_aggfunc.html)
