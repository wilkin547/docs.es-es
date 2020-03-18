---
title: Ejecución de árboles de expresión
description: Obtenga información sobre la ejecución de árboles de expresión convirtiéndolos en instrucciones de lenguaje intermedio (IL) ejecutables.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 109e0ac5-2a9c-48b4-ac68-9b6219cdbccf
ms.openlocfilehash: 802a83f52f9c05a99c3f49f8f6511eff81ef3eaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146026"
---
# <a name="executing-expression-trees"></a>Ejecución de árboles de expresión

[Anterior: Tipos de marco que admiten árboles de expresión](expression-classes.md)

Un *árbol de expresión* es una estructura de datos que representa un código.
No es código compilado y ejecutable. Si quiere ejecutar el código de .NET que se representa mediante un árbol de expresión, debe convertirlo en instrucciones de lenguaje intermedio ejecutables.

## <a name="lambda-expressions-to-functions"></a>Expresiones lambda a funciones

Puede convertir cualquier objeto LambdaExpression o cualquier tipo derivado de LambdaExpression en lenguaje intermedio ejecutable. Otros tipos de expresión no se pueden convertir directamente a código. Esta restricción tiene poco efecto en la práctica. Las expresiones lambda son los únicos tipos de expresiones que podría querer ejecutar mediante la conversión a lenguaje intermedio (IL) ejecutable. (Piense lo que significaría ejecutar directamente una `ConstantExpression`. ¿Tendría algún significado útil?). Cualquier árbol de expresión que es una `LambdaExpression` o un tipo derivado de `LambdaExpression` se puede convertir a lenguaje intermedio.
El tipo de expresión `Expression<TDelegate>` es el único ejemplo concreto en las bibliotecas de .NET Core. Se usa para representar una expresión que se asigna a cualquier tipo de delegado. Dado que este tipo se asigna a un tipo de delegado, .NET puede examinar la expresión y generar el lenguaje intermedio de un delegado adecuado que coincida con la firma de la expresión lambda.

En la mayoría de los casos, esto crea una asignación simple entre una expresión y su delegado correspondiente. Por ejemplo, un árbol de expresión que se representa por `Expression<Func<int>>` se convertiría a un delegado del tipo `Func<int>`. Para una expresión lambda con cualquier tipo de valor devuelto y lista de argumentos, existe un tipo de delegado que es el tipo de destino para el código ejecutable representado por esa expresión lambda.

El tipo `LambdaExpression` contiene los miembros `Compile` y `CompileToMethod` que se usarían para convertir un árbol de expresión en código ejecutable. El método `Compile` crea un delegado. El método `CompileToMethod` actualiza un objeto `MethodBuilder` con el lenguaje intermedio que representa la salida compilada del árbol de expresión. Tenga en cuenta que `CompileToMethod` solo está disponible en el marco de trabajo de escritorio completo, no en .NET Core.

Como opción, también puede proporcionar un `DebugInfoGenerator` para que reciba la información de depuración de símbolos para el objeto de delegado generado. Esto le permite convertir el árbol de expresión en un objeto de delegado y disponer de información de depuración completa sobre el delegado generado.

Para convertir una expresión en un delegado se usaría el siguiente código:

```csharp
Expression<Func<int>> add = () => 1 + 2;
var func = add.Compile(); // Create Delegate
var answer = func(); // Invoke Delegate
Console.WriteLine(answer);
```

Observe que el tipo de delegado se basa en el tipo de expresión. Debe conocer el tipo de valor devuelto y la lista de argumentos si quiere usar el objeto de delegado de una forma fuertemente tipada. El método `LambdaExpression.Compile()` devuelve el tipo `Delegate`. Tendrá que convertirlo al tipo de delegado correcto para que las herramientas de tiempo de compilación comprueben la lista de argumentos del tipo de valor devuelto.

## <a name="execution-and-lifetimes"></a>Ejecución y duraciones

El código se ejecuta mediante la invocación del delegado que se crea al llamar a `LambdaExpression.Compile()`. Puede verlo encima de donde `add.Compile()` devuelve un delegado. Invocar ese delegado, mediante una llamada a `func()` ejecuta el código.

Ese delegado representa el código en el árbol de expresión. Se puede conservar el identificador a ese delegado e invocarlo más adelante. No es necesario compilar el árbol de expresión cada vez que se quiera ejecutar el código que representa. (Recuerde que los árboles de expresión son inmutables y que compilar el mismo árbol de expresión más adelante creará un delegado que ejecuta el mismo código).

