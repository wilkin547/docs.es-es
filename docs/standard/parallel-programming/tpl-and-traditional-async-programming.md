---
title: TPL y la programación asincrónica tradicional de .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, with other asynchronous models
ms.assetid: e7b31170-a156-433f-9f26-b1fc7cd1776f
ms.openlocfilehash: 7db031c655980dd800de77cbbd6a07a0ba94b33b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284889"
---
# <a name="tpl-and-traditional-net-framework-asynchronous-programming"></a>TPL y la programación asincrónica tradicional de .NET Framework
.NET Framework proporciona los siguientes dos modelos estándar para realizar las operaciones asincrónicas enlazadas a E/S y enlazadas a cálculos:  
  
- Modelo de programación asincrónica (APM), en el que las operaciones asincrónicas se representan mediante un par de métodos Begin/End como <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> y <xref:System.IO.Stream.EndRead%2A?displayProperty=nameWithType>.  
  
- Modelo asincrónico basado en eventos (EAP) en el que las operaciones asincrónicas se representan mediante un par método-evento que se denomina *OperationName*Async y *OperationName*Completed; por ejemplo, <xref:System.Net.WebClient.DownloadStringAsync%2A?displayProperty=nameWithType> y <xref:System.Net.WebClient.DownloadStringCompleted?displayProperty=nameWithType>. (EAP apareció por primera vez en .NET Framework versión 2.0).  
  
 La biblioteca TPL (Task Parallel Library, biblioteca de procesamiento paralelo basado en tareas) se puede usar de varias maneras junto con cualquiera de los modelos asincrónicos. Puede exponer las operaciones de APM y EAP como tareas a los consumidores de la biblioteca o puede exponer los modelos de APM, pero usar objetos de tarea para implementarlos internamente. En ambos escenarios, al usar los objetos de tarea, puede simplificar el código y aprovechar la siguiente funcionalidad útil:  
  
- Registre las devoluciones de llamada, en el formulario de continuaciones de la tarea, en cualquier momento después de que se haya iniciado la tarea.  
  
- Coordine varias operaciones que se ejecutan en respuesta a un método `Begin_`, mediante los métodos <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>, <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A>, <xref:System.Threading.Tasks.Task.WaitAll%2A> o <xref:System.Threading.Tasks.Task.WaitAny%2A>.  
  
- Encapsule las operaciones asincrónicas enlazadas a E/S y enlazadas a cálculos en el mismo objeto de tarea.  
  
- Supervise el estado del objeto de tarea.  
  
- Serialice las referencias del estado una operación para un objeto de tarea mediante <xref:System.Threading.Tasks.TaskCompletionSource%601>.  
  
