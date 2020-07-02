---
title: Uso de variables de difusión en .NET para Apache Spark
description: Aprenda a usar variables de difusión en .NET para aplicaciones Apache Spark.
ms.date: 06/11/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 391e32cda14a9b3186ac96800351ddcb39a3d359
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105631"
---
# <a name="use-broadcast-variables-in-net-for-apache-spark"></a><span data-ttu-id="b01d7-103">Uso de variables de difusión en .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="b01d7-103">Use broadcast variables in .NET for Apache Spark</span></span>

<span data-ttu-id="b01d7-104">En este artículo, aprenderá a usar variables de difusión en .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="b01d7-104">In this article, you learn how to use broadcast variables in .NET for Apache Spark.</span></span> <span data-ttu-id="b01d7-105">Las [variables de difusión en Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) son mecanismos para compartir variables entre ejecutores que están diseñados para ser de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="b01d7-105">[Broadcast variables in Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) are mechanisms for sharing variables across executors that are meant to be read-only.</span></span> <span data-ttu-id="b01d7-106">Las variables de difusión permiten mantener una variable de solo lectura almacenada en caché en cada máquina en lugar de enviar una copia de ella con las tareas.</span><span class="sxs-lookup"><span data-stu-id="b01d7-106">Broadcast variables allow you to keep a read-only variable cached on each machine rather than shipping a copy of it with tasks.</span></span> <span data-ttu-id="b01d7-107">Las variables de difusión son una manera eficaz de asignar a cada nodo una copia de un conjunto de datos de entrada grande.</span><span class="sxs-lookup"><span data-stu-id="b01d7-107">You can use broadcast variables to give every node a copy of a large input dataset in an efficient manner.</span></span>

<span data-ttu-id="b01d7-108">Dado que los datos se envían solo una vez, las variables de difusión tienen ventajas de rendimiento cuando se comparan con las variables locales que se envían a los ejecutores con cada tarea.</span><span class="sxs-lookup"><span data-stu-id="b01d7-108">Because the data is sent only once, broadcast variables have performance benefits when compared to local variables that are shipped to the executors with each task.</span></span> <span data-ttu-id="b01d7-109">Consulte la [documentación oficial de la variable de difusión](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) para obtener una comprensión más profunda de las variables de difusión y por qué se usan.</span><span class="sxs-lookup"><span data-stu-id="b01d7-109">Refer to the [official broadcast variable documentation](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) to get a deeper understanding of broadcast variables and why they are used.</span></span>

## <a name="create-broadcast-variables"></a><span data-ttu-id="b01d7-110">Creación de variables de difusión</span><span class="sxs-lookup"><span data-stu-id="b01d7-110">Create broadcast variables</span></span>

<span data-ttu-id="b01d7-111">Para crear una variable de difusión, llame a `SparkContext.Broadcast(v)` para cualquier variable `v`.</span><span class="sxs-lookup"><span data-stu-id="b01d7-111">To create a broadcast variable, call `SparkContext.Broadcast(v)` for any variable `v`.</span></span> <span data-ttu-id="b01d7-112">La variable de difusión es un contenedor alrededor de la variable `v`, y se puede acceder a su valor llamando al método `Value()`.</span><span class="sxs-lookup"><span data-stu-id="b01d7-112">The broadcast variable is a wrapper around the variable `v`, and its value can be accessed by calling the `Value()` method.</span></span>

<span data-ttu-id="b01d7-113">En el fragmento de código siguiente, se crea una variable de cadena `v` y se crea una variable de difusión `bv` cuando se llama a `SparkContext.Broadcast(v)`.</span><span class="sxs-lookup"><span data-stu-id="b01d7-113">In the following code snippet, a string variable `v` is created, and a broadcast variable `bv` is created when `SparkContext.Broadcast(v)`is called.</span></span> <span data-ttu-id="b01d7-114">Observe que el parámetro de tipo `Broadcast`, cadena, coincide con el tipo de la variable que se va a difundir.</span><span class="sxs-lookup"><span data-stu-id="b01d7-114">Notice the type parameter for `Broadcast`, string, matches the type of the variable being broadcasted.</span></span> <span data-ttu-id="b01d7-115">La función definida por el usuario (UDF) devuelve el valor de `bv`.</span><span class="sxs-lookup"><span data-stu-id="b01d7-115">The user-defined function (UDF) returns the value of `bv`.</span></span>

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

Func<Column, Column> udf = Udf<string, string>(
    str => $"{str}: {bv.Value()}");
