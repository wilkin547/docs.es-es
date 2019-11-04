---
title: Introducción a Azure Queue Storage mediante F#
description: Las colas de Azure proporcionan mensajería asincrónica confiable entre los componentes de la aplicación. La mensajería en la nube permite que los componentes de la aplicación se escalen de forma independiente.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: a09cbdd4b995e34177c110ce91b02162bb19dfa8
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423848"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>Introducción a Azure Queue Storage mediante F\#

Azure Queue Storage proporciona mensajería en la nube entre componentes de la aplicación. Al diseñar aplicaciones para escala, los componentes de la aplicación suelen estar desacoplados, por lo que se pueden escalar de manera independiente. Queue Storage ofrece mensajería asincrónica para la comunicación entre los componentes de la aplicación, tanto si se ejecutan en la nube, en el escritorio, en un servidor local o en un dispositivo móvil. Queue Storage también admite la administración de tareas asincrónicas y la creación de flujos de trabajo de proceso.

### <a name="about-this-tutorial"></a>Acerca de este tutorial

En este tutorial se muestra cómo F# escribir código para algunas tareas comunes mediante el almacenamiento de colas de Azure. Entre las tareas descritas se incluyen la creación y eliminación de colas y la adición, lectura y eliminación de mensajes de la cola.

Para obtener información general conceptual sobre Queue Storage, consulte [la guía de .net para Queue Storage](/azure/storage/storage-dotnet-how-to-use-queues).

## <a name="prerequisites"></a>Requisitos previos

Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).
También necesitará la clave de acceso de almacenamiento para esta cuenta.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creación de F# un script e F# Inicio interactivo

Los ejemplos de este artículo se pueden usar en una F# aplicación o en un F# script. Para crear un F# script, cree un archivo con la extensión `.fsx`, por ejemplo `queues.fsx`, en el F# entorno de desarrollo.

A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el paquete `WindowsAzure.Storage` y haga referencia a `WindowsAzure.Storage.dll` en el script mediante una directiva `#r`.

### <a name="add-namespace-declarations"></a>Agregar declaraciones de espacio de nombres

Agregue las siguientes instrucciones de `open` en la parte superior del archivo de `queues.fsx`:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>Obtener la cadena de conexión

Necesitará una cadena de conexión Azure Storage para este tutorial. Para obtener más información sobre las cadenas de conexión, consulte Configuración de las [cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).

En el tutorial, escribirá la cadena de conexión en el script, de la siguiente manera:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

Sin embargo, esto **no se recomienda** para los proyectos reales. La clave de la cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento. Siempre debe proteger la clave de la cuenta de almacenamiento. Evite distribuirla a otros usuarios, codificarla de forma rígida o guardarla en un archivo de texto sin formato al que puedan acceder otras personas. Puede volver a generar la clave mediante Azure portal si cree que puede estar en peligro.

En el caso de las aplicaciones reales, la mejor manera de mantener la cadena de conexión de almacenamiento se encuentra en un archivo de configuración. Para capturar la cadena de conexión de un archivo de configuración, puede hacer lo siguiente:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

El uso de Azure Configuration Manager es opcional. También puede usar una API, como el tipo `ConfigurationManager` del .NET Framework.

### <a name="parse-the-connection-string"></a>Analizar la cadena de conexión

Para analizar la cadena de conexión, use:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

Esto devolverá un `CloudStorageAccount`.

### <a name="create-the-queue-service-client"></a>Creación del cliente de Queue service

La clase `CloudQueueClient` permite recuperar las colas almacenadas en Queue Storage. Esta es una forma de crear el cliente del servicio:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

Ahora está listo para escribir código que lee y escribe datos en el almacenamiento en cola.

## <a name="create-a-queue"></a>Crear una cola

En este ejemplo se muestra cómo crear una cola si aún no existe:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>Insertar un mensaje en una cola

Para insertar un mensaje en una cola existente, cree primero un nuevo `CloudQueueMessage`. A continuación, llame al método `AddMessage`. Un `CloudQueueMessage` se puede crear a partir de una cadena (en formato UTF-8) o de una matriz de `byte`, de la siguiente manera:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>Inspeccionar el siguiente mensaje

