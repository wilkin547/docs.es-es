---
title: "Introducción al almacenamiento de cola de Azure con F #"
description: "Las colas de Azure proporcionan mensajería confiable y asincrónica entre los componentes de la aplicación. La nube permite mensajería los componentes de aplicación para escalar de forma independiente."
keywords: "Visual f #, f #, funcional de programación,. NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 70dc554c-8f4d-42a7-8e2a-6438657d012a
ms.openlocfilehash: 50b2d69a1753add688aa14c3314a0ca2df9f03a4
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>Introducción al almacenamiento de cola de Azure con F # #

Almacenamiento de la cola de Azure proporciona mensajería entre los componentes de la aplicación en la nube. En el diseño de aplicaciones para la escala, a menudo se desvinculan componentes de la aplicación, por lo que puede escalar de forma independiente. Almacenamiento de cola ofrece mensajería asincrónica para la comunicación entre componentes de aplicaciones, si se están ejecutando en la nube, en el escritorio, en un servidor local o en un dispositivo móvil. Almacenamiento de cola también admite administrar tareas asincrónicas y generar flujos de trabajo de proceso.

### <a name="about-this-tutorial"></a>Acerca de este tutorial

Este tutorial muestra cómo escribir código de F # para algunas tareas comunes mediante el almacenamiento de la cola de Azure. Las tareas que se tratan incluyen creación y eliminación de colas y agregar, leer y eliminar mensajes de la cola.

Para obtener información conceptual de almacenamiento de cola, vea [la Guía de .NET para el almacenamiento de cola](/azure/storage/storage-dotnet-how-to-use-queues).

## <a name="prerequisites"></a>Requisitos previos

Para utilizar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).
También necesitará la clave de acceso de almacenamiento para esta cuenta.

## <a name="create-an-f-script-and-start-f-interactive"></a>Crear un Script de F # y el inicio de F # Interactive

Los ejemplos de este artículo pueden usarse en una aplicación de F # o un script de F #. Para crear un script de F #, cree un archivo con el `.fsx` extensión, por ejemplo `queues.fsx`, en el entorno de desarrollo de F #.

