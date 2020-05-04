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
# <a name="user-defined-functions"></a><span data-ttu-id="93b1d-103">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="93b1d-103">User-defined functions</span></span>

<span data-ttu-id="93b1d-104">La mayoría de las bases de datos tienen un dialecto de procedimientos de SQL que puede usar para definir sus propias funciones.</span><span class="sxs-lookup"><span data-stu-id="93b1d-104">Most databases have a procedural dialect of SQL that you can use to define your own functions.</span></span> <span data-ttu-id="93b1d-105">SQLite, en cambio, se ejecuta en el mismo proceso que la aplicación.</span><span class="sxs-lookup"><span data-stu-id="93b1d-105">SQLite however, runs in-process with your app.</span></span> <span data-ttu-id="93b1d-106">Así, en lugar de tener que aprender un nuevo dialecto de SQL, se puede usar simplemente el lenguaje de programación de la aplicación en cuestión.</span><span class="sxs-lookup"><span data-stu-id="93b1d-106">Instead of having to learn a new dialect of SQL, you can just use the programming language of your app.</span></span>

## <a name="scalar-functions"></a><span data-ttu-id="93b1d-107">Funciones escalares</span><span class="sxs-lookup"><span data-stu-id="93b1d-107">Scalar functions</span></span>

<span data-ttu-id="93b1d-108">Las funciones escalares devuelven un único valor escalar por cada fila de una consulta.</span><span class="sxs-lookup"><span data-stu-id="93b1d-108">Scalar functions return a single, scalar value for each row in a query.</span></span> <span data-ttu-id="93b1d-109">Use <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A> para definir nuevas funciones escalares e invalidar las que estén integradas.</span><span class="sxs-lookup"><span data-stu-id="93b1d-109">Define new scalar functions and override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span></span>

<span data-ttu-id="93b1d-110">Vea [Tipos de datos](types.md) para obtener una lista de los tipos de parámetro y de valor devuelto admitidos en el argumento `func`.</span><span class="sxs-lookup"><span data-stu-id="93b1d-110">See [Data types](types.md) for a list of supported parameter and return types for the `func` argument.</span></span>

<span data-ttu-id="93b1d-111">Si se especifica el argumento `state`, ese valor se pasará a cada invocación de la función.</span><span class="sxs-lookup"><span data-stu-id="93b1d-111">Specifying the `state` argument will pass that value into every invocation of the function.</span></span> <span data-ttu-id="93b1d-112">Recurra a este método para evitar cierres.</span><span class="sxs-lookup"><span data-stu-id="93b1d-112">Use this to avoid closures.</span></span>

<span data-ttu-id="93b1d-113">Si la función es determinista, especifique `isDeterministic` para permitir que SQLite use más optimizaciones al compilar consultas.</span><span class="sxs-lookup"><span data-stu-id="93b1d-113">Specify `isDeterministic` if your function is deterministic to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="93b1d-114">En el siguiente ejemplo se muestra cómo agregar una función escalar para calcular el radio de un cilindro.</span><span class="sxs-lookup"><span data-stu-id="93b1d-114">The following example shows how to add a scalar function to calculate the radius of a cylinder.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a><span data-ttu-id="93b1d-115">Operadores</span><span class="sxs-lookup"><span data-stu-id="93b1d-115">Operators</span></span>

<span data-ttu-id="93b1d-116">Los siguientes operadores de SQLite se implementan a través de las funciones escalares correspondientes.</span><span class="sxs-lookup"><span data-stu-id="93b1d-116">The following SQLite operators are implemented by corresponding scalar functions.</span></span> <span data-ttu-id="93b1d-117">Al definir estas funciones escalares en la aplicación, el comportamiento de estos operadores se invalidará.</span><span class="sxs-lookup"><span data-stu-id="93b1d-117">Defining these scalar functions in your app will override the behavior of these operators.</span></span>

