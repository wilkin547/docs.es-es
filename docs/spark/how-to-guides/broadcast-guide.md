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
# <a name="use-broadcast-variables-in-net-for-apache-spark"></a>Uso de variables de difusión en .NET para Apache Spark

En este artículo, aprenderá a usar variables de difusión en .NET para Apache Spark. Las [variables de difusión en Apache Spark](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) son mecanismos para compartir variables entre ejecutores que están diseñados para ser de solo lectura. Las variables de difusión permiten mantener una variable de solo lectura almacenada en caché en cada máquina en lugar de enviar una copia de ella con las tareas. Las variables de difusión son una manera eficaz de asignar a cada nodo una copia de un conjunto de datos de entrada grande.

Dado que los datos se envían solo una vez, las variables de difusión tienen ventajas de rendimiento cuando se comparan con las variables locales que se envían a los ejecutores con cada tarea. Consulte la [documentación oficial de la variable de difusión](https://spark.apache.org/docs/2.2.0/rdd-programming-guide.html#broadcast-variables) para obtener una comprensión más profunda de las variables de difusión y por qué se usan.

## <a name="create-broadcast-variables"></a>Creación de variables de difusión

Para crear una variable de difusión, llame a `SparkContext.Broadcast(v)` para cualquier variable `v`. La variable de difusión es un contenedor alrededor de la variable `v`, y se puede acceder a su valor llamando al método `Value()`.

En el fragmento de código siguiente, se crea una variable de cadena `v` y se crea una variable de difusión `bv` cuando se llama a `SparkContext.Broadcast(v)`. Observe que el parámetro de tipo `Broadcast`, cadena, coincide con el tipo de la variable que se va a difundir. La función definida por el usuario (UDF) devuelve el valor de `bv`.

```csharp
string v = "Variable to be broadcasted";
Broadcast<string> bv = SparkContext.Broadcast(v);

Func<Column, Column> udf = Udf<string, string>(
    str => $"{str}: {bv.Value()}");
```

## <a name="delete-broadcast-variables"></a>Eliminación de variables de difusión

La variable de difusión se puede eliminar de todos los ejecutores llamando al método `Destroy()`.

```csharp
bv.Destroy();
```

`Destroy()` elimina todos los datos y metadatos relacionados con la variable de difusión y debe usarse con precaución. Una vez que se destruye una variable de difusión, no se puede volver a usar.

## <a name="limit-broadcast-variable-scope-in-udfs"></a>Límite del ámbito de la variable de difusión en funciones UDF

Cuando se usan variables de difusión en funciones UDF, es necesario limitar el ámbito de la variable a solo la UDF que hace referencia a la variable. En la [guía de uso de funciones UDF](udf-guide.md) se describe este fenómeno en detalle. El ámbito es especialmente importante cuando se llama a `Destroy()` en la variable de difusión.

Si la variable de difusión que se ha destruido es visible o accesible desde otras UDF, todas las UDF la seleccionan para la serialización, aunque no se haga referencia a ellas. .NET para Apache Spark no puede serializar la variable de difusión destruida, lo que produce un error. El siguiente fragmento de código muestra este error:

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

En el fragmento de código siguiente se muestra cómo debemos asegurarnos de que la destrucción de `bv` no afecte a `udf2` debido a un comportamiento de serialización inesperado:

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

## <a name="next-steps"></a>Pasos siguientes

* [Introducción a .NET para Apache Spark](../tutorials/get-started.md)
* [Depuración de una aplicación de .NET para Apache Spark en Windows](debug.md)
* [Implementación de binarios de trabajo y función definida por el usuario de .NET para Apache Spark](deploy-worker-udf-binaries.md)
