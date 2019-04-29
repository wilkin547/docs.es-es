---
title: Introducción a Azure Queue storage medianteF#
description: Las colas de Azure proporcionan mensajería confiable y asincrónica entre los componentes de la aplicación. En la nube permite mensajería los componentes de aplicación para escalar de forma independiente.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 58a46dfe905a32be77a13d11df8f0544546ea0ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756382"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="dee01-104">Introducción a Azure Queue storage mediante F\#</span><span class="sxs-lookup"><span data-stu-id="dee01-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="dee01-105">Azure Queue storage proporciona mensajería entre componentes de la aplicación en la nube.</span><span class="sxs-lookup"><span data-stu-id="dee01-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="dee01-106">En el diseño de aplicaciones para escala, los componentes de aplicación suelen desacoplarse para que puedan escalarse de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="dee01-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="dee01-107">Almacenamiento en cola ofrece mensajería asincrónica para la comunicación entre componentes de la aplicación, independientemente de si se ejecutan en la nube, en el escritorio, en un servidor local o en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="dee01-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="dee01-108">Almacenamiento de colas también admite la administración de tareas asincrónicas y creación de flujos de trabajo de proceso.</span><span class="sxs-lookup"><span data-stu-id="dee01-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="dee01-109">Acerca de este tutorial</span><span class="sxs-lookup"><span data-stu-id="dee01-109">About this tutorial</span></span>

<span data-ttu-id="dee01-110">Este tutorial muestra cómo escribir F# código para algunas tareas comunes de usar Azure Queue storage.</span><span class="sxs-lookup"><span data-stu-id="dee01-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="dee01-111">Tareas descritas incluyen crear y eliminar colas y agregar, leer y eliminar mensajes de la cola.</span><span class="sxs-lookup"><span data-stu-id="dee01-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="dee01-112">Información general conceptual de queue storage, consulte [la Guía de .NET para queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="dee01-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dee01-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="dee01-113">Prerequisites</span></span>

<span data-ttu-id="dee01-114">Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="dee01-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="dee01-115">También necesitará la clave de acceso de almacenamiento para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="dee01-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="dee01-116">Crear un F# Script e iniciar F# interactivo</span><span class="sxs-lookup"><span data-stu-id="dee01-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="dee01-117">Los ejemplos de este artículo pueden usarse en cualquiera un F# aplicación o un F# secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="dee01-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="dee01-118">Para crear un F# de script, cree un archivo con el `.fsx` extensión, por ejemplo `queues.fsx`, en su F# entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="dee01-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="dee01-119">A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` paquete y referencia `WindowsAzure.Storage.dll` en el script mediante un `#r`directiva.</span><span class="sxs-lookup"><span data-stu-id="dee01-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="dee01-120">Agregue las declaraciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="dee01-120">Add namespace declarations</span></span>

<span data-ttu-id="dee01-121">Agregue el siguiente `open` instrucciones a la parte superior de la `queues.fsx` archivo:</span><span class="sxs-lookup"><span data-stu-id="dee01-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="dee01-122">Obtener la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="dee01-122">Get your connection string</span></span>

<span data-ttu-id="dee01-123">Necesitará una cadena de conexión de Azure Storage para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="dee01-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="dee01-124">Para obtener más información acerca de las cadenas de conexión, consulte [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="dee01-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="dee01-125">Para este tutorial, deberá escribir la cadena de conexión en el script, similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="dee01-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="dee01-126">Sin embargo, esto es **no recomienda** proyectos reales.</span><span class="sxs-lookup"><span data-stu-id="dee01-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="dee01-127">La clave de cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="dee01-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="dee01-128">Siempre debe proteger la clave de cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="dee01-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="dee01-129">Evite distribuirla a otros usuarios, codificarla de forma o guardarlo en un archivo de texto sin formato que sea accesible a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="dee01-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="dee01-130">Puede volver a generar la clave mediante Azure Portal si cree que puede verse comprometida.</span><span class="sxs-lookup"><span data-stu-id="dee01-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="dee01-131">Las aplicaciones para el real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="dee01-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="dee01-132">Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:</span><span class="sxs-lookup"><span data-stu-id="dee01-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="dee01-133">Con el Administrador de configuración de Azure es opcional.</span><span class="sxs-lookup"><span data-stu-id="dee01-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="dee01-134">También puede usar una API como .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="dee01-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="dee01-135">Analizar la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="dee01-135">Parse the connection string</span></span>

