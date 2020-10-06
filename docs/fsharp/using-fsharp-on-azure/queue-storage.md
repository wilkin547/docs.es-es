---
title: Introducción a Azure Queue Storage mediante F#
description: Las colas de Azure proporcionan mensajería asincrónica confiable entre componentes de aplicaciones. La mensajería en la nube permite que los componentes de las aplicaciones se escalen de forma independiente.
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: daa5372b7903f10c0d966c5c92e35c8bf9d362d8
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756226"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>Introducción a Azure Queue Storage mediante F\#

El almacenamiento en cola de Azure proporciona mensajería en la nube entre componentes de aplicaciones. A la hora de diseñar aplicaciones para escala, los componentes de las mismas suelen desacoplarse para poder escalarlos de forma independiente. El almacenamiento en cola ofrece mensajería asincrónica para la comunicación entre los componentes de las aplicaciones, independientemente de si se ejecutan en la nube, en el escritorio, en un servidor local o en un dispositivo móvil. Además, este tipo de almacenamiento admite la administración de tareas asincrónicas y la creación de flujos de trabajo de procesos.

### <a name="about-this-tutorial"></a>Acerca de este tutorial

En este tutorial se muestra cómo escribir código de F # para algunas tareas comunes mediante el almacenamiento de colas de Azure. Entre las tareas descritas se incluyen la creación y eliminación de colas y la adición, lectura y eliminación de mensajes de la cola.

Para obtener información general conceptual sobre Queue Storage, consulte [la guía de .net para Queue Storage](/azure/storage/storage-dotnet-how-to-use-queues).

## <a name="prerequisites"></a>Requisitos previos

Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).
También necesitará la clave de acceso de almacenamiento para esta cuenta.

## <a name="create-an-f-script-and-start-f-interactive"></a>Crear un script de F # e iniciar F# interactivo

Los ejemplos de este artículo se pueden usar en una aplicación de F # o en un script de F #. Para crear un script de F #, cree un archivo con la `.fsx` extensión, por ejemplo `queues.fsx` , en el entorno de desarrollo de f #.

A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` paquete y la referencia `WindowsAzure.Storage.dll` en el script mediante una `#r` Directiva.

### <a name="add-namespace-declarations"></a>Incorporación de declaraciones de espacio de nombres

Agregue las siguientes instrucciones `open` en la parte superior del archivo `queues.fsx`:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>Obtención de la cadena de conexión

Necesitará una cadena de conexión Azure Storage para este tutorial. Para obtener más información sobre las cadenas de conexión, consulte Configuración de las [cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).

En el tutorial, escribirá la cadena de conexión en el script, de la siguiente manera:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

Sin embargo, esto **no se recomienda** para los proyectos reales. La clave de la cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento. Siempre debe proteger la clave de la cuenta de almacenamiento. Evite distribuirla a otros usuarios, codificarla de forma rígida o guardarla en un archivo de texto que sea accesible a otros usuarios. Puede volver a generar la clave con el Azure Portal si cree que se ha puesto en peligro.

En el caso de las aplicaciones reales, la mejor manera de mantener la cadena de conexión de almacenamiento se encuentra en un archivo de configuración. Para capturar la cadena de conexión de un archivo de configuración, puede hacer lo siguiente:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

El uso del Administrador de configuración Azure es opcional. También puede usar una API, como el tipo de .NET Framework `ConfigurationManager` .

### <a name="parse-the-connection-string"></a>Análisis de la cadena de conexión

Para analizar la cadena de conexión, use:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

Esto devolverá un `CloudStorageAccount` .

### <a name="create-the-queue-service-client"></a>Creación del cliente del servicio Cola

La `CloudQueueClient` clase permite recuperar las colas almacenadas en Queue Storage. Esta es una forma de crear el cliente de servicio:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

Ahora ya puede escribir código que lee y escribe datos en el Almacenamiento en cola.

## <a name="create-a-queue"></a>Creación de una cola

En este ejemplo se muestra cómo crear una cola si aún no existe:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>un mensaje en una cola

Para insertar un mensaje en una cola existente, cree primero un nuevo `CloudQueueMessage` . A continuación, llame al `AddMessage` método. `CloudQueueMessage`Se puede crear una a partir de una cadena (en formato UTF-8) o de una `byte` matriz, de la siguiente manera:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>siguiente mensaje

