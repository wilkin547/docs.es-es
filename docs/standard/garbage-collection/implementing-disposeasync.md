---
title: Implementación de un método DisposeAsync
description: Obtenga información sobre cómo implementar los métodos DisposeAsync y DisposeAsyncCore para realizar una limpieza de recursos asincrónica.
author: IEvangelist
ms.author: dapine
ms.date: 10/26/2020
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 551dbc30f6f5c99c7bfa468d7d708789c06acb7b
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827807"
---
# <a name="implement-a-disposeasync-method"></a>Implementación de un método DisposeAsync

La interfaz <xref:System.IAsyncDisposable?displayProperty=nameWithType> se presentó como parte de C# 8.0. El método <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> se implementa cuando se necesita realizar una limpieza de recursos, tal como se haría a la hora de [implementar un método Dispose](implementing-dispose.md). Sin embargo, una de las principales diferencias es que esta implementación permite operaciones de limpieza asincrónicas. El elemento <xref:System.IAsyncDisposable.DisposeAsync> devuelve un elemento <xref:System.Threading.Tasks.ValueTask> que representa la operación de eliminación asincrónica.

Es habitual que, al implementar la interfaz <xref:System.IAsyncDisposable>, las clases también implementen la interfaz <xref:System.IDisposable>. Se debe preparar un patrón de implementación correcto de la interfaz <xref:System.IAsyncDisposable> para la eliminación sincrónica o asincrónica. Todas las instrucciones para implementar el patrón de eliminación se aplican también a la implementación asincrónica. En este artículo se supone que ya se ha familiarizado con el modo de [implementar un método Dispose](implementing-dispose.md).

## <a name="disposeasync-and-disposeasynccore"></a>DisposeAsync() y DisposeAsyncCore()

La interfaz <xref:System.IAsyncDisposable> declara un único método sin parámetros: <xref:System.IAsyncDisposable.DisposeAsync>. Cualquier clase no sellada debe tener un método `DisposeAsyncCore()` adicional que también devuelva un elemento <xref:System.Threading.Tasks.ValueTask>.

- Una implementación de <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> `public` que no tenga parámetros.
- Un método `protected virtual ValueTask DisposeAsyncCore()` cuya signatura sea:

  ```csharp
  protected virtual ValueTask DisposeAsyncCore()
  {
  }
  ```

### <a name="the-disposeasync-method"></a>El método DisposeAsync()

Se llama de forma implícita al método `DisposeAsync()` sin parámetros `public` en una instrucción `await using`, y su propósito consiste en liberar los recursos no administrados, realizar una limpieza general e indicar que el finalizador, si existe, no necesita ejecutarse. La liberación de la memoria asociada a un objeto administrado siempre corresponde al [recolector de elementos no utilizados](index.md). Debido a esto, se realiza una implementación estándar:

```csharp
public async ValueTask DisposeAsync()
{
    // Perform async cleanup.
    await DisposeAsyncCore();

    // Dispose of unmanaged resources.
    Dispose(false);
    // Suppress finalization.
    GC.SuppressFinalize(this);
}
```

> [!NOTE]
> Una diferencia principal en el patrón de eliminación asincrónica en comparación con el patrón de eliminación es que la llamada desde <xref:System.IAsyncDisposable.DisposeAsync> al método de sobrecarga `Dispose(bool)` recibe el valor `false` como argumento. Pero al implementar el método <xref:System.IDisposable.Dispose?displayProperty=nameWithType>, en su lugar se pasa el valor `true`. Esto ayuda a garantizar la equivalencia funcional con el patrón de eliminación sincrónico y garantiza aún más que se invoquen las rutas de acceso al código finalizador. En otras palabras, el método `DisposeAsyncCore()` eliminará los recursos administrados de forma asincrónica, por lo que no querrá eliminarlos también de forma sincrónica. Por tanto, llame a `Dispose(false)` en lugar de a `Dispose(true)`.

### <a name="the-disposeasynccore-method"></a>Método DisposeAsyncCore()

El método `DisposeAsyncCore()` está diseñado para realizar la limpieza asincrónica de los recursos administrados o para hacer llamadas en cascada a `DisposeAsync()`. Encapsula las operaciones de limpieza asincrónica comunes cuando una subclase hereda una clase base que es una implementación de <xref:System.IAsyncDisposable>. El método `DisposeAsyncCore()` es `virtual` para que las clases derivadas puedan definir la limpieza adicional en sus invalidaciones.

> [!TIP]
> Si una implementación de <xref:System.IAsyncDisposable> es `sealed`, el método `DisposeAsyncCore()` no es necesario y la limpieza asincrónica se puede realizar directamente en el método <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>.

## <a name="implement-the-async-dispose-pattern"></a>Implementación del patrón de eliminación asincrónica

Todas las clases no selladas deben considerarse una clase base potencial, ya que se podrían heredar. Cuando se implementa el patrón de eliminación asincrónica para cualquier clase base potencial, se debe proporcionar el método `protected virtual ValueTask DisposeAsyncCore()`. Este es un ejemplo de implementación del patrón de eliminación asincrónica que usa un elemento <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

En el ejemplo anterior se usa <xref:System.Text.Json.Utf8JsonWriter>. Para obtener más información sobre `System.Text.Json`, vea [Migración desde Newtonsoft.json a System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).

