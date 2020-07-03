---
title: Creación de funciones definidas por el usuario (UDF) en .NET para Apache Spark
description: Obtenga información sobre cómo implementar funciones definidas por el usuario (UDF) en .NET para aplicaciones Apache Spark.
ms.date: 06/11/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: fe3dec187f94f84adb1217c39ff6aabc4b4db1c5
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2020
ms.locfileid: "85142022"
---
# <a name="create-user-defined-functions-udf-in-net-for-apache-spark"></a>Creación de funciones definidas por el usuario (UDF) en .NET para Apache Spark

En este artículo, veremos cómo se usan las funciones definidas por el usuario (UDF) en .NET para Apache Spark. Las [UDF](https://spark.apache.org/docs/latest/api/java/org/apache/spark/sql/expressions/UserDefinedFunction.html) son una característica de Spark que permite usar funciones personalizadas para ampliar la funcionalidad integrada del sistema. Las UDF transforman los valores de una sola fila de una tabla con el fin de generar un único valor de salida correspondiente por fila en función de la lógica definida en la UDF.

## <a name="define-udfs"></a>Definición de las UDF

Revise la siguiente definición de UDF:

```csharp
string s1 = "hello";
Func<Column, Column> udf = Udf<string, string>(
    str => $"{s1} {str}");
```

La UDF toma un valor `string` como entrada en forma de [columna](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Column.cs#L14) de un [DataFrame](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/DataFrame.cs#L24)) y devuelve un valor `string` con `hello` anexado delante de la entrada.

El siguiente DataFrame `df` contiene una lista de nombres:

```text
+-------+
|   name|
+-------+
|Michael|
|   Andy|
| Justin|
+-------+
```

Ahora vamos a aplicar la `udf` definida anteriormente al `df` de DataFrame:

```csharp
DataFrame udfResult = df.Select(udf(df["name"]));
```

El siguiente DataFrame `udfResult` es el resultado de la UDF:

```text
+-------------+
|         name|
+-------------+
|hello Michael|
|   hello Andy|
| hello Justin|
+-------------+
```

Para comprender mejor cómo implementar las UDF, revise las [funciones auxiliares de UDF](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Sql/Functions.cs#L3616) y los [ejemplos](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark.E2ETest/UdfTests/UdfSimpleTypesTests.cs#L49) en GitHub.

## <a name="udf-serialization"></a>Serialización de las UDF

Dado que las UDF son funciones que necesitan ejecutarse en los trabajos, deben serializarse y enviarse a los trabajos como parte de la carga del controlador. Así, es necesario serializar tanto el [delegado](../../csharp/programming-guide/delegates/index.md), que es una referencia al método, como su [destino](xref:System.Delegate.Target%2A), que es la instancia de clase en la que el delegado actual invoca al método de instancia. Revise [este ejemplo de código de GitHub](https://github.com/dotnet/spark/blob/master/src/csharp/Microsoft.Spark/Utils/CommandSerDe.cs#L149) para comprender mejor cómo se realiza la serialización de UDF.

.NET para Apache Spark usa .NET Core, que no admite la serialización de delegados. En su lugar, se usa la reflexión para serializar el destino en el que se define el delegado. Cuando se definen varios delegados en un ámbito común, tienen una clausura compartida que se convierte en el destino de la reflexión de la serialización.

### <a name="serialization-example"></a>Ejemplo de serialización

En el fragmento de código siguiente, se definen dos variables de cadena a las que se hace referencia en dos delegados de función que devuelven las cadenas respectivas como resultado:

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

El código C# anterior genera el siguiente código de desensamblado de C# (fuente de crédito: [sharplab.io](https://sharplab.io)) del compilador:

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

Tanto `func` como `func2` comparten el mismo `<>c__DisplayClass0_0` de clausura, que es el destino que se serializa al serializar los delegados `func` y `func2`. Aunque `Func<string, string> a` solo hace referencia a `s1`, `s2` también se serializa cuando los bytes se envían a los trabajos.

Esto puede dar lugar a comportamientos inesperados en tiempo de ejecución (como en el caso de usar [variables de difusión](broadcast-guide.md)), motivo por el cual se recomienda restringir la visibilidad de las variables usadas en una función al ámbito de esa función.

El siguiente fragmento de código es el método recomendado para implementar el comportamiento de serialización deseado:

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

El código C# anterior genera el siguiente código de desensamblado de C# (fuente de crédito: [sharplab.io](https://sharplab.io)) del compilador:

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

Observe que `func` y `func2` ya no comparten clausura y cada una tiene la suya propia, `<>c__DisplayClass0_0` y `<>c__DisplayClass0_1` respectivamente. Cuando se usa como destino para la serialización, solo se serializará para el delegado las variables a las que se hace referencia. Es importante tener en cuenta este comportamiento mientras se implementan varias UDF en un ámbito común.

## <a name="some-spark-udf-caveats"></a>Algunas advertencias sobre las UDF de Spark

* Los valores NULL de las UDF pueden iniciar excepciones. Es responsabilidad del desarrollador controlarlas.
* Las UDF no aprovechan las optimizaciones que proporcionan las funciones integradas de Spark, por lo que se recomienda usar las funciones integradas siempre que sea posible.

## <a name="next-steps"></a>Pasos siguientes

* [Introducción a .NET para Apache Spark](../tutorials/get-started.md)
* [Depuración de una aplicación de .NET para Apache Spark en Windows](debug.md)