A continuación, use un [el Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` paquete y referencia `WindowsAzure.Storage.dll` en el script mediante un `#r`directiva.

### <a name="add-namespace-declarations"></a>Agregue las declaraciones de espacio de nombres

Agregue el siguiente `open` instrucciones a la parte superior de la `queues.fsx` archivo:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>Obtener la cadena de conexión

Necesitará una cadena de conexión de almacenamiento de Azure para este tutorial. Para obtener más información acerca de las cadenas de conexión, vea [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).

Para el tutorial, especificará la cadena de conexión en el script, similar al siguiente:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

Sin embargo, esto es **no recomienda** proyectos de una manera real. La clave de cuenta de almacenamiento es similar a la contraseña raíz para la cuenta de almacenamiento. Tenga siempre cuidado proteger la clave de cuenta de almacenamiento. Evitar la distribución a otros usuarios, codificar de forma rígida, o guardarlo en un archivo de texto sin formato sea accesible a otros usuarios. Puede volver a generar la clave mediante el Portal de Azure si cree que se han comprometido.

Las aplicaciones de una manera real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración. Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

Con el Administrador de configuración de Azure es opcional. También puede utilizar una API como .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizar la cadena de conexión

Para analizar la cadena de conexión, use:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

Esto devolverá una `CloudStorageAccount`.

### <a name="create-the-queue-service-client"></a>Crear al cliente del servicio cola

La `CloudQueueClient` clase le permite recuperar las colas almacenadas en almacenamiento de la cola. Aquí es una manera de crear al cliente del servicio:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

Ahora está listo para escribir código que lee datos de y escribe datos en el almacenamiento de cola.

## <a name="create-a-queue"></a>Crear una cola

En este ejemplo se muestra cómo crear una cola si aún no existe:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>Insertar un mensaje en una cola

Para insertar un mensaje en una cola existente, primero debe crear un nuevo `CloudQueueMessage`. A continuación, llame a la `AddMessage` método. A `CloudQueueMessage` pueden crearse desde una cadena (en formato UTF-8) o un `byte` matriz, similar al siguiente:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>Inspeccionar el mensaje siguiente

Puede inspeccionar el mensaje del principio de una cola sin quitarlo de la cola, mediante una llamada a la `PeekMessage` método.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>Obtener el siguiente mensaje de procesamiento

Puede recuperar el mensaje en la parte frontal de una cola para su procesamiento mediante una llamada a la `GetMessage` método.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

Más adelante indican un procesamiento correcto del mensaje utilizando `DeleteMessage`.

## <a name="change-the-contents-of-a-queued-message"></a>Cambiar el contenido de un mensaje en cola

Puede cambiar el contenido de un mensaje recuperado en lugar de en la cola. Si el mensaje representa una tarea de trabajo, puede utilizar esta característica para actualizar el estado de la tarea de trabajo. El código siguiente actualiza el mensaje de la cola con nuevo contenido y establece el tiempo de espera de visibilidad para extender otro 60 segundos. Esto guarda el estado de trabajo asociada al mensaje y le ofrece al cliente otro minuto para seguir trabajando en el mensaje. Puede usar esta técnica para realizar el seguimiento de los flujos de trabajo de varios pasos en cola de mensajes, sin tener que empezar de nuevo desde el principio si se produce un error en un paso de procesamiento debido a un error de hardware o software. Normalmente, se mantendría también un número de reintentos y si el mensaje se vuelve a intentar más de un número de veces, debería eliminarla. Esto protege contra un mensaje que desencadena un error de aplicación cada vez que se procesa.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>Eliminación de la cola el mensaje siguiente

El código anular pone en cola un mensaje de una cola en dos pasos. Cuando se llama a `GetMessage`, obtendrá el siguiente mensaje en una cola. Un mensaje devuelto de `GetMessage` se convierte en invisible para cualquier otro código que lee mensajes de esta cola. De forma predeterminada, este mensaje permanece visible durante 30 segundos. Para terminar de quitar el mensaje de la cola, también debe llamar a `DeleteMessage`. Este proceso de dos pasos de la eliminación de un mensaje garantiza que si se produce un error en el código procesar un mensaje debido a un error de hardware o software, otra instancia de su código puede obtener el mismo mensaje y vuelva a intentarlo. Las llamadas de código `DeleteMessage` justo después de que se ha procesado el mensaje.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>Usar Async flujos de trabajo con las API de almacenamiento de cola común

Este ejemplo muestra cómo usar un flujo de trabajo asincrónico con las API de almacenamiento de cola común.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>Opciones adicionales para quitando de la cola de mensajes

Hay dos maneras de personalizar la recuperación de mensajes de una cola.
En primer lugar, puede obtener un lote de mensajes (hasta 32). En segundo lugar, puede establecer un tiempo de espera de invisibilidad mayores o menores, lo que permite el código más o menos tiempo para procesar completamente cada mensaje. El siguiente ejemplo de código usa `GetMessages` para obtener 20 mensajes en uno, llame a y, a continuación, procesa cada mensaje. También establece el tiempo de espera de invisibilidad en cinco minutos para cada mensaje. Tenga en cuenta que inicia los 5 minutos para todos los mensajes al mismo tiempo, se pasa después tiene 5 minutos desde la llamada a `GetMessages`, los mensajes que no se eliminaron estará visibles de nuevo.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>Obtener la longitud de cola

Puede obtener una estimación del número de mensajes en una cola. El `FetchAttributes` método solicita el servicio de cola para recuperar los atributos de la cola, incluido el número de mensajes. El `ApproximateMessageCount` propiedad devuelve el último valor recuperado por la `FetchAttributes` método sin llamar al servicio de cola.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>Eliminar una cola

Para eliminar una cola y todos los mensajes contenidos en ella, llame a la `Delete` método en el objeto de cola.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>Pasos siguientes

Ahora que conoce los conceptos básicos de almacenamiento de la cola, siga estos vínculos para obtener información acerca de las tareas más complejas de almacenamiento.

- [API de almacenamiento de Azure para .NET](/dotnet/api/overview/azure/storage)
- [Proveedor de tipos de almacenamiento de Azure](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Blog del equipo de almacenamiento de Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Configurar cadenas de conexión de almacenamiento de Azure](/azure/storage/common/storage-configure-connection-string)
- [Referencia de API de REST de servicios de almacenamiento de Azure](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