## <a name="implement-both-dispose-and-async-dispose-patterns"></a>Implementación de patrones de eliminación y eliminación asincrónica

Es posible que tenga que implementar las interfaces <xref:System.IDisposable> y <xref:System.IAsyncDisposable>, especialmente si el ámbito de clase contiene instancias de estas implementaciones. De este modo se asegura de poder limpiar correctamente las llamadas en cascada. A continuación se incluye una clase de ejemplo que implementa ambas interfaces y muestra las instrucciones adecuadas para la limpieza.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/dispose-and-disposeasync.cs":::

Las implementaciones de <xref:System.IDisposable.Dispose?displayProperty=nameWithType> y <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> se llevan a cabo mediante código reutilizable sencillo.

En el método de sobrecarga `Dispose(bool)`, la instancia de <xref:System.IDisposable> se elimina condicionalmente si no es `null`. La instancia de <xref:System.IAsyncDisposable> se convierte a <xref:System.IDisposable> y, si tampoco es `null`, también se elimina. Después, se asignan ambas instancias a `null`.

Con el método `DisposeAsyncCore()`, se sigue el mismo enfoque lógico. Si la instancia de <xref:System.IAsyncDisposable> no es `null`, se espera a la llamada a `DisposeAsync().ConfigureAwait(false)`. Si la instancia de <xref:System.IDisposable> también es una implementación de <xref:System.IAsyncDisposable>, entonces, también se elimina de forma asincrónica. Después, se asignan ambas instancias a `null`.

## <a name="using-async-disposable"></a>Uso de la eliminación asincrónica

Para usar correctamente un objeto que implementa la interfaz <xref:System.IAsyncDisposable>, utilice las palabras clave [await](../../csharp/language-reference/operators/await.md) y [using](../../csharp/language-reference/keywords/using-statement.md) juntas. Tenga en cuenta el ejemplo siguiente, donde se crea una instancia de la clase `ExampleAsyncDisposable` y después se encapsula en una instrucción `await using`.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> Use el método de extensión <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> de la interfaz <xref:System.IAsyncDisposable> para configurar el modo en que se serializa la continuación de la tarea en su contexto o programador original. Para obtener más información sobre `ConfigureAwait`, consulte las [preguntas más frecuentes sobre ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq/).

En situaciones en las que no se necesita el uso de `ConfigureAwait`, la instrucción `await using` se podría simplificar de la siguiente manera:

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

Además, se podría escribir para utilizar el ámbito implícito de una [declaración "using"](../../csharp/whats-new/csharp-8.md#using-declarations).

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a>Declaraciones "using" apiladas

En situaciones en las que se crean y se usan varios objetos que implementan <xref:System.IAsyncDisposable>, es posible que el apilamiento de instrucciones `await using` con <xref:System.Threading.Tasks.ValueTask.ConfigureAwait%2A> en condiciones errantes pueda impedir las llamadas a <xref:System.IAsyncDisposable.DisposeAsync>. Para asegurarse de que siempre se llama a <xref:System.IAsyncDisposable.DisposeAsync>, debe evitar el apilamiento. En los tres ejemplos de código siguientes se muestran patrones aceptables para usar en su lugar.

### <a name="acceptable-pattern-one"></a>Patrón aceptable 1

:::code language="csharp" id="one" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

En el ejemplo anterior, cada operación de limpieza asincrónica tiene un ámbito explícito en el bloque `await using`. El ámbito externo se define en la forma en la que `objOne` establece sus llaves y se encierra `objTwo`; por tanto, primero se elimina `objTwo`, seguido de `objOne`. Las dos instancias de `IAsyncDisposable` tienen métodos <xref:System.IAsyncDisposable.DisposeAsync> en espera, con lo que se realiza su operación de limpieza asincrónica. Las llamadas están anidadas, no apiladas.

### <a name="acceptable-pattern-two"></a>Patrón aceptable 2

:::code language="csharp" id="two" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

En el ejemplo anterior, cada operación de limpieza asincrónica tiene un ámbito explícito en el bloque `await using`. Al final de cada bloque, la instancia de `IAsyncDisposable` correspondiente tiene su método <xref:System.IAsyncDisposable.DisposeAsync> en espera, con lo que se realiza su operación de limpieza asincrónica. Las llamadas son secuenciales, no apiladas. En este escenario, primero se elimina `objOne` y, luego, `objTwo`.

### <a name="acceptable-pattern-three"></a>Patrón aceptable 3

:::code language="csharp" id="three" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

En el ejemplo anterior, cada operación de limpieza asincrónica tiene un ámbito implícito en el cuerpo del método contenedor. Al final del bloque contenedor, las instancias de `IAsyncDisposable` realizan sus operaciones de limpieza asincrónicas. Esto se ejecuta en orden inverso en el que se han declarado, lo que significa que `objTwo` se elimina antes que `objOne`.

### <a name="unacceptable-pattern"></a>Patrón no aceptable

Si se inicia una excepción desde el constructor `AnotherAsyncDisposable`, `objOne` no se elimina correctamente:

:::code language="csharp" id="dontdothis" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

> [!TIP]
> Evite este patrón, ya que podría provocar un comportamiento inesperado.

## <a name="see-also"></a>Consulte también

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