<span data-ttu-id="dee01-136">Para analizar la cadena de conexión, use:</span><span class="sxs-lookup"><span data-stu-id="dee01-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="dee01-137">Esto devolverá un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="dee01-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="dee01-138">Crear al cliente del servicio cola</span><span class="sxs-lookup"><span data-stu-id="dee01-138">Create the Queue service client</span></span>

<span data-ttu-id="dee01-139">La `CloudQueueClient` clase le permite recuperar las colas almacenadas en almacenamiento de la cola.</span><span class="sxs-lookup"><span data-stu-id="dee01-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="dee01-140">Aquí es una forma de crear al cliente del servicio:</span><span class="sxs-lookup"><span data-stu-id="dee01-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="dee01-141">Ahora está listo para escribir código que lee y escribe datos en almacenamiento de la cola.</span><span class="sxs-lookup"><span data-stu-id="dee01-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="dee01-142">Crear una cola</span><span class="sxs-lookup"><span data-stu-id="dee01-142">Create a queue</span></span>

<span data-ttu-id="dee01-143">En este ejemplo se muestra cómo crear una cola si aún no existe:</span><span class="sxs-lookup"><span data-stu-id="dee01-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="dee01-144">Insertar un mensaje en una cola</span><span class="sxs-lookup"><span data-stu-id="dee01-144">Insert a message into a queue</span></span>

<span data-ttu-id="dee01-145">Para insertar un mensaje en una cola existente, primero debe crear un nuevo `CloudQueueMessage`.</span><span class="sxs-lookup"><span data-stu-id="dee01-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="dee01-146">A continuación, llame a la `AddMessage` método.</span><span class="sxs-lookup"><span data-stu-id="dee01-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="dee01-147">Un `CloudQueueMessage` pueden crearse desde una cadena (en formato UTF-8) o un `byte` matriz, similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="dee01-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="dee01-148">Inspeccionar el mensaje siguiente</span><span class="sxs-lookup"><span data-stu-id="dee01-148">Peek at the next message</span></span>

<span data-ttu-id="dee01-149">Puede inspeccionar el mensaje de la parte delantera de una cola, sin quitarlo de la cola, mediante una llamada a la `PeekMessage` método.</span><span class="sxs-lookup"><span data-stu-id="dee01-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="dee01-150">Obtiene el siguiente mensaje de procesamiento</span><span class="sxs-lookup"><span data-stu-id="dee01-150">Get the next message for processing</span></span>

<span data-ttu-id="dee01-151">Puede recuperar el mensaje en la parte delantera de una cola para su procesamiento mediante una llamada a la `GetMessage` método.</span><span class="sxs-lookup"><span data-stu-id="dee01-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="dee01-152">Procesamiento correcto del mensaje se indica más adelante mediante el uso de `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="dee01-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="dee01-153">Cambiar el contenido de un mensaje en cola</span><span class="sxs-lookup"><span data-stu-id="dee01-153">Change the contents of a queued message</span></span>

<span data-ttu-id="dee01-154">Puede cambiar el contenido de un mensaje recuperado en lugar de en la cola.</span><span class="sxs-lookup"><span data-stu-id="dee01-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="dee01-155">Si el mensaje representa una tarea de trabajo, puede utilizar esta característica para actualizar el estado de la tarea de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dee01-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="dee01-156">El siguiente código actualiza el mensaje de cola con contenido nuevo y establece el tiempo de espera de visibilidad en 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="dee01-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="dee01-157">Esto guarda el estado del trabajo asociado con el mensaje y da al cliente minuto más para que siga elaborando el mensaje.</span><span class="sxs-lookup"><span data-stu-id="dee01-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="dee01-158">Puede usar esta técnica para realizar el seguimiento de los flujos de trabajo de varios pasos en los mensajes de cola, sin tener que empezar de nuevo desde el principio si se produce un error en un paso de procesamiento debido a un error de hardware o software.</span><span class="sxs-lookup"><span data-stu-id="dee01-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="dee01-159">Normalmente, también mantendría un número de reintentos y si el mensaje se intentara más de cierto número de veces, lo eliminaría.</span><span class="sxs-lookup"><span data-stu-id="dee01-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="dee01-160">Esto protege contra un mensaje que desencadena un error de aplicación cada vez que se procese.</span><span class="sxs-lookup"><span data-stu-id="dee01-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="dee01-161">El siguiente mensaje de la cola</span><span class="sxs-lookup"><span data-stu-id="dee01-161">De-queue the next message</span></span>

