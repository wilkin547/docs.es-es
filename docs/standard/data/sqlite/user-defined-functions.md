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
# <a name="user-defined-functions"></a><span data-ttu-id="7ec14-103">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="7ec14-103">User-defined functions</span></span>

<span data-ttu-id="7ec14-104">La mayoría de las bases de datos tienen un dialecto de procedimientos de SQL que puede usar para definir sus propias funciones.</span><span class="sxs-lookup"><span data-stu-id="7ec14-104">Most databases have a procedural dialect of SQL that you can use to define your own functions.</span></span> <span data-ttu-id="7ec14-105">Sin embargo, SQLite se ejecuta en proceso con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7ec14-105">SQLite however, runs in-process with your app.</span></span> <span data-ttu-id="7ec14-106">En lugar de tener que aprender un nuevo dialecto de SQL, puede usar simplemente el lenguaje de programación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7ec14-106">Instead of having to learn a new dialect of SQL, you can just use the programming language of your app.</span></span>

## <a name="scalar-functions"></a><span data-ttu-id="7ec14-107">Funciones escalares</span><span class="sxs-lookup"><span data-stu-id="7ec14-107">Scalar functions</span></span>

<span data-ttu-id="7ec14-108">Las funciones escalares devuelven un único valor escalar para cada fila de una consulta.</span><span class="sxs-lookup"><span data-stu-id="7ec14-108">Scalar functions return a single, scalar value for each row in a query.</span></span> <span data-ttu-id="7ec14-109">Defina nuevas funciones escalares e invalide las integradas mediante <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span><span class="sxs-lookup"><span data-stu-id="7ec14-109">Define new scalar functions and override the built-in ones using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateFunction%2A>.</span></span>

<span data-ttu-id="7ec14-110">Vea [tipos de datos](types.md) para obtener una lista de parámetros admitidos y tipos de valor devueltos para el argumento `func`.</span><span class="sxs-lookup"><span data-stu-id="7ec14-110">See [Data types](types.md) for a list of supported parameter and return types for the `func` argument.</span></span>

<span data-ttu-id="7ec14-111">Especificar el `state` argumento pasará ese valor a cada invocación de la función.</span><span class="sxs-lookup"><span data-stu-id="7ec14-111">Specifying the `state` argument will pass that value into every invocation of the function.</span></span> <span data-ttu-id="7ec14-112">Úselo para evitar cierres.</span><span class="sxs-lookup"><span data-stu-id="7ec14-112">Use this to avoid closures.</span></span>

<span data-ttu-id="7ec14-113">Especifique `isDeterministic` si la función es determinista para permitir que SQLite use optimizaciones adicionales al compilar las consultas.</span><span class="sxs-lookup"><span data-stu-id="7ec14-113">Specify `isDeterministic` if your function is deterministic to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="7ec14-114">En el ejemplo siguiente se muestra cómo agregar una función escalar para calcular el radio de un cilindro.</span><span class="sxs-lookup"><span data-stu-id="7ec14-114">The following example shows how to add a scalar function to calculate the radius of a cylinder.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/ScalarFunctionSample/Program.cs?name=snippet_CreateFunction)]

## <a name="operators"></a><span data-ttu-id="7ec14-115">Operadores</span><span class="sxs-lookup"><span data-stu-id="7ec14-115">Operators</span></span>

<span data-ttu-id="7ec14-116">Las funciones escalares correspondientes implementan los siguientes operadores de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7ec14-116">The following SQLite operators are implemented by corresponding scalar functions.</span></span> <span data-ttu-id="7ec14-117">Al definir estas funciones escalares en la aplicación, se invalidará el comportamiento de estos operadores.</span><span class="sxs-lookup"><span data-stu-id="7ec14-117">Defining these scalar functions in your app will override the behavior of these operators.</span></span>

