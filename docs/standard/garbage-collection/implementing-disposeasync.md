---
title: Implementación de un método DisposeAsync
description: ''
ms.date: 06/02/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: c4f541d5a4f5b5fd31b344a299789d86cd78424c
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "84311003"
---
# <a name="implement-a-disposeasync-method"></a>Implementación de un método DisposeAsync

La interfaz <xref:System.IAsyncDisposable?displayProperty=nameWithType> se presentó como parte de C# 8.0. El método <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> se implementa cuando se necesita realizar una limpieza de recursos, tal como se haría a la hora de [implementar un método Dispose](implementing-dispose.md). Sin embargo, una de las principales diferencias es que esta implementación permite operaciones de limpieza asincrónicas. El elemento <xref:System.IAsyncDisposable.DisposeAsync> devuelve un elemento <xref:System.Threading.Tasks.ValueTask> que representa la operación de eliminación asincrónica.

Resulta habitual que, al implementar la interfaz <xref:System.IAsyncDisposable>, las clases también implementen la interfaz <xref:System.IDisposable>. Debe prepararse un buen patrón de implementación de la interfaz <xref:System.IAsyncDisposable> para la eliminación sincrónica o asincrónica. Todas las instrucciones para implementar el patrón de eliminación se aplican a la implementación asincrónica. En este artículo se supone que ya se ha familiarizado con el modo de [implementar un método Dispose](implementing-dispose.md).

## <a name="disposeasync-and-disposeasynccore"></a>DisposeAsync() y DisposeAsyncCore()

La interfaz <xref:System.IAsyncDisposable> declara un único método sin parámetros: <xref:System.IAsyncDisposable.DisposeAsync>. Cualquier clase no sellada debe tener un método `DisposeAsyncCore()` adicional que también devuelva un elemento <xref:System.Threading.Tasks.ValueTask>.

- Una implementación de <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> `public` que no tenga parámetros.
- Un método `protected virtual ValueTask DisposeAsyncCore()` cuya signatura sea:

```csharp
protected virtual ValueTask DisposeAsyncCore()
{
}
```

El método `DisposeAsyncCore()` es `virtual` para que las clases derivadas puedan definir la limpieza adicional en sus invalidaciones.

### <a name="the-disposeasync-method"></a>El método DisposeAsync()

Se llama de forma implícita al método `DisposeAsync()` sin parámetros `public` en una instrucción `await using`, y su propósito consiste en liberar recursos no administrados, realizar una limpieza general e indicar que el finalizador, si existe, no necesita ejecutarse. La liberación de la memoria asociada a un objeto administrado siempre corresponde al [recolector de elementos no utilizados](index.md). Debido a esto, se realiza una implementación estándar:

```csharp
public async ValueTask DisposeAsync()
{
    // Perform async cleanup.
    await DisposeAsyncCore();

    // Dispose of managed resources.
    Dispose(false);
    // Suppress finalization.
    GC.SuppressFinalize(this);
}
```

> [!NOTE]
> Una diferencia principal en el patrón de eliminación asincrónica en comparación con el patrón de eliminación es que la llamada desde <xref:System.IAsyncDisposable.DisposeAsync> al método de sobrecarga `Dispose(bool)` recibe el valor `false` como argumento. Sin embargo, al implementar el método <xref:System.IDisposable.Dispose?displayProperty=nameWithType>, se pasa el valor `true`. Esto ayuda a garantizar la equivalencia funcional con el patrón de eliminación sincrónico y garantiza aún más que se invoquen las rutas de acceso al código finalizador. En otras palabras, el método `DisposeAsyncCore()` eliminará los recursos administrados de forma asincrónica, por lo que no querrá eliminarlos también de forma sincrónica. Por tanto, llame a `Dispose(false)` en lugar de a `Dispose(true)`.

## <a name="implement-the-async-dispose-pattern"></a>Implementación del patrón de eliminación asincrónica

Todas las clases no selladas deben considerarse una clase base potencial, ya que se podrían heredar. Cuando se implementa el patrón de eliminación asincrónica para cualquier clase base potencial, se debe proporcionar el método `protected virtual ValueTask DisposeAsyncCore()`. Este es un ejemplo de implementación del patrón de eliminación asincrónica que usa un elemento <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

En el ejemplo anterior se usaba el elemento <xref:System.Text.Json.Utf8JsonWriter>. Para obtener más información sobre `System.Text.Json`, consulte [migración de Newtonsoft.Json a System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).

## <a name="using-async-disposable"></a>Uso de la eliminación asincrónica

Para usar correctamente un objeto que implementa la interfaz <xref:System.IAsyncDisposable>, utilice las palabras clave [await](../../csharp/language-reference/operators/await.md) y [using](../../csharp/language-reference/keywords/using.md) juntas. Tenga en cuenta el ejemplo siguiente, donde se crea una instancia de la clase `ExampleAsyncDisposable` y, a continuación, se encapsula en una instrucción `await using`.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> Use el método de extensión <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> de la interfaz <xref:System.IAsyncDisposable> para configurar el modo en que se serializa la continuación de la tarea en su contexto o programador original. Para obtener más información sobre `ConfigureAwait`, consulte las [preguntas más frecuentes sobre ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq/).

En situaciones en las que no se necesita el uso de `ConfigureAwait`, la instrucción `await using` se podría simplificar de la siguiente manera:

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

Además, se podría escribir para utilizar el ámbito implícito de una [declaración "using"](../../csharp/whats-new/csharp-8.md#using-declarations).

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a>Declaraciones "using" apiladas

En situaciones en las que se crean y se utilizan varios objetos que implementan <xref:System.IAsyncDisposable>, es posible que el apilamiento de instrucciones `using` en condiciones errantes pudiera impedir la realización de llamadas a <xref:System.IAsyncDisposable.DisposeAsync>. Para ayudar a evitar un posible problema, debe evitar el apilamiento y, en su lugar, seguir este patrón de ejemplo:

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a>Vea también

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