| <span data-ttu-id="93b1d-118">Operador</span><span class="sxs-lookup"><span data-stu-id="93b1d-118">Operator</span></span>          | <span data-ttu-id="93b1d-119">Función</span><span class="sxs-lookup"><span data-stu-id="93b1d-119">Function</span></span>      |
| ----------------- | ------------- |
| <span data-ttu-id="93b1d-120">X GLOB Y</span><span class="sxs-lookup"><span data-stu-id="93b1d-120">X GLOB Y</span></span>          | <span data-ttu-id="93b1d-121">glob(Y, X)</span><span class="sxs-lookup"><span data-stu-id="93b1d-121">glob(Y, X)</span></span>    |
| <span data-ttu-id="93b1d-122">X LIKE Y</span><span class="sxs-lookup"><span data-stu-id="93b1d-122">X LIKE Y</span></span>          | <span data-ttu-id="93b1d-123">like(Y, X)</span><span class="sxs-lookup"><span data-stu-id="93b1d-123">like(Y, X)</span></span>    |
| <span data-ttu-id="93b1d-124">X LIKE Y ESCAPE Z</span><span class="sxs-lookup"><span data-stu-id="93b1d-124">X LIKE Y ESCAPE Z</span></span> | <span data-ttu-id="93b1d-125">like(Y, X, Z)</span><span class="sxs-lookup"><span data-stu-id="93b1d-125">like(Y, X, Z)</span></span> |
| <span data-ttu-id="93b1d-126">X MATCH Y</span><span class="sxs-lookup"><span data-stu-id="93b1d-126">X MATCH Y</span></span>         | <span data-ttu-id="93b1d-127">match(Y, X)</span><span class="sxs-lookup"><span data-stu-id="93b1d-127">match(Y, X)</span></span>   |
| <span data-ttu-id="93b1d-128">X REGEXP Y</span><span class="sxs-lookup"><span data-stu-id="93b1d-128">X REGEXP Y</span></span>        | <span data-ttu-id="93b1d-129">regexp(Y, X)</span><span class="sxs-lookup"><span data-stu-id="93b1d-129">regexp(Y, X)</span></span>  |

<span data-ttu-id="93b1d-130">En el siguiente ejemplo se muestra cómo definir la función RegExp para habilitar su operador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="93b1d-130">The following example shows how to define the regexp function to enable its corresponding operator.</span></span> <span data-ttu-id="93b1d-131">SQLite no incluye una implementación predeterminada de la función RegExp.</span><span class="sxs-lookup"><span data-stu-id="93b1d-131">SQLite doesn't include a default implementation of the regexp function.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a><span data-ttu-id="93b1d-132">Funciones de agregado</span><span class="sxs-lookup"><span data-stu-id="93b1d-132">Aggregate functions</span></span>

<span data-ttu-id="93b1d-133">Las funciones de agregado devuelven un único valor agregado para todas las filas de una consulta.</span><span class="sxs-lookup"><span data-stu-id="93b1d-133">Aggregate functions return a single, aggregated value for all the rows in a query.</span></span> <span data-ttu-id="93b1d-134">Use <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A> para definir e invalidar funciones de agregado.</span><span class="sxs-lookup"><span data-stu-id="93b1d-134">Define and override aggregate functions using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span></span>

<span data-ttu-id="93b1d-135">El argumento `seed` especifica el estado inicial del contexto.</span><span class="sxs-lookup"><span data-stu-id="93b1d-135">The `seed` argument specifies the initial state of the context.</span></span> <span data-ttu-id="93b1d-136">Recurra a este método también para evitar cierres.</span><span class="sxs-lookup"><span data-stu-id="93b1d-136">Use this to avoid closures also.</span></span>

<span data-ttu-id="93b1d-137">El argumento `func` se invoca una vez por cada fila.</span><span class="sxs-lookup"><span data-stu-id="93b1d-137">The `func` argument is invoked once per row.</span></span> <span data-ttu-id="93b1d-138">Use el contexto para acumular un resultado final.</span><span class="sxs-lookup"><span data-stu-id="93b1d-138">Use the context to accumulate a final result.</span></span> <span data-ttu-id="93b1d-139">Devuelva el contexto.</span><span class="sxs-lookup"><span data-stu-id="93b1d-139">Return the context.</span></span> <span data-ttu-id="93b1d-140">Este patrón permite que el contexto sea un tipo de valor o inmutable.</span><span class="sxs-lookup"><span data-stu-id="93b1d-140">This pattern allows the context to be a value type or immutable.</span></span>

<span data-ttu-id="93b1d-141">Si no se especifica ningún elemento `resultSelector`, se usa como resultado el estado final del contexto.</span><span class="sxs-lookup"><span data-stu-id="93b1d-141">If no `resultSelector` is specified, the final state of the context is used as the result.</span></span> <span data-ttu-id="93b1d-142">Esto puede simplificar la definición de funciones como SUM y COUNT, donde solo es necesario aumentar un número cada fila y devolver el valor correspondiente.</span><span class="sxs-lookup"><span data-stu-id="93b1d-142">This can simplify the definition of functions like sum and count that only need to increment a number each row and return it.</span></span>