| <span data-ttu-id="7ec14-118">"??"</span><span class="sxs-lookup"><span data-stu-id="7ec14-118">Operator</span></span>          | <span data-ttu-id="7ec14-119">Función</span><span class="sxs-lookup"><span data-stu-id="7ec14-119">Function</span></span>      |
| ----------------- | ------------- |
| <span data-ttu-id="7ec14-120">X GLOB Y</span><span class="sxs-lookup"><span data-stu-id="7ec14-120">X GLOB Y</span></span>          | <span data-ttu-id="7ec14-121">Glob (Y, X)</span><span class="sxs-lookup"><span data-stu-id="7ec14-121">glob(Y, X)</span></span>    |
| <span data-ttu-id="7ec14-122">X LIKE Y</span><span class="sxs-lookup"><span data-stu-id="7ec14-122">X LIKE Y</span></span>          | <span data-ttu-id="7ec14-123">like (Y, X)</span><span class="sxs-lookup"><span data-stu-id="7ec14-123">like(Y, X)</span></span>    |
| <span data-ttu-id="7ec14-124">X LIKE Y ESCAPE Z</span><span class="sxs-lookup"><span data-stu-id="7ec14-124">X LIKE Y ESCAPE Z</span></span> | <span data-ttu-id="7ec14-125">like (Y, X, Z)</span><span class="sxs-lookup"><span data-stu-id="7ec14-125">like(Y, X, Z)</span></span> |
| <span data-ttu-id="7ec14-126">X COINCIDE Y</span><span class="sxs-lookup"><span data-stu-id="7ec14-126">X MATCH Y</span></span>         | <span data-ttu-id="7ec14-127">coincidencia (Y, X)</span><span class="sxs-lookup"><span data-stu-id="7ec14-127">match(Y, X)</span></span>   |
| <span data-ttu-id="7ec14-128">X REGEXP Y</span><span class="sxs-lookup"><span data-stu-id="7ec14-128">X REGEXP Y</span></span>        | <span data-ttu-id="7ec14-129">RegExp (Y, X)</span><span class="sxs-lookup"><span data-stu-id="7ec14-129">regexp(Y, X)</span></span>  |

<span data-ttu-id="7ec14-130">En el ejemplo siguiente se muestra cómo definir la función RegExp para habilitar su operador correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7ec14-130">The following example shows how to define the regexp function to enable its corresponding operator.</span></span> <span data-ttu-id="7ec14-131">SQLite no incluye una implementación predeterminada de la función RegExp.</span><span class="sxs-lookup"><span data-stu-id="7ec14-131">SQLite doesn't include a default implementation of the regexp function.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/RegularExpressionSample/Program.cs?name=snippet_Regex)]

## <a name="aggregate-functions"></a><span data-ttu-id="7ec14-132">Funciones de agregado</span><span class="sxs-lookup"><span data-stu-id="7ec14-132">Aggregate functions</span></span>

<span data-ttu-id="7ec14-133">Las funciones de agregado devuelven un único valor agregado para todas las filas de una consulta.</span><span class="sxs-lookup"><span data-stu-id="7ec14-133">Aggregate functions return a single, aggregated value for all the rows in a query.</span></span> <span data-ttu-id="7ec14-134">Defina e invalide las funciones de agregado mediante <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span><span class="sxs-lookup"><span data-stu-id="7ec14-134">Define and override aggregate functions using <xref:Microsoft.Data.Sqlite.SqliteConnection.CreateAggregate%2A>.</span></span>

<span data-ttu-id="7ec14-135">El argumento `seed` especifica el estado inicial del contexto.</span><span class="sxs-lookup"><span data-stu-id="7ec14-135">The `seed` argument specifies the initial state of the context.</span></span> <span data-ttu-id="7ec14-136">Úselo también para evitar cierres.</span><span class="sxs-lookup"><span data-stu-id="7ec14-136">Use this to avoid closures also.</span></span>

<span data-ttu-id="7ec14-137">El argumento `func` se invoca una vez por cada fila.</span><span class="sxs-lookup"><span data-stu-id="7ec14-137">The `func` argument is invoked once per row.</span></span> <span data-ttu-id="7ec14-138">Use el contexto para acumular un resultado final.</span><span class="sxs-lookup"><span data-stu-id="7ec14-138">Use the context to accumulate a final result.</span></span> <span data-ttu-id="7ec14-139">Devuelve el contexto.</span><span class="sxs-lookup"><span data-stu-id="7ec14-139">Return the context.</span></span> <span data-ttu-id="7ec14-140">Este patrón permite que el contexto sea un tipo de valor o inmutable.</span><span class="sxs-lookup"><span data-stu-id="7ec14-140">This pattern allows the context to be a value type or immutable.</span></span>

<span data-ttu-id="7ec14-141">Si no se especifica ningún `resultSelector`, el estado final del contexto se utiliza como resultado.</span><span class="sxs-lookup"><span data-stu-id="7ec14-141">If no `resultSelector` is specified, the final state of the context is used as the result.</span></span> <span data-ttu-id="7ec14-142">Esto puede simplificar la definición de funciones como SUM y Count que solo necesitan incrementar un número cada fila y devolverlo.</span><span class="sxs-lookup"><span data-stu-id="7ec14-142">This can simplify the definition of functions like sum and count that only need to increment a number each row and return it.</span></span>