```

## <a name="delete-broadcast-variables"></a><span data-ttu-id="b01d7-116">Eliminación de variables de difusión</span><span class="sxs-lookup"><span data-stu-id="b01d7-116">Delete broadcast variables</span></span>

<span data-ttu-id="b01d7-117">La variable de difusión se puede eliminar de todos los ejecutores llamando al método `Destroy()`.</span><span class="sxs-lookup"><span data-stu-id="b01d7-117">The broadcast variable can be deleted from all executors by calling the `Destroy()` method.</span></span>

```csharp
bv.Destroy();
```

<span data-ttu-id="b01d7-118">`Destroy()` elimina todos los datos y metadatos relacionados con la variable de difusión y debe usarse con precaución.</span><span class="sxs-lookup"><span data-stu-id="b01d7-118">`Destroy()` deletes all data and metadata related to the broadcast variable and should be used with caution.</span></span> <span data-ttu-id="b01d7-119">Una vez que se destruye una variable de difusión, no se puede volver a usar.</span><span class="sxs-lookup"><span data-stu-id="b01d7-119">Once a broadcast variable is destroyed, it can't be used again.</span></span>

## <a name="limit-broadcast-variable-scope-in-udfs"></a><span data-ttu-id="b01d7-120">Límite del ámbito de la variable de difusión en funciones UDF</span><span class="sxs-lookup"><span data-stu-id="b01d7-120">Limit broadcast variable scope in UDFs</span></span>

<span data-ttu-id="b01d7-121">Cuando se usan variables de difusión en funciones UDF, es necesario limitar el ámbito de la variable a solo la UDF que hace referencia a la variable.</span><span class="sxs-lookup"><span data-stu-id="b01d7-121">When you use broadcast variables in UDFs, you need to limit the scope of the variable to only the UDF that is referencing the variable.</span></span> <span data-ttu-id="b01d7-122">En la [guía de uso de funciones UDF](udf-guide.md) se describe este fenómeno en detalle.</span><span class="sxs-lookup"><span data-stu-id="b01d7-122">The [guide to using UDFs](udf-guide.md) describes this phenomenon in detail.</span></span> <span data-ttu-id="b01d7-123">El ámbito es especialmente importante cuando se llama a `Destroy()` en la variable de difusión.</span><span class="sxs-lookup"><span data-stu-id="b01d7-123">Scope is especially crucial when you call `Destroy()` on the broadcast variable.</span></span>

<span data-ttu-id="b01d7-124">Si la variable de difusión que se ha destruido es visible o accesible desde otras UDF, todas las UDF la seleccionan para la serialización, aunque no se haga referencia a ellas.</span><span class="sxs-lookup"><span data-stu-id="b01d7-124">If the broadcast variable that has been destroyed is visible to or accessible from other UDFs, it gets picked up for serialization by all of the UDFs, even if it is not being referenced by them.</span></span> <span data-ttu-id="b01d7-125">.NET para Apache Spark no puede serializar la variable de difusión destruida, lo que produce un error.</span><span class="sxs-lookup"><span data-stu-id="b01d7-125">.NET for Apache Spark is unable to serialize the destroyed broadcast variable, which results in an error.</span></span> <span data-ttu-id="b01d7-126">El siguiente fragmento de código muestra este error:</span><span class="sxs-lookup"><span data-stu-id="b01d7-126">The following code snippet demonstrates this error:</span></span>

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

// Using the broadcast variable in a UDF:
Func<Column, Column> udf1 = Udf<string, string>(
    str => $"{str}: {bv.Value()}");

// Destroying bv
bv.Destroy();

// Calling udf1 after destroying bv throws the following expected exception:
// org.apache.spark.SparkException: Attempted to use Broadcast(0) after it was destroyed
df.Select(udf1(df["_1"])).Show();

// Different UDF udf2 that is not referencing bv
Func<Column, Column> udf2 = Udf<string, string>(
    str => $"{str}: not referencing broadcast variable");

// Calling udf2 throws the following (unexpected) exception:
// [Error] [JvmBridge] org.apache.spark.SparkException: Task not serializable
df.Select(udf2(df["_1"])).Show();
```

<span data-ttu-id="b01d7-127">En el fragmento de código siguiente se muestra cómo debemos asegurarnos de que la destrucción de `bv` no afecte a `udf2` debido a un comportamiento de serialización inesperado:</span><span class="sxs-lookup"><span data-stu-id="b01d7-127">The following code snippet demonstrates how to ensure that destroying `bv` doesn't affect `udf2` because of an unexpected serialization behavior:</span></span>

```csharp
string v = "Variable to be broadcasted";
// Restricting the visibility of bv to only the UDF referencing it
{
    Broadcast<string> bv = SparkContext.Broadcast(v);

    // Using the broadcast variable in a UDF:
    Func<Column, Column> udf1 = Udf<string, string>(
        str => $"{str}: {bv.Value()}");

    // Destroying bv
    bv.Destroy();
}

// Different UDF udf2 that is not referencing bv
Func<Column, Column> udf2 = Udf<string, string>(
    str => $"{str}: not referencing broadcast variable");

// Calling udf2 works fine as expected
df.Select(udf2(df["_1"])).Show();
```

## <a name="next-steps"></a><span data-ttu-id="b01d7-128">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b01d7-128">Next steps</span></span>

* [<span data-ttu-id="b01d7-129">Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="b01d7-129">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="b01d7-130">Depuración de una aplicación de .NET para Apache Spark en Windows</span><span class="sxs-lookup"><span data-stu-id="b01d7-130">Debug a .NET for Apache Spark application on Windows</span></span>](debug.md)
* [<span data-ttu-id="b01d7-131">Implementación de binarios de trabajo y función definida por el usuario de .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="b01d7-131">Deploy .NET for Apache Spark worker and user-defined function binaries</span></span>](deploy-worker-udf-binaries.md)
