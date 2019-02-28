---
title: Introducción a Azure Queue storage medianteF#
description: Las colas de Azure proporcionan mensajería confiable y asincrónica entre los componentes de la aplicación. En la nube permite mensajería los componentes de aplicación para escalar de forma independiente.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 58a46dfe905a32be77a13d11df8f0544546ea0ed
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974281"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>Introducción a Azure Queue storage mediante F\#

Azure Queue storage proporciona mensajería entre componentes de la aplicación en la nube. En el diseño de aplicaciones para escala, los componentes de aplicación suelen desacoplarse para que puedan escalarse de forma independiente. Almacenamiento en cola ofrece mensajería asincrónica para la comunicación entre componentes de la aplicación, independientemente de si se ejecutan en la nube, en el escritorio, en un servidor local o en un dispositivo móvil. Almacenamiento de colas también admite la administración de tareas asincrónicas y creación de flujos de trabajo de proceso.

### <a name="about-this-tutorial"></a>Acerca de este tutorial

Este tutorial muestra cómo escribir F# código para algunas tareas comunes de usar Azure Queue storage. Tareas descritas incluyen crear y eliminar colas y agregar, leer y eliminar mensajes de la cola.

Información general conceptual de queue storage, consulte [la Guía de .NET para queue storage](/azure/storage/storage-dotnet-how-to-use-queues).

## <a name="prerequisites"></a>Requisitos previos

Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).
También necesitará la clave de acceso de almacenamiento para esta cuenta.

## <a name="create-an-f-script-and-start-f-interactive"></a>Crear un F# Script e iniciar F# interactivo

Los ejemplos de este artículo pueden usarse en cualquiera un F# aplicación o un F# secuencia de comandos. Para crear un F# de script, cree un archivo con el `.fsx` extensión, por ejemplo `queues.fsx`, en su F# entorno de desarrollo.

A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` paquete y referencia `WindowsAzure.Storage.dll` en el script mediante un `#r`directiva.

### <a name="add-namespace-declarations"></a>Agregue las declaraciones de espacio de nombres

Agregue el siguiente `open` instrucciones a la parte superior de la `queues.fsx` archivo:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>Obtener la cadena de conexión

Necesitará una cadena de conexión de Azure Storage para este tutorial. Para obtener más información acerca de las cadenas de conexión, consulte [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).

Para este tutorial, deberá escribir la cadena de conexión en el script, similar al siguiente:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

Sin embargo, esto es **no recomienda** proyectos reales. La clave de cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento. Siempre debe proteger la clave de cuenta de almacenamiento. Evite distribuirla a otros usuarios, codificarla de forma o guardarlo en un archivo de texto sin formato que sea accesible a otros usuarios. Puede volver a generar la clave mediante Azure Portal si cree que puede verse comprometida.

Las aplicaciones para el real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración. Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

Con el Administrador de configuración de Azure es opcional. También puede usar una API como .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizar la cadena de conexión

Para analizar la cadena de conexión, use:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

Esto devolverá un `CloudStorageAccount`.

### <a name="create-the-queue-service-client"></a>Crear al cliente del servicio cola

La `CloudQueueClient` clase le permite recuperar las colas almacenadas en almacenamiento de la cola. Aquí es una forma de crear al cliente del servicio:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

Ahora está listo para escribir código que lee y escribe datos en almacenamiento de la cola.

## <a name="create-a-queue"></a>Crear una cola

En este ejemplo se muestra cómo crear una cola si aún no existe:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>Insertar un mensaje en una cola

Para insertar un mensaje en una cola existente, primero debe crear un nuevo `CloudQueueMessage`. A continuación, llame a la `AddMessage` método. Un `CloudQueueMessage` pueden crearse desde una cadena (en formato UTF-8) o un `byte` matriz, similar al siguiente:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>Inspeccionar el mensaje siguiente

Puede inspeccionar el mensaje de la parte delantera de una cola, sin quitarlo de la cola, mediante una llamada a la `PeekMessage` método.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>Obtiene el siguiente mensaje de procesamiento