## <a name="wrapping-apm-operations-in-a-task"></a>Ajustar las operaciones de APM en una tarea  
 Las clases <xref:System.Threading.Tasks.TaskFactory?displayProperty=nameWithType> y <xref:System.Threading.Tasks.TaskFactory%601?displayProperty=nameWithType> proporcionan varias sobrecargas de los métodos<xref:System.Threading.Tasks.TaskFactory.FromAsync%2A?displayProperty=nameWithType> y<xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType>que permiten encapsular un par de métodos Begin/End en una instancia <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601>. Las diversas sobrecargas hospedan cualquier par de métodos de Begin/End que tenga entre cero y tres parámetros de entrada.  
  
 Para los pares que tienen métodos `End` que devuelven un valor (`Function` en Visual Basic), use los métodos de <xref:System.Threading.Tasks.TaskFactory%601> que crean un objeto <xref:System.Threading.Tasks.Task%601>. Para los métodos `End` que devuelven un valor void (`Sub` en Visual Basic), use los métodos de <xref:System.Threading.Tasks.TaskFactory> que crean un objeto <xref:System.Threading.Tasks.Task>.  
  
 En los pocos casos en los que el método `Begin` tiene más de tres parámetros o contiene parámetros `ref` o `out`, se proporcionan las sobrecargas `FromAsync` adicionales que encapsulan sólo el método `End`.  
  
 En el ejemplo siguiente, se muestra la signatura para la sobrecarga `FromAsync` que coincide con los métodos <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType> y <xref:System.IO.FileStream.EndRead%2A?displayProperty=nameWithType>. Esta sobrecarga toma los tres parámetros de entrada siguientes.  
  
 [!code-csharp[FromAsync#01](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#01)]
 [!code-vb[FromAsync#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#01)]  
  
 El primer parámetro es un delegado <xref:System.Func%606> que coincide con la signatura del método <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType>. El segundo parámetro es un delegado <xref:System.Func%602> que toma una interfaz <xref:System.IAsyncResult> y devuelve `TResult`. Dado que <xref:System.IO.FileStream.EndRead%2A> devuelve un entero, el compilador deduce el tipo de `TResult` como <xref:System.Int32> y el tipo de la tarea como <xref:System.Threading.Tasks.Task>. Los últimos cuatro parámetros son idénticos a los del método <xref:System.IO.FileStream.BeginRead%2A?displayProperty=nameWithType>:  
  
- Búfer donde se van a almacenar los datos de archivo.  
  
- Desplazamiento en el búfer donde deben comenzar a escribirse los datos.  
  
- Cantidad máxima de datos que se van a leer del archivo.  
  
- Un objeto opcional que almacena los datos de estado definidos por el usuario que se van a pasar a la devolución de llamada.  
  
### <a name="using-continuewith-for-the-callback-functionality"></a>Usar ContinueWith para la funcionalidad de devolución de llamada  
 Si necesita obtener acceso a los datos del archivo, en contraposición a solo el número de bytes, el método <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> no es suficiente. En su ligar, use <xref:System.Threading.Tasks.Task>, cuya propiedad `Result` contiene los datos de archivo. Puede hacer si agrega una continuación a la tarea original. La continuación realiza el trabajo que normalmente realizaría el delegado <xref:System.AsyncCallback>. Se invoca cuando se completa el antecedente y se ha rellenado el búfer de datos. (El objeto <xref:System.IO.FileStream> se debería cerrar antes de devolver un valor).  
  
 En el siguiente ejemplo se muestra cómo devolver un objeto <xref:System.Threading.Tasks.Task> que encapsula el par BeginRead/EndRead de la clase <xref:System.IO.FileStream>.  
  
 [!code-csharp[FromAsync#03](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#03)]
 [!code-vb[FromAsync#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#03)]  
  
 A continuación, se puede llamar al método de la forma siguiente.  
  
 [!code-csharp[FromAsync#04](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#04)]
 [!code-vb[FromAsync#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#04)]  
  
### <a name="providing-custom-state-data"></a>Proporcionar los datos de estado personalizados  
 En las operaciones <xref:System.IAsyncResult> típicas, si el delegado <xref:System.AsyncCallback> requiere algún dato de estado personalizado, tiene que pasarlo a través del último parámetro `Begin` para que los datos se puedan empaquetar en el objeto <xref:System.IAsyncResult> que se pasará finalmente al método de devolución de llamada. Normalmente no se requiere esto cuando se usan los métodos `FromAsync`. Si los datos personalizados son conocidos para la continuación, se pueden capturar directamente en el delegado de continuación. El siguiente ejemplo se parece el ejemplo anterior, pero en lugar de examinar la propiedad `Result` del antecedente, la continuación examina los datos de estado personalizados que son directamente accesibles al delegado de usuario de la continuación.  
  
 [!code-csharp[FromAsync#05](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#05)]
 [!code-vb[FromAsync#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#05)]  
  
### <a name="synchronizing-multiple-fromasync-tasks"></a>Sincronizar varias tareas FromAsync  
 Los métodos estáticos <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A> y <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAny%2A> proporcionan flexibilidad adicional cuando se usan junto con los métodos `FromAsync`. El siguiente ejemplo muestra cómo iniciar varias operaciones asincrónicas de E/S y, a continuación, espera a que todos ellas se completen antes de ejecutar la continuación.  
  
 [!code-csharp[FromAsync#06](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#06)]
 [!code-vb[FromAsync#06](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#06)]  
  
### <a name="fromasync-tasks-for-only-the-end-method"></a>Tareas FromAsync solo para el método End  
 En los pocos casos en los que el método `Begin` requiere más de tres parámetros de entrada o tiene parámetros `ref` o `out`, puede usar las sobrecargas `FromAsync`, por ejemplo, <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%28System.IAsyncResult%2CSystem.Func%7BSystem.IAsyncResult%2C%600%7D%29?displayProperty=nameWithType>, que representa sólo el método `End`. Estos métodos también se pueden usar en cualquier escenario en el que se pasa <xref:System.IAsyncResult> y desea encapsularlo en una tarea.  
  
 [!code-csharp[FromAsync#07](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#07)]
 [!code-vb[FromAsync#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#07)]  
  
### <a name="starting-and-canceling-fromasync-tasks"></a>Iniciar y cancelar las tareas FromAsync  
 La tarea devuelta por un método `FromAsync` tiene un estado de WaitingForActivation y la iniciará el sistema en algún momento una vez creada la tarea. Si intenta llamar a Start en este tipo de tarea, se producirá una excepción.  
  
 No puede cancelar una tarea `FromAsync`, porque las API subyacentes de .NET Framework admiten actualmente la cancelación en curso del la E/S de archivo o red. Puede agregar la funcionalidad de cancelación a un método que encapsula una llamada `FromAsync`, pero sólo puede responder a la cancelación antes de que se llame a `FromAsync` o después de completar (por ejemplo, en una tarea de continuación).  
  
 Algunas clases que admiten EAP, por ejemplo, <xref:System.Net.WebClient>, admiten la cancelación y esa funcionalidad de cancelación nativa se puede integrar mediante los tokens de cancelación.  
  
## <a name="exposing-complex-eap-operations-as-tasks"></a>Exponer las operaciones de EAP complejas como tareas  
 La TPL no proporciona ningún método diseñado específicamente para encapsular una operación asincrónica basada en eventos del mismo modo que la familia de métodos `FromAsync` ajusta el modelo <xref:System.IAsyncResult>. Sin embargo, TPL proporciona la clase <xref:System.Threading.Tasks.TaskCompletionSource%601?displayProperty=nameWithType>, que se puede usar para representar cualquier conjunto arbitrario de operaciones como <xref:System.Threading.Tasks.Task%601>. Las operaciones pueden ser sincrónicas o asincrónicas y pueden ser enlazadas a E/S o enlazadas a cálculo, o ambos.  
  
 En el siguiente ejemplo se muestra cómo usar <xref:System.Threading.Tasks.TaskCompletionSource%601> para exponer un conjunto de operaciones <xref:System.Net.WebClient> asincrónicas al código de cliente como un objeto <xref:System.Threading.Tasks.Task%601> básico. El método permite escribir una matriz de direcciones URL de web y un término o nombre que se va a buscar y, a continuación, devuelve el número de veces que aparece el término de búsqueda en cada sitio.  
  
 [!code-csharp[FromAsync#10](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/snippet10.cs#10)]
 [!code-vb[FromAsync#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/snippet10.vb#10)]  
  
 Para obtener un ejemplo más completo, en donde se incluye control de excepciones adicional y se muestra cómo llamar al método desde código de cliente, vea [Procedimiento: Encapsulado de patrones de EAP en una tarea](how-to-wrap-eap-patterns-in-a-task.md).  
  
 Recuerde que TaskCompletionSource iniciará cualquier tarea creada por <xref:System.Threading.Tasks.TaskCompletionSource%601> y, por consiguiente, el código de usuario no debería llamar al método Start en esa tarea.  
  
## <a name="implementing-the-apm-pattern-by-using-tasks"></a>Implementar el modelo de APM usando las tareas  
 En algunos escenarios, puede ser deseable exponer directamente el modelo <xref:System.IAsyncResult> mediante pares de métodos Begin/End en una API. Por ejemplo, quizás desee mantener la coherencia con las API existentes o puede haber automatizado herramientas que requieren este modelo. En tales casos, puede usar las tareas para simplificar la forma en que se implementa internamente el modelo de APM.  
  
 En el siguiente ejemplo se muestra cómo usar las tareas para implementar un par de métodos Begin/End de APM para un método enlazado a cálculo de ejecución prolongada.  
  
 [!code-csharp[FromAsync#09](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#09)]
 [!code-vb[FromAsync#09](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#09)]  
  
## <a name="using-the-streamextensions-sample-code"></a>Usar el código de ejemplo de StreamExtensions  
 El archivo *StreamExtensions.cs*, en el repositorio [Extensiones adicionales en paralelo de .NET Standard](/samples/dotnet/samples/parallel-programming-extensions-extras-cs/), contiene varias implementaciones de la referencia que usan objetos de `Task` para la E/S asincrónica de archivo y red.
  
## <a name="see-also"></a>Vea también

- [Biblioteca TPL](task-parallel-library-tpl.md)