No es aconsejable intentar crear cualquier mecanismo de almacenamiento en caché más sofisticado para aumentar el rendimiento evitando llamadas innecesarias de compilación. La comparación de dos árboles de expresión arbitrarios para determinar si representan el mismo algoritmo también consumirá mucho tiempo de ejecución. Probablemente comprobará que el tiempo de proceso que se ahorra al evitar llamadas adicionales a `LambdaExpression.Compile()` será consumido por el tiempo de ejecución de código que determina que dos árboles de expresión diferentes devuelven el mismo código ejecutable.

## <a name="caveats"></a>Advertencias

Compilar una expresión lambda en un delegado e invocar ese delegado es una de las operaciones más simples que se pueden realizar con un árbol de expresión. Pero incluso con esta sencilla operación, hay advertencias que debe conocer.

Las expresiones lambda crean clausuras sobre las variables locales a las que se hace referencia en la expresión. Debe garantizar que las variables que formarían parte del delegado se pueden usar en la ubicación desde la que se llama a `Compile`, y cuando se ejecuta el delegado resultante.

En general, el compilador se asegurará de que esto es cierto. Pero si la expresión tiene acceso a una variable que implementa `IDisposable`, es posible que el código deseche el objeto mientras se sigue manteniendo en el árbol de expresión.

Por ejemplo, este código funciona bien porque `int` no implementa `IDisposable`:

```csharp
private static Func<int, int> CreateBoundFunc()
{
    var constant = 5; // constant is captured by the expression tree
    Expression<Func<int, int>> expression = (b) => constant + b;
    var rVal = expression.Compile();
    return rVal;
}
```

El delegado capturó una referencia a la variable local `constant`.
Esa variable es accesible en cualquier momento posterior, cuando se ejecuta la función devuelta por `CreateBoundFunc`.

Pero considere esta clase (bastante artificiosa) que implementa `IDisposable`:

```csharp
public class Resource : IDisposable
{
    private bool isDisposed = false;
    public int Argument
    {
        get
        {
            if (!isDisposed)
                return 5;
            else throw new ObjectDisposedException("Resource");
        }
    }

    public void Dispose()
    {
        isDisposed = true;
    }
}
```

Si se usa en una expresión como se muestra a continuación, obtendrá una `ObjectDisposedException` al ejecutar el código al que hace referencia la propiedad `Resource.Argument`:

```csharp
private static Func<int, int> CreateBoundResource()
{
    using (var constant = new Resource()) // constant is captured by the expression tree
    {
        Expression<Func<int, int>> expression = (b) => constant.Argument + b;
        var rVal = expression.Compile();
        return rVal;
    }
}
```

El delegado devuelto por este método se clausuró sobre el objeto `constant`, que se eliminó. (Se eliminó porque se declaró en una instrucción `using`).

Ahora, al ejecutar el delegado devuelto por este método, se producirá una excepción `ObjectDisposedException` en el punto de ejecución.

Parece extraño tener un error en tiempo de ejecución que representa una construcción de tiempo de compilación, pero es el mundo al que se entra cuando se trabaja con árboles de expresión.

Hay una gran cantidad de permutaciones de este problema, por lo que resulta difícil ofrecer instrucciones generales para evitarlo. Tenga cuidado al obtener acceso a las variables locales al definir expresiones y al obtener acceso al estado en el objeto actual (representado por `this`) al crear un árbol de expresión que pueda ser devuelto por una API pública.

El código de la expresión puede hacer referencia a métodos o propiedades de otros ensamblados. Ese ensamblado debe ser accesible cuando se define la expresión, cuando se compila y cuando se invoca el delegado resultante. En los casos en los que no esté presente, se producirá una excepción `ReferencedAssemblyNotFoundException`.

## <a name="summary"></a>Resumen

Los árboles de expresión que representan expresiones lambda se pueden compilar para crear un delegado que se puede ejecutar. Esto proporciona un mecanismo para ejecutar el código representado por un árbol de expresión.

El árbol de expresión representa el código que se ejecutaría para cualquier construcción que se cree. Mientras que el entorno donde se compile y ejecute el código coincida con el entorno donde se crea la expresión, todo funciona según lo esperado. Cuando eso no sucede, los errores son muy predecibles y se detectarán en las primeras pruebas de cualquier código que use los árboles de expresión.

[Siguiente: Interpretación de expresiones](expression-trees-interpreting.md)