Puede recuperar el mensaje en la parte delantera de una cola para su procesamiento mediante una llamada a la `GetMessage` método.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

Procesamiento correcto del mensaje se indica más adelante mediante el uso de `DeleteMessage`.

## <a name="change-the-contents-of-a-queued-message"></a>Cambiar el contenido de un mensaje en cola

Puede cambiar el contenido de un mensaje recuperado en lugar de en la cola. Si el mensaje representa una tarea de trabajo, puede utilizar esta característica para actualizar el estado de la tarea de trabajo. El siguiente código actualiza el mensaje de cola con contenido nuevo y establece el tiempo de espera de visibilidad en 60 segundos. Esto guarda el estado del trabajo asociado con el mensaje y da al cliente minuto más para que siga elaborando el mensaje. Puede usar esta técnica para realizar el seguimiento de los flujos de trabajo de varios pasos en los mensajes de cola, sin tener que empezar de nuevo desde el principio si se produce un error en un paso de procesamiento debido a un error de hardware o software. Normalmente, también mantendría un número de reintentos y si el mensaje se intentara más de cierto número de veces, lo eliminaría. Esto protege contra un mensaje que desencadena un error de aplicación cada vez que se procese.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>El siguiente mensaje de la cola

Quita el código de la cola un mensaje de una cola en dos pasos. Cuando se llama a `GetMessage`, obtendrá el siguiente mensaje en una cola. Un mensaje devuelto por `GetMessage` se hace invisible a cualquier otro código de lectura de mensajes de esta cola. De forma predeterminada, este mensaje permanece invisible durante 30 segundos. Para terminar de quitar el mensaje de la cola, también se debe llamar `DeleteMessage`. Este proceso en dos pasos de la eliminación de un mensaje garantiza que si se produce un error en el código procesar un mensaje debido a un error de hardware o software, otra instancia de su código puede obtener el mismo mensaje y vuelva a intentarlo. El código llama a `DeleteMessage` justo después de haber procesado el mensaje.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>Usar flujos de trabajo asincrónicos con API comunes de almacenamiento de cola

En este ejemplo se muestra cómo usar un flujo de trabajo asincrónico con API comunes de almacenamiento de cola.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>Opciones adicionales para quitando de la cola de mensajes

Hay dos formas de personalizar la recuperación de mensajes de una cola.
En primer lugar, puede obtener un lote de mensajes (hasta 32). En segundo lugar, puede establecer un tiempo de espera de invisibilidad más largo o más corto que el código más o menos tiempo para procesar cada mensaje. El siguiente ejemplo de código usa `GetMessages` para obtener 20 mensajes en uno, llame a y, a continuación, procesa cada mensaje. También se establece el tiempo de espera de invisibilidad en cinco minutos para cada mensaje. Tenga en cuenta que los 5 minutos se inicia para todos los mensajes al mismo tiempo, tras 5 minutos ha transcurrido desde la llamada a `GetMessages`, todos los mensajes que no se han eliminado volverán a visibles.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>Obtener la longitud de cola

Puede obtener una estimación del número de mensajes en una cola. El `FetchAttributes` método solicita a Queue service para recuperar los atributos de la cola, incluido el número de mensajes. El `ApproximateMessageCount` propiedad devuelve el último valor recuperado por el `FetchAttributes` método sin llamar a Queue service.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>Eliminar una cola

Para eliminar una cola y todos los mensajes contenidos en ella, llame a la `Delete` método en el objeto de cola.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha aprendido los conceptos básicos de Queue storage, siga estos vínculos para obtener información sobre tareas de almacenamiento más complejas.

- [API de Azure Storage para .NET](/dotnet/api/overview/azure/storage)
- [Proveedor de tipos de almacenamiento de Azure](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Blog del equipo de almacenamiento de Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Configurar cadenas de conexión de Azure Storage](/azure/storage/common/storage-configure-connection-string)
- [Referencia de API de REST de servicios de Azure Storage](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