<span data-ttu-id="7ec14-143">Especifique `resultSelector` para calcular el resultado final del contexto después de recorrer en iteración todas las filas.</span><span class="sxs-lookup"><span data-stu-id="7ec14-143">Specify `resultSelector` to calculate the final result from the context after iterating through all the rows.</span></span>

<span data-ttu-id="7ec14-144">Vea [tipos de datos](types.md) para obtener una lista de los tipos de parámetro admitidos para el argumento `func` y los tipos de valor devueltos para `resultSelector`.</span><span class="sxs-lookup"><span data-stu-id="7ec14-144">See [Data types](types.md) for a list of supported parameter types for the `func` argument and return types for `resultSelector`.</span></span>

<span data-ttu-id="7ec14-145">Si la función es determinista, especifique `isDeterministic` para permitir que SQLite use optimizaciones adicionales al compilar las consultas.</span><span class="sxs-lookup"><span data-stu-id="7ec14-145">If your function is deterministic, specify `isDeterministic` to allow SQLite to use additional optimizations when compiling queries.</span></span>

<span data-ttu-id="7ec14-146">En el ejemplo siguiente se define una función de agregado para calcular la desviación estándar de una columna.</span><span class="sxs-lookup"><span data-stu-id="7ec14-146">The following example defines an aggregate function to calculate the standard deviation of a column.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AggregateFunctionSample/Program.cs?name=snippet_CreateAggregate)]

## <a name="errors"></a><span data-ttu-id="7ec14-147">Errores de</span><span class="sxs-lookup"><span data-stu-id="7ec14-147">Errors</span></span>

<span data-ttu-id="7ec14-148">Si una función definida por el usuario produce una excepción, el mensaje se devuelve a SQLite.</span><span class="sxs-lookup"><span data-stu-id="7ec14-148">If a user-defined function throws an exception, the message is returned to SQLite.</span></span> <span data-ttu-id="7ec14-149">SQLite producirá un error y Microsoft. Data. SQLite producirá un SqliteException.</span><span class="sxs-lookup"><span data-stu-id="7ec14-149">SQLite will then raise an error and Microsoft.Data.Sqlite will throw a SqliteException.</span></span> <span data-ttu-id="7ec14-150">Para obtener más información, vea [errores de base de datos](database-errors.md).</span><span class="sxs-lookup"><span data-stu-id="7ec14-150">For more information, see [Database errors](database-errors.md).</span></span>

<span data-ttu-id="7ec14-151">De forma predeterminada, el código de error de SQLite de error se SQLITE_ERROR (o 1).</span><span class="sxs-lookup"><span data-stu-id="7ec14-151">By default, the error SQLite error code will be SQLITE_ERROR (or 1).</span></span> <span data-ttu-id="7ec14-152">Sin embargo, puede cambiarlo iniciando una <xref:Microsoft.Data.Sqlite.SqliteException> en la función con el <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> deseado especificado.</span><span class="sxs-lookup"><span data-stu-id="7ec14-152">You can, however, change it by throwing a <xref:Microsoft.Data.Sqlite.SqliteException> in your function with the desired <xref:Microsoft.Data.Sqlite.SqliteException.SqliteErrorCode> specified.</span></span>

## <a name="debugging"></a><span data-ttu-id="7ec14-153">Depuración</span><span class="sxs-lookup"><span data-stu-id="7ec14-153">Debugging</span></span>

<span data-ttu-id="7ec14-154">SQLite llama directamente a su implementación.</span><span class="sxs-lookup"><span data-stu-id="7ec14-154">SQLite calls your implementation directly.</span></span> <span data-ttu-id="7ec14-155">Esto le permite agregar puntos de interrupción que se desencadenan mientras SQLite está evaluando consultas.</span><span class="sxs-lookup"><span data-stu-id="7ec14-155">This lets you add breakpoints that trigger while SQLite is evaluating queries.</span></span> <span data-ttu-id="7ec14-156">La experiencia completa de depuración de .NET está disponible para ayudarle a crear funciones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="7ec14-156">The full .NET debugging experience is available to help you create your user-defined functions.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ec14-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ec14-157">See also</span></span>

* [<span data-ttu-id="7ec14-158">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="7ec14-158">Data types</span></span>](types.md)
* [<span data-ttu-id="7ec14-159">Funciones principales de SQLite</span><span class="sxs-lookup"><span data-stu-id="7ec14-159">SQLite Core functions</span></span>](https://www.sqlite.org/lang_corefunc.html)
* [<span data-ttu-id="7ec14-160">Funciones de agregado de SQLite</span><span class="sxs-lookup"><span data-stu-id="7ec14-160">SQLite Aggregate Functions</span></span>](https://www.sqlite.org/lang_aggfunc.html)