<span data-ttu-id="93b1d-143">Especifique `resultSelector` para calcular el resultado final del contexto después de recorrer en iteración todas las filas.</span><span class="sxs-lookup"><span data-stu-id="93b1d-143">Specify `resultSelector` to calculate the final result from the context after iterating through all the rows.</span></span>

<span data-ttu-id="93b1d-144">Vea [Tipos de datos](types.md) para obtener una lista de los tipos de parámetro del argumento `func` y los tipos devueltos de `resultSelector`.</span><span class="sxs-lookup"><span data-stu-id="93b1d-144">See [Data types](types.md) for a list of supported parameter types for the `func` argument and return types for `resultSelector`.</span></span>

<span data-ttu-id="93b1d-145">Si la función es determinista, especifique `isDeterministic` para permitir que SQLite use más optimizaciones al compilar consultas.</span><span class="sxs-lookup"><span data-stu-id="93b1d-145">If your function is deterministic, specify `isDeterministic` to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="93b1d-146">En el siguiente ejemplo se define una función de agregado para calcular la desviación estándar de una columna.</span><span class="sxs-lookup"><span data-stu-id="93b1d-146">The following example defines an aggregate function to calculate the standard deviation of a column.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a><span data-ttu-id="93b1d-147">Errores</span><span class="sxs-lookup"><span data-stu-id="93b1d-147">Errors</span></span>

<span data-ttu-id="93b1d-148">Si una función definida por el usuario produce una excepción, el mensaje se devuelve a SQLite.</span><span class="sxs-lookup"><span data-stu-id="93b1d-148">If a user-defined function throws an exception, the message is returned to SQLite.</span></span> <span data-ttu-id="93b1d-149">Tras ello, SQLite producirá un error y Microsoft.Data.Sqlite producirá una excepción SqliteException.</span><span class="sxs-lookup"><span data-stu-id="93b1d-149">SQLite will then raise an error and Microsoft.Data.Sqlite will throw a SqliteException.</span></span> <span data-ttu-id="93b1d-150">Para más información, vea [Errores de base de datos](database-errors.md).</span><span class="sxs-lookup"><span data-stu-id="93b1d-150">For more information, see [Database errors](database-errors.md).</span></span>

<span data-ttu-id="93b1d-151">El código de error del error de SQLite será de forma predeterminada SQLITE_ERROR (o 1),</span><span class="sxs-lookup"><span data-stu-id="93b1d-151">By default, the error SQLite error code will be SQLITE_ERROR (or 1).</span></span> <span data-ttu-id="93b1d-152">pero se puede cambiar produciendo una excepción <xref:Microsoft.Data.Sqlite.SqliteException> en la función con el elemento <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> deseado especificado.</span><span class="sxs-lookup"><span data-stu-id="93b1d-152">You can, however, change it by throwing a <xref:Microsoft.Data.Sqlite.SqliteException> in your function with the desired <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> specified.</span></span>

## <a name="debugging"></a><span data-ttu-id="93b1d-153">Depuración</span><span class="sxs-lookup"><span data-stu-id="93b1d-153">Debugging</span></span>

<span data-ttu-id="93b1d-154">SQLite llama directamente a su implementación,</span><span class="sxs-lookup"><span data-stu-id="93b1d-154">SQLite calls your implementation directly.</span></span> <span data-ttu-id="93b1d-155">lo que le permite agregar puntos de interrupción que se desencadenan mientras SQLite está evaluando consultas.</span><span class="sxs-lookup"><span data-stu-id="93b1d-155">This lets you add breakpoints that trigger while SQLite is evaluating queries.</span></span> <span data-ttu-id="93b1d-156">La experiencia de depuración completa de .NET está disponible para ayudarle a crear funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="93b1d-156">The full .NET debugging experience is available to help you create your user-defined functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="93b1d-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="93b1d-157">See also</span></span>

* [<span data-ttu-id="93b1d-158">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="93b1d-158">Data types</span></span>](types.md)
* [<span data-ttu-id="93b1d-159">Funciones principales de SQLite</span><span class="sxs-lookup"><span data-stu-id="93b1d-159">SQLite Core functions</span></span>](https://www.sqlite.org/lang_corefunc.html)
* [<span data-ttu-id="93b1d-160">Funciones de agregado de SQLite</span><span class="sxs-lookup"><span data-stu-id="93b1d-160">SQLite Aggregate Functions</span></span>](https://www.sqlite.org/lang_aggfunc.html)