Puede inspeccionar el mensaje situado en la parte delantera de una cola, sin quitarlo de la cola, llamando al `PeekMessage` método.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>Obtener el siguiente mensaje para el procesamiento

Puede recuperar el mensaje al principio de una cola para su procesamiento mediante una llamada al `GetMessage` método.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

Más adelante indicará el procesamiento correcto del mensaje mediante `DeleteMessage` .

## <a name="change-the-contents-of-a-queued-message"></a>contenido de un mensaje en cola

Puede cambiar el contenido de un mensaje recuperado en la cola. Si el mensaje representa una tarea de trabajo, puede usar esta característica para actualizar el estado de la tarea de trabajo. El siguiente código actualiza el mensaje de la cola con contenido nuevo y amplía el tiempo de espera de la visibilidad en 60 segundos más. De este modo, se guarda el estado de trabajo asociado al mensaje y se le proporciona al cliente un minuto más para que siga elaborando el mensaje. Esta técnica se puede utilizar para realizar un seguimiento de los flujos de trabajo de varios pasos en los mensajes en cola, sin que sea necesario volver a empezar desde el principio si se produce un error en un paso del proceso a causa de un error de hardware o software. Normalmente, también tendría que mantener un número de reintentos y, si el mensaje se vuelve a intentar más de un número de veces, lo eliminaría. Esto proporciona protección frente a un mensaje que produce un error en la aplicación cada vez que se procesa.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>siguiente mensaje de la cola

El código quita un mensaje de una cola en dos pasos. Cuando llame a `GetMessage` , obtendrá el siguiente mensaje en una cola. Un mensaje devuelto por `GetMessage` se hace invisible a cualquier otro código de lectura de mensajes de esta cola. De forma predeterminada, este mensaje permanece invisible durante 30 segundos. Para terminar de quitar el mensaje de la cola, también debe llamar a `DeleteMessage` . Este proceso de extracción de un mensaje que consta de dos pasos garantiza que si su código no puede procesar un mensaje a causa de un error de hardware o software, otra instancia de su código puede obtener el mismo mensaje e intentarlo de nuevo. El código siguiente llama a `DeleteMessage` justo después de haberse procesado el mensaje.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>Uso de flujos de trabajo asincrónicos con API comunes de almacenamiento de colas

En este ejemplo se muestra cómo usar un flujo de trabajo asincrónico con API comunes de almacenamiento de colas.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>Opciones adicionales para quitar mensajes de la cola

Hay dos formas de personalizar la recuperación de mensajes de una cola.
En primer lugar, puede obtener un lote de mensajes (hasta 32). En segundo lugar, puede establecer un tiempo de espera de la invisibilidad más largo o más corto para que el código disponga de más o menos tiempo para procesar cada mensaje. En el ejemplo de código siguiente `GetMessages` se usa para obtener 20 mensajes en una llamada y, a continuación, se procesa cada mensaje. También establece el tiempo de espera de la invisibilidad en cinco minutos para cada mensaje. Los 5 minutos se inician para todos los mensajes al mismo tiempo, por lo que después de que pasen 5 minutos desde la llamada a `GetMessages` , los mensajes que no se hayan eliminado volverán a estar visibles.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>la longitud de la cola

Puede obtener una estimación del número de mensajes existentes en una cola. El `FetchAttributes` método pide al Queue Service que recupere los atributos de la cola, incluido el recuento de mensajes. La `ApproximateMessageCount` propiedad devuelve el último valor recuperado por el `FetchAttributes` método, sin llamar a la Queue Service.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>Eliminación de una cola

Para eliminar una cola y todos los mensajes contenidos en ella, llame al `Delete` método en el objeto Queue.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>Pasos siguientes

Ahora que está familiarizado con los aspectos básicos del almacenamiento de colas, utilice estos vínculos para obtener más información acerca de tareas de almacenamiento más complejas.

- [API de Azure Storage para .NET](/dotnet/api/overview/azure/storage)
- [Azure Storage proveedor de tipos](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Blog del equipo de Azure Storage](/archive/blogs/windowsazurestorage/)
- [Configuración de las cadenas de conexión de Azure Storage](/azure/storage/common/storage-configure-connection-string)
- [Azure Storage Services REST API Reference](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference) (Referencia de la API REST de los servicios de Azure Storage)
