---
title: Creación de funciones definidas por el usuario (UDF) en .NET para Apache Spark
description: Obtenga información sobre cómo implementar funciones definidas por el usuario (UDF) en .NET para aplicaciones Apache Spark.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 97afda8ed17d3719c534d72ad3ad026745a70922
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620929"
---
# <a name="create-user-defined-functions-udf-in-net-for-apache-spark"></a><span data-ttu-id="13a02-103">Creación de funciones definidas por el usuario (UDF) en .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="13a02-103">Create user-defined functions (UDF) in .NET for Apache Spark</span></span>

<span data-ttu-id="13a02-104">En este artículo, veremos cómo se usan las funciones definidas por el usuario (UDF) en .NET para Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="13a02-104">In this article, you learn how to use user-defined functions (UDF) in .NET for Apache Spark.</span></span> <span data-ttu-id="13a02-105">Las [UDF](https://spark.apache.org/docs/latest/api/java/org/apache/spark/sql/expressions/UserDefinedFunction.html) son una característica de Spark que permite usar funciones personalizadas para ampliar la funcionalidad integrada del sistema.</span><span class="sxs-lookup"><span data-stu-id="13a02-105">[UDFs)](https://spark.apache.org/docs/latest/api/java/org/apache/spark/sql/expressions/UserDefinedFunction.html) are a Spark feature that allow you to use custom functions to extend the system's built-in functionality.</span></span> <span data-ttu-id="13a02-106">Las UDF transforman los valores de una sola fila de una tabla con el fin de generar un único valor de salida correspondiente por fila en función de la lógica definida en la UDF.</span><span class="sxs-lookup"><span data-stu-id="13a02-106">UDFs transform values from a single row within a table to produce a single corresponding output value per row based on the logic defined in the UDF.</span></span>

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="define-udfs"></a><span data-ttu-id="13a02-107">Definición de las UDF</span><span class="sxs-lookup"><span data-stu-id="13a02-107">Define UDFs</span></span>

<span data-ttu-id="13a02-108">Revise la siguiente definición de UDF:</span><span class="sxs-lookup"><span data-stu-id="13a02-108">Review the following UDF definition:</span></span>

```csharp
string s1 = "hello";
Func<Column, Column> udf = Udf<string, string>(
    str => $"{s1} {str}");
```

<span data-ttu-id="13a02-109">La UDF toma un valor `string` como entrada en forma de [columna](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Column.cs#L14) de un [DataFrame](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L24)) y devuelve un valor `string` con `hello` anexado delante de la entrada.</span><span class="sxs-lookup"><span data-stu-id="13a02-109">The UDF takes a `string` as an input in the form of a [Column](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Column.cs#L14) of a [Dataframe](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L24)) and returns a `string` with `hello` appended in front of the input.</span></span>

<span data-ttu-id="13a02-110">El siguiente DataFrame `df` contiene una lista de nombres:</span><span class="sxs-lookup"><span data-stu-id="13a02-110">The following DataFrame `df` contains a list of names:</span></span>

```text
+-------+
|   name|
+-------+
|Michael|
|   Andy|
| Justin|
+-------+
```

<span data-ttu-id="13a02-111">Ahora vamos a aplicar la `udf` definida anteriormente al `df` de DataFrame:</span><span class="sxs-lookup"><span data-stu-id="13a02-111">Now let's apply the above defined `udf` to the DataFrame `df`:</span></span>

```csharp
DataFrame udfResult = df.Select(udf(df["name"]));
```

<span data-ttu-id="13a02-112">El siguiente DataFrame `udfResult` es el resultado de la UDF:</span><span class="sxs-lookup"><span data-stu-id="13a02-112">The following DataFrame `udfResult` is the result of the UDF:</span></span>

```text
+-------------+
|         name|
+-------------+
|hello Michael|
|   hello Andy|
| hello Justin|
+-------------+
```

<span data-ttu-id="13a02-113">Para comprender mejor cómo implementar las UDF, revise las [funciones auxiliares de UDF](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Functions.cs#L3616) y los [ejemplos](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark.E2ETest/UdfTests/UdfSimpleTypesTests.cs#L49) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="13a02-113">To better understand how to implement UDFs, review the [UDF helper functions](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Functions.cs#L3616) and [examples](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark.E2ETest/UdfTests/UdfSimpleTypesTests.cs#L49) on GitHub.</span></span>

## <a name="udf-serialization"></a><span data-ttu-id="13a02-114">Serialización de las UDF</span><span class="sxs-lookup"><span data-stu-id="13a02-114">UDF serialization</span></span>

<span data-ttu-id="13a02-115">Dado que las UDF son funciones que necesitan ejecutarse en los trabajos, deben serializarse y enviarse a los trabajos como parte de la carga del controlador.</span><span class="sxs-lookup"><span data-stu-id="13a02-115">Because UDFs are functions that need to be executed on workers, they have to be serialized and sent to the workers as part of the payload from the driver.</span></span> <span data-ttu-id="13a02-116">Así, es necesario serializar tanto el [delegado](../../csharp/programming-guide/delegates/index.md), que es una referencia al método, como su [destino](xref:System.Delegate.Target%2A), que es la instancia de clase en la que el delegado actual invoca al método de instancia.</span><span class="sxs-lookup"><span data-stu-id="13a02-116">The [delegate](../../csharp/programming-guide/delegates/index.md), which is a reference to the method, needs to be serialized as well as its [target](xref:System.Delegate.Target%2A), which is the class instance on which the current delegate invokes the instance method.</span></span> <span data-ttu-id="13a02-117">Revise [este ejemplo de código de GitHub](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Utils/CommandSerDe.cs#L149) para comprender mejor cómo se realiza la serialización de UDF.</span><span class="sxs-lookup"><span data-stu-id="13a02-117">Review this [code example in GitHub](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Utils/CommandSerDe.cs#L149) to get a better understanding of how UDF serialization is being done.</span></span>

<span data-ttu-id="13a02-118">.NET para Apache Spark usa .NET Core, que no admite la serialización de delegados.</span><span class="sxs-lookup"><span data-stu-id="13a02-118">.NET for Apache Spark uses .NET Core, which doesn't support serializing delegates.</span></span> <span data-ttu-id="13a02-119">En su lugar, se usa la reflexión para serializar el destino en el que se define el delegado.</span><span class="sxs-lookup"><span data-stu-id="13a02-119">Instead, reflection is used to serialize the target where the delegate is defined.</span></span> <span data-ttu-id="13a02-120">Cuando se definen varios delegados en un ámbito común, tienen una clausura compartida que se convierte en el destino de la reflexión de la serialización.</span><span class="sxs-lookup"><span data-stu-id="13a02-120">When multiple delegates are defined in a common scope, they have a shared closure that becomes the target of reflection for serialization.</span></span>

### <a name="serialization-example"></a><span data-ttu-id="13a02-121">Ejemplo de serialización</span><span class="sxs-lookup"><span data-stu-id="13a02-121">Serialization example</span></span>

<span data-ttu-id="13a02-122">En el fragmento de código siguiente, se definen dos variables de cadena a las que se hace referencia en dos delegados de función que devuelven las cadenas respectivas como resultado:</span><span class="sxs-lookup"><span data-stu-id="13a02-122">The following code snippet defines two string variables that are being referenced in two function delegates that return the respective strings as a result:</span></span>

```csharp
using System;

public class C {
    public void M() {
        string s1 = "s1";
        string s2 = "s2";
        Func<string, string> a = str => s1;
        Func<string, string> b = str => s2;
    }
}
```

<span data-ttu-id="13a02-123">El código C# anterior genera el siguiente código de desensamblado de C# (fuente de crédito: [sharplab.io](https://sharplab.io)) del compilador:</span><span class="sxs-lookup"><span data-stu-id="13a02-123">The above C# code generates the following C# disassembly (credit source: [sharplab.io](https://sharplab.io)) code from the compiler:</span></span>

```csharp
public class C
{
    [CompilerGenerated]
    private sealed class <>c__DisplayClass0_0
    {
        public string s1;

        public string s2;

        internal string <M>b__0(string str)
        {
            return s1;
        }

        internal string <M>b__1(string str)
        {
            return s2;
        }
    }

    public void M()
    {
        <>c__DisplayClass0_0 <>c__DisplayClass0_ = new <>c__DisplayClass0_0();
        <>c__DisplayClass0_.s1 = "s1";
        <>c__DisplayClass0_.s2 = "s2";
        Func<string, string> func = new Func<string, string>(<>c__DisplayClass0_.<M>b__0);
        Func<string, string> func2 = new Func<string, string>(<>c__DisplayClass0_.<M>b__1);
    }
}
```

<span data-ttu-id="13a02-124">Tanto `func` como `func2` comparten el mismo `<>c__DisplayClass0_0` de clausura, que es el destino que se serializa al serializar los delegados `func` y `func2`.</span><span class="sxs-lookup"><span data-stu-id="13a02-124">Both `func` and `func2` share the same closure `<>c__DisplayClass0_0`, which is the target that is serialized when serializing the delegates `func` and `func2`.</span></span> <span data-ttu-id="13a02-125">Aunque `Func<string, string> a` solo hace referencia a `s1`, `s2` también se serializa cuando los bytes se envían a los trabajos.</span><span class="sxs-lookup"><span data-stu-id="13a02-125">Even though `Func<string, string> a` is only referencing `s1`, `s2` is also serialized when the bytes are sent to the workers.</span></span>

<span data-ttu-id="13a02-126">Esto puede dar lugar a comportamientos inesperados en tiempo de ejecución (como en el caso de usar [variables de difusión](broadcast-guide.md)), motivo por el cual se recomienda restringir la visibilidad de las variables usadas en una función al ámbito de esa función.</span><span class="sxs-lookup"><span data-stu-id="13a02-126">This can lead to some unexpected behaviors at runtime (like in the case of using [broadcast variables](broadcast-guide.md)), which is why we recommend that you restrict the visibility of the variables used in a function to that function's scope.</span></span>

<span data-ttu-id="13a02-127">El siguiente fragmento de código es el método recomendado para implementar el comportamiento de serialización deseado:</span><span class="sxs-lookup"><span data-stu-id="13a02-127">The following code snippet is the recommended way to implement the desired serialization behavior:</span></span>

```csharp
using System;

public class C {
    public void M() {
        {
            string s1 = "s1";
            Func<string, string> a = str => s1;
        }
        {
            string s2 = "s2";
            Func<string, string> b = str => s2;
        }
    }
}
```

<span data-ttu-id="13a02-128">El código C# anterior genera el siguiente código de desensamblado de C# (fuente de crédito: [sharplab.io](https://sharplab.io)) del compilador:</span><span class="sxs-lookup"><span data-stu-id="13a02-128">The above C# code generates the following C# disassembly (credit source: [sharplab.io](https://sharplab.io)) code from the compiler:</span></span>

```csharp
public class C
{
    [CompilerGenerated]
    private sealed class <>c__DisplayClass0_0
    {
        public string s1;

        internal string <M>b__0(string str)
        {
            return s1;
        }
    }

    [CompilerGenerated]
    private sealed class <>c__DisplayClass0_1
    {
        public string s2;

        internal string <M>b__1(string str)
        {
            return s2;
        }
    }

    public void M()
    {
        <>c__DisplayClass0_0 <>c__DisplayClass0_ = new <>c__DisplayClass0_0();
        <>c__DisplayClass0_.s1 = "s1";
        Func<string, string> func = new Func<string, string>(<>c__DisplayClass0_.<M>b__0);
        <>c__DisplayClass0_1 <>c__DisplayClass0_2 = new <>c__DisplayClass0_1();
        <>c__DisplayClass0_2.s2 = "s2";
        Func<string, string> func2 = new Func<string, string>(<>c__DisplayClass0_2.<M>b__1);
    }
}
```

<span data-ttu-id="13a02-129">Observe que `func` y `func2` ya no comparten clausura y cada una tiene la suya propia, `<>c__DisplayClass0_0` y `<>c__DisplayClass0_1` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="13a02-129">Notice that `func` and `func2` no longer share a closure, and they have their own separate closures `<>c__DisplayClass0_0` and `<>c__DisplayClass0_1` respectively.</span></span> <span data-ttu-id="13a02-130">Cuando se usa como destino para la serialización, solo se serializará para el delegado las variables a las que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="13a02-130">When used as the target for serialization, nothing other than the referenced variables will get serialized for the delegate.</span></span> <span data-ttu-id="13a02-131">Es importante tener en cuenta este comportamiento mientras se implementan varias UDF en un ámbito común.</span><span class="sxs-lookup"><span data-stu-id="13a02-131">This behavior is important to keep in mind while implementing multiple UDFs in a common scope.</span></span>

## <a name="some-spark-udf-caveats"></a><span data-ttu-id="13a02-132">Algunas advertencias sobre las UDF de Spark</span><span class="sxs-lookup"><span data-stu-id="13a02-132">Some Spark UDF caveats</span></span>

* <span data-ttu-id="13a02-133">Los valores NULL de las UDF pueden iniciar excepciones.</span><span class="sxs-lookup"><span data-stu-id="13a02-133">Null values in UDFs can throw exceptions.</span></span> <span data-ttu-id="13a02-134">Es responsabilidad del desarrollador controlarlas.</span><span class="sxs-lookup"><span data-stu-id="13a02-134">It's the responsibility of the developer to handle them.</span></span>
* <span data-ttu-id="13a02-135">Las UDF no aprovechan las optimizaciones que proporcionan las funciones integradas de Spark, por lo que se recomienda usar las funciones integradas siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="13a02-135">UDFs don't leverage the optimizations provided by Spark's built-in functions, so it's recommended to use built-in functions where possible.</span></span>

## <a name="next-steps"></a><span data-ttu-id="13a02-136">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="13a02-136">Next steps</span></span>

* [<span data-ttu-id="13a02-137">Introducción a .NET para Apache Spark</span><span class="sxs-lookup"><span data-stu-id="13a02-137">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="13a02-138">Depuración de una aplicación de .NET para Apache Spark en Windows</span><span class="sxs-lookup"><span data-stu-id="13a02-138">Debug a .NET for Apache Spark application on Windows</span></span>](debug.md)