Puede inspeccionar el mensaje situado en la parte delantera de una cola, sin quitarlo de la cola, llamando al método `PeekMessage`.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>Obtener el siguiente mensaje para el procesamiento

Puede recuperar el mensaje al principio de una cola para su procesamiento llamando al método `GetMessage`.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

Más adelante indicará el procesamiento correcto del mensaje mediante `DeleteMessage`.

## <a name="change-the-contents-of-a-queued-message"></a>Cambiar el contenido de un mensaje en cola

Puede cambiar el contenido de un mensaje recuperado en la cola. Si el mensaje representa una tarea de trabajo, podría usar esta característica para actualizar el estado de la tarea de trabajo. El siguiente código actualiza el mensaje de la cola con contenido nuevo y establece el tiempo de espera de visibilidad para extender otros 60 segundos. Esto guarda el estado de trabajo asociado al mensaje y proporciona al cliente otro minuto para seguir trabajando en el mensaje. Podría usar esta técnica para realizar un seguimiento de los flujos de trabajo de varios pasos en los mensajes en cola, sin tener que empezar de nuevo desde el principio si se produce un error en un paso de procesamiento debido a un error de hardware o software. Normalmente, también tendría que mantener un número de reintentos y, si el mensaje se vuelve a intentar más de un número de veces, lo eliminaría. Esto protege contra un mensaje que desencadena un error de aplicación cada vez que se procesa.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>Quitar de la cola el siguiente mensaje

El código quita de la cola un mensaje de una cola en dos pasos. Cuando se llama a `GetMessage`, se obtiene el siguiente mensaje en una cola. Un mensaje devuelto de `GetMessage` se vuelve invisible a cualquier otro código que lea mensajes de esta cola. De forma predeterminada, este mensaje permanece invisible durante 30 segundos. Para terminar de quitar el mensaje de la cola, también debe llamar a `DeleteMessage`. Este proceso de dos pasos para quitar un mensaje garantiza que si el código no puede procesar un mensaje debido a un error de hardware o software, otra instancia del código puede obtener el mismo mensaje e intentarlo de nuevo. El código llama `DeleteMessage` justo después de que se haya procesado el mensaje.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>Uso de flujos de trabajo asincrónicos con API comunes de almacenamiento de colas

En este ejemplo se muestra cómo usar un flujo de trabajo asincrónico con API comunes de almacenamiento de colas.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>Opciones adicionales para quitar mensajes de la cola

Hay dos maneras de personalizar la recuperación de mensajes de una cola.
En primer lugar, puede obtener un lote de mensajes (hasta 32). En segundo lugar, se puede establecer un tiempo de espera de invisibilidad más largo o más corto, lo que permite que el código tenga más o menos tiempo para procesar cada mensaje por completo. En el ejemplo de código siguiente se usa `GetMessages` para obtener 20 mensajes en una llamada y, a continuación, procesa cada mensaje. También establece el tiempo de espera de la invisibilidad en cinco minutos para cada mensaje. Tenga en cuenta que los 5 minutos se inician para todos los mensajes al mismo tiempo, por lo que después de pasar 5 minutos desde la llamada a `GetMessages`, los mensajes que no se han eliminado volverán a estar visibles.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>Obtener la longitud de la cola

Puede obtener una estimación del número de mensajes de una cola. El método `FetchAttributes` pide al Queue service que recupere los atributos de la cola, incluido el recuento de mensajes. La propiedad `ApproximateMessageCount` devuelve el último valor recuperado por el método `FetchAttributes`, sin llamar a la Queue service.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>Eliminar una cola

Para eliminar una cola y todos los mensajes contenidos en ella, llame al método `Delete` en el objeto Queue.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha aprendido los conceptos básicos de Queue Storage, siga estos vínculos para obtener más información sobre tareas de almacenamiento más complejas.

- [API de Azure Storage para .NET](/dotnet/api/overview/azure/storage)
- [Azure Storage proveedor de tipos](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Blog del equipo de Azure Storage](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Configurar cadenas de conexión de Azure Storage](/azure/storage/common/storage-configure-connection-string)
- [Referencia de la API de REST de Azure Storage Services](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
