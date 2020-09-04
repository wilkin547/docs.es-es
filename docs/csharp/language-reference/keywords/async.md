---
description: 'async: Referencia de C#'
title: 'async: Referencia de C#'
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 5a70389c9c423300fad03123cfc4738dfe10e481
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89118525"
---
# <a name="async-c-reference"></a>async (Referencia de C#)

Use el modificador `async` para especificar que un método, una [expresión lambda](../operators/lambda-expressions.md) o un [método anónimo](../operators/delegate-operator.md) es asincrónico. Si usa este modificador en un método o una expresión, se hace referencia al mismo como un *método asincrónico*. En el ejemplo siguiente se define un método asincrónico denominado `ExampleMethodAsync`:

```csharp
public async Task<int> ExampleMethodAsync()
{
    //...
}
```

Si no está familiarizado con la programación asincrónica o no entiende cómo un método asincrónico usa el [operador `await`](../operators/await.md) para hacer el trabajo de larga duración sin bloquear el subproceso del autor de la llamada, lea la introducción de [Programación asincrónica con async y await](../../programming-guide/concepts/async/index.md). El siguiente código se encuentra dentro de un método asincrónico y llama al método <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>:

```csharp
string contents = await httpClient.GetStringAsync(requestUrl);
```

Un método asincrónico se ejecuta sincrónicamente hasta alcanzar la primera expresión `await`, en la que se suspende el método hasta que se complete la tarea en espera. Mientras tanto, el control vuelve al llamador del método, como se muestra en el ejemplo de la sección siguiente.

Si el método que la palabra clave `async` modifica no contiene una expresión o instrucción `await`, el método se ejecuta de forma sincrónica. Una advertencia del compilador alerta de cualquier método asincrónico que no contenga instrucciones de `await`, porque esa situación podría indicar un error. Vea [Advertencia del compilador (nivel 1) CS4014](../compiler-messages/cs4014.md).

 La palabra clave `async` es contextual en el sentido de que es una palabra clave cuando modifica un método, una expresión lambda o un método anónimo. En todos los demás contextos, se interpreta como identificador.

## <a name="example"></a>Ejemplo
En el ejemplo siguiente se muestra la estructura y el flujo de control entre un controlador de eventos asincrónicos, `StartButton_Click`, y un método asincrónico, `ExampleMethodAsync`. El resultado del método asincrónico es el número de caracteres de una página web. El código es adecuado para una aplicación Windows Presentation Foundation (WPF) o de la Tienda Windows creada en Visual Studio; vea los comentarios del código para configurar la aplicación.

Puede ejecutar este código en Visual Studio como una aplicación Windows Presentation Foundation (WPF) o una aplicación de la Tienda Windows. Necesita un control de botón denominado `StartButton` y un control de cuadro de texto denominado `ResultsTextBox`. Recuerde establecer los nombres y el controlador de manera que tenga algo similar a esto:

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"
        Click="StartButton_Click" Name="StartButton"/>
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>
```

Para ejecutar el código como una aplicación WPF:

- Pegue este código en la clase `MainWindow` en MainWindow.xaml.cs.
- Agregue una referencia a System.Net.Http.
- Agregue una directiva `using` a System.Net.Http.

Para ejecutar el código como una aplicación de la Tienda Windows:

- Pegue este código en la clase `MainPage` en MainPage.xaml.cs.
- Agregue directivas using para System.Net.Http y System.Threading.Tasks.

[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]

> [!IMPORTANT]
> Para obtener más información sobre las tareas y el código que se ejecuta mientras se espera la finalización de una tarea, vea [Programación asincrónica con async y await](../../programming-guide/concepts/async/index.md). Para ver un ejemplo completo de la consola que usa elementos similares, consulte el artículo [Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).

## <a name="return-types"></a>Tipos de valor devueltos
Un método asincrónico puede tener los siguientes tipos de valor devuelto:

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- [void](../builtin-types/void.md). Los métodos `async void` no suelen ser recomendables para código que no sea controladores de eventos dado que los autores de la llamada no pueden usar `await` con esos métodos y deben implementar otro mecanismo para informar sobre la finalización correcta o condiciones de error.
- A partir de C# 7.0, cualquier tipo que tenga un método `GetAwaiter` accesible. El tipo `System.Threading.Tasks.ValueTask<TResult>` es una implementación de ese tipo. Está disponible agregando el paquete NuGet `System.Threading.Tasks.Extensions`.

El método asincrónico no puede declarar ningún parámetro [in](./in-parameter-modifier.md), [ref](./ref.md) o [out](./out-parameter-modifier.md), ni puede tener un [valor devuelto de referencia](../../programming-guide/classes-and-structs/ref-returns.md), pero puede llamar a los métodos que tienen estos parámetros.

Se puede especificar `Task<TResult>` como el tipo de valor devuelto de un método asincrónico si la instrucción [return](./return.md) del método especifica un operando de tipo `TResult`. Utilice `Task` si no se devuelve ningún valor significativo al completarse el método. Es decir, una llamada al método devuelve `Task`, pero cuando se completa `Task`, las expresiones `await` que esperan a que `Task` finalice se evalúan como `void`.

El tipo devuelto `void` se utiliza principalmente para definir controladores de eventos, que requieren ese tipo devuelto. El llamador de un método asincrónico que devuelva `void` no puede esperar a que finalice y no puede detectar las excepciones que el método inicia.

A partir de C# 7.0, devuelve otro tipo, normalmente un tipo de valor, que tiene un método `GetAwaiter` para minimizar las asignaciones de memoria en secciones críticas de rendimiento del código.

Para más información y ejemplos, vea [Tipos de valor devueltos asincrónicos](../../programming-guide/concepts/async/async-return-types.md).

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [await](../operators/await.md)
- [Programación asincrónica con async y await](../../programming-guide/concepts/async/index.md)
- [Procesamiento de tareas asincrónicas a medida que se completan](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)