<span data-ttu-id="dee01-162">Quita el código de la cola un mensaje de una cola en dos pasos.</span><span class="sxs-lookup"><span data-stu-id="dee01-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="dee01-163">Cuando se llama a `GetMessage`, obtendrá el siguiente mensaje en una cola.</span><span class="sxs-lookup"><span data-stu-id="dee01-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="dee01-164">Un mensaje devuelto por `GetMessage` se hace invisible a cualquier otro código de lectura de mensajes de esta cola.</span><span class="sxs-lookup"><span data-stu-id="dee01-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="dee01-165">De forma predeterminada, este mensaje permanece invisible durante 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="dee01-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="dee01-166">Para terminar de quitar el mensaje de la cola, también se debe llamar `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="dee01-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="dee01-167">Este proceso en dos pasos de la eliminación de un mensaje garantiza que si se produce un error en el código procesar un mensaje debido a un error de hardware o software, otra instancia de su código puede obtener el mismo mensaje y vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="dee01-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="dee01-168">El código llama a `DeleteMessage` justo después de haber procesado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="dee01-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="dee01-169">Usar flujos de trabajo asincrónicos con API comunes de almacenamiento de cola</span><span class="sxs-lookup"><span data-stu-id="dee01-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="dee01-170">En este ejemplo se muestra cómo usar un flujo de trabajo asincrónico con API comunes de almacenamiento de cola.</span><span class="sxs-lookup"><span data-stu-id="dee01-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="dee01-171">Opciones adicionales para quitando de la cola de mensajes</span><span class="sxs-lookup"><span data-stu-id="dee01-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="dee01-172">Hay dos formas de personalizar la recuperación de mensajes de una cola.</span><span class="sxs-lookup"><span data-stu-id="dee01-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="dee01-173">En primer lugar, puede obtener un lote de mensajes (hasta 32).</span><span class="sxs-lookup"><span data-stu-id="dee01-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="dee01-174">En segundo lugar, puede establecer un tiempo de espera de invisibilidad más largo o más corto que el código más o menos tiempo para procesar cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="dee01-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="dee01-175">El siguiente ejemplo de código usa `GetMessages` para obtener 20 mensajes en uno, llame a y, a continuación, procesa cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="dee01-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="dee01-176">También se establece el tiempo de espera de invisibilidad en cinco minutos para cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="dee01-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="dee01-177">Tenga en cuenta que los 5 minutos se inicia para todos los mensajes al mismo tiempo, tras 5 minutos ha transcurrido desde la llamada a `GetMessages`, todos los mensajes que no se han eliminado volverán a visibles.</span><span class="sxs-lookup"><span data-stu-id="dee01-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="dee01-178">Obtener la longitud de cola</span><span class="sxs-lookup"><span data-stu-id="dee01-178">Get the queue length</span></span>

<span data-ttu-id="dee01-179">Puede obtener una estimación del número de mensajes en una cola.</span><span class="sxs-lookup"><span data-stu-id="dee01-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="dee01-180">El `FetchAttributes` método solicita a Queue service para recuperar los atributos de la cola, incluido el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="dee01-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="dee01-181">El `ApproximateMessageCount` propiedad devuelve el último valor recuperado por el `FetchAttributes` método sin llamar a Queue service.</span><span class="sxs-lookup"><span data-stu-id="dee01-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="dee01-182">Eliminar una cola</span><span class="sxs-lookup"><span data-stu-id="dee01-182">Delete a queue</span></span>

<span data-ttu-id="dee01-183">Para eliminar una cola y todos los mensajes contenidos en ella, llame a la `Delete` método en el objeto de cola.</span><span class="sxs-lookup"><span data-stu-id="dee01-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="dee01-184">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="dee01-184">Next steps</span></span>

<span data-ttu-id="dee01-185">Ahora que ha aprendido los conceptos básicos de Queue storage, siga estos vínculos para obtener información sobre tareas de almacenamiento más complejas.</span><span class="sxs-lookup"><span data-stu-id="dee01-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="dee01-186">API de Azure Storage para .NET</span><span class="sxs-lookup"><span data-stu-id="dee01-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="dee01-187">Proveedor de tipos de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="dee01-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="dee01-188">Blog del equipo de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="dee01-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="dee01-189">Configurar cadenas de conexión de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="dee01-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="dee01-190">Referencia de API de REST de servicios de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="dee01-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
