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
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="be2e3-104">Introducción a Azure Queue Storage mediante F\#</span><span class="sxs-lookup"><span data-stu-id="be2e3-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="be2e3-105">Azure Queue Storage proporciona mensajería en la nube entre componentes de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="be2e3-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="be2e3-106">Al diseñar aplicaciones para escala, los componentes de la aplicación suelen estar desacoplados, por lo que se pueden escalar de manera independiente.</span><span class="sxs-lookup"><span data-stu-id="be2e3-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="be2e3-107">Queue Storage ofrece mensajería asincrónica para la comunicación entre los componentes de la aplicación, tanto si se ejecutan en la nube, en el escritorio, en un servidor local o en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="be2e3-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="be2e3-108">Queue Storage también admite la administración de tareas asincrónicas y la creación de flujos de trabajo de proceso.</span><span class="sxs-lookup"><span data-stu-id="be2e3-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="be2e3-109">Acerca de este tutorial</span><span class="sxs-lookup"><span data-stu-id="be2e3-109">About this tutorial</span></span>

<span data-ttu-id="be2e3-110">En este tutorial se muestra cómo F# escribir código para algunas tareas comunes mediante el almacenamiento de colas de Azure.</span><span class="sxs-lookup"><span data-stu-id="be2e3-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="be2e3-111">Entre las tareas descritas se incluyen la creación y eliminación de colas y la adición, lectura y eliminación de mensajes de la cola.</span><span class="sxs-lookup"><span data-stu-id="be2e3-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="be2e3-112">Para obtener información general conceptual sobre Queue Storage, consulte [la guía de .net para Queue Storage](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="be2e3-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="be2e3-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="be2e3-113">Prerequisites</span></span>

<span data-ttu-id="be2e3-114">Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="be2e3-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="be2e3-115">También necesitará la clave de acceso de almacenamiento para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="be2e3-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="be2e3-116">Creación de F# un script e F# Inicio interactivo</span><span class="sxs-lookup"><span data-stu-id="be2e3-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="be2e3-117">Los ejemplos de este artículo se pueden usar en una F# aplicación o en un F# script.</span><span class="sxs-lookup"><span data-stu-id="be2e3-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="be2e3-118">Para crear un F# script, cree un archivo con la extensión `.fsx`, por ejemplo `queues.fsx`, en el F# entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="be2e3-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="be2e3-119">A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el paquete `WindowsAzure.Storage` y haga referencia a `WindowsAzure.Storage.dll` en el script mediante una directiva `#r`.</span><span class="sxs-lookup"><span data-stu-id="be2e3-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="be2e3-120">Agregar declaraciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="be2e3-120">Add namespace declarations</span></span>

<span data-ttu-id="be2e3-121">Agregue las siguientes instrucciones de `open` en la parte superior del archivo de `queues.fsx`:</span><span class="sxs-lookup"><span data-stu-id="be2e3-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="be2e3-122">Obtener la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="be2e3-122">Get your connection string</span></span>

<span data-ttu-id="be2e3-123">Necesitará una cadena de conexión Azure Storage para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="be2e3-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="be2e3-124">Para obtener más información sobre las cadenas de conexión, consulte Configuración de las [cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="be2e3-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="be2e3-125">En el tutorial, escribirá la cadena de conexión en el script, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="be2e3-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="be2e3-126">Sin embargo, esto **no se recomienda** para los proyectos reales.</span><span class="sxs-lookup"><span data-stu-id="be2e3-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="be2e3-127">La clave de la cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="be2e3-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="be2e3-128">Siempre debe proteger la clave de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="be2e3-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="be2e3-129">Evite distribuirla a otros usuarios, codificarla de forma rígida o guardarla en un archivo de texto sin formato al que puedan acceder otras personas.</span><span class="sxs-lookup"><span data-stu-id="be2e3-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="be2e3-130">Puede volver a generar la clave mediante Azure portal si cree que puede estar en peligro.</span><span class="sxs-lookup"><span data-stu-id="be2e3-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="be2e3-131">En el caso de las aplicaciones reales, la mejor manera de mantener la cadena de conexión de almacenamiento se encuentra en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="be2e3-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="be2e3-132">Para capturar la cadena de conexión de un archivo de configuración, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="be2e3-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="be2e3-133">El uso de Azure Configuration Manager es opcional.</span><span class="sxs-lookup"><span data-stu-id="be2e3-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="be2e3-134">También puede usar una API, como el tipo `ConfigurationManager` del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="be2e3-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="be2e3-135">Analizar la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="be2e3-135">Parse the connection string</span></span>

<span data-ttu-id="be2e3-136">Para analizar la cadena de conexión, use:</span><span class="sxs-lookup"><span data-stu-id="be2e3-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="be2e3-137">Esto devolverá un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="be2e3-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="be2e3-138">Creación del cliente de Queue service</span><span class="sxs-lookup"><span data-stu-id="be2e3-138">Create the Queue service client</span></span>

<span data-ttu-id="be2e3-139">La clase `CloudQueueClient` permite recuperar las colas almacenadas en Queue Storage.</span><span class="sxs-lookup"><span data-stu-id="be2e3-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="be2e3-140">Esta es una forma de crear el cliente del servicio:</span><span class="sxs-lookup"><span data-stu-id="be2e3-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="be2e3-141">Ahora está listo para escribir código que lee y escribe datos en el almacenamiento en cola.</span><span class="sxs-lookup"><span data-stu-id="be2e3-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="be2e3-142">Crear una cola</span><span class="sxs-lookup"><span data-stu-id="be2e3-142">Create a queue</span></span>

<span data-ttu-id="be2e3-143">En este ejemplo se muestra cómo crear una cola si aún no existe:</span><span class="sxs-lookup"><span data-stu-id="be2e3-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="be2e3-144">Insertar un mensaje en una cola</span><span class="sxs-lookup"><span data-stu-id="be2e3-144">Insert a message into a queue</span></span>

<span data-ttu-id="be2e3-145">Para insertar un mensaje en una cola existente, cree primero un nuevo `CloudQueueMessage`.</span><span class="sxs-lookup"><span data-stu-id="be2e3-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="be2e3-146">A continuación, llame al método `AddMessage`.</span><span class="sxs-lookup"><span data-stu-id="be2e3-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="be2e3-147">Un `CloudQueueMessage` se puede crear a partir de una cadena (en formato UTF-8) o de una matriz de `byte`, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="be2e3-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="be2e3-148">Inspeccionar el siguiente mensaje</span><span class="sxs-lookup"><span data-stu-id="be2e3-148">Peek at the next message</span></span>

<span data-ttu-id="be2e3-149">Puede inspeccionar el mensaje situado en la parte delantera de una cola, sin quitarlo de la cola, llamando al método `PeekMessage`.</span><span class="sxs-lookup"><span data-stu-id="be2e3-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="be2e3-150">Obtener el siguiente mensaje para el procesamiento</span><span class="sxs-lookup"><span data-stu-id="be2e3-150">Get the next message for processing</span></span>

<span data-ttu-id="be2e3-151">Puede recuperar el mensaje al principio de una cola para su procesamiento llamando al método `GetMessage`.</span><span class="sxs-lookup"><span data-stu-id="be2e3-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="be2e3-152">Más adelante indicará el procesamiento correcto del mensaje mediante `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="be2e3-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="be2e3-153">Cambiar el contenido de un mensaje en cola</span><span class="sxs-lookup"><span data-stu-id="be2e3-153">Change the contents of a queued message</span></span>

<span data-ttu-id="be2e3-154">Puede cambiar el contenido de un mensaje recuperado en la cola.</span><span class="sxs-lookup"><span data-stu-id="be2e3-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="be2e3-155">Si el mensaje representa una tarea de trabajo, podría usar esta característica para actualizar el estado de la tarea de trabajo.</span><span class="sxs-lookup"><span data-stu-id="be2e3-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="be2e3-156">El siguiente código actualiza el mensaje de la cola con contenido nuevo y establece el tiempo de espera de visibilidad para extender otros 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="be2e3-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="be2e3-157">Esto guarda el estado de trabajo asociado al mensaje y proporciona al cliente otro minuto para seguir trabajando en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="be2e3-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="be2e3-158">Podría usar esta técnica para realizar un seguimiento de los flujos de trabajo de varios pasos en los mensajes en cola, sin tener que empezar de nuevo desde el principio si se produce un error en un paso de procesamiento debido a un error de hardware o software.</span><span class="sxs-lookup"><span data-stu-id="be2e3-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="be2e3-159">Normalmente, también tendría que mantener un número de reintentos y, si el mensaje se vuelve a intentar más de un número de veces, lo eliminaría.</span><span class="sxs-lookup"><span data-stu-id="be2e3-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="be2e3-160">Esto protege contra un mensaje que desencadena un error de aplicación cada vez que se procesa.</span><span class="sxs-lookup"><span data-stu-id="be2e3-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="be2e3-161">Quitar de la cola el siguiente mensaje</span><span class="sxs-lookup"><span data-stu-id="be2e3-161">De-queue the next message</span></span>

<span data-ttu-id="be2e3-162">El código quita de la cola un mensaje de una cola en dos pasos.</span><span class="sxs-lookup"><span data-stu-id="be2e3-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="be2e3-163">Cuando se llama a `GetMessage`, se obtiene el siguiente mensaje en una cola.</span><span class="sxs-lookup"><span data-stu-id="be2e3-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="be2e3-164">Un mensaje devuelto de `GetMessage` se vuelve invisible a cualquier otro código que lea mensajes de esta cola.</span><span class="sxs-lookup"><span data-stu-id="be2e3-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="be2e3-165">De forma predeterminada, este mensaje permanece invisible durante 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="be2e3-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="be2e3-166">Para terminar de quitar el mensaje de la cola, también debe llamar a `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="be2e3-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="be2e3-167">Este proceso de dos pasos para quitar un mensaje garantiza que si el código no puede procesar un mensaje debido a un error de hardware o software, otra instancia del código puede obtener el mismo mensaje e intentarlo de nuevo.</span><span class="sxs-lookup"><span data-stu-id="be2e3-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="be2e3-168">El código llama `DeleteMessage` justo después de que se haya procesado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="be2e3-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="be2e3-169">Uso de flujos de trabajo asincrónicos con API comunes de almacenamiento de colas</span><span class="sxs-lookup"><span data-stu-id="be2e3-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="be2e3-170">En este ejemplo se muestra cómo usar un flujo de trabajo asincrónico con API comunes de almacenamiento de colas.</span><span class="sxs-lookup"><span data-stu-id="be2e3-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="be2e3-171">Opciones adicionales para quitar mensajes de la cola</span><span class="sxs-lookup"><span data-stu-id="be2e3-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="be2e3-172">Hay dos maneras de personalizar la recuperación de mensajes de una cola.</span><span class="sxs-lookup"><span data-stu-id="be2e3-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="be2e3-173">En primer lugar, puede obtener un lote de mensajes (hasta 32).</span><span class="sxs-lookup"><span data-stu-id="be2e3-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="be2e3-174">En segundo lugar, se puede establecer un tiempo de espera de invisibilidad más largo o más corto, lo que permite que el código tenga más o menos tiempo para procesar cada mensaje por completo.</span><span class="sxs-lookup"><span data-stu-id="be2e3-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="be2e3-175">En el ejemplo de código siguiente se usa `GetMessages` para obtener 20 mensajes en una llamada y, a continuación, procesa cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="be2e3-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="be2e3-176">También establece el tiempo de espera de la invisibilidad en cinco minutos para cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="be2e3-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="be2e3-177">Tenga en cuenta que los 5 minutos se inician para todos los mensajes al mismo tiempo, por lo que después de pasar 5 minutos desde la llamada a `GetMessages`, los mensajes que no se han eliminado volverán a estar visibles.</span><span class="sxs-lookup"><span data-stu-id="be2e3-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="be2e3-178">Obtener la longitud de la cola</span><span class="sxs-lookup"><span data-stu-id="be2e3-178">Get the queue length</span></span>

<span data-ttu-id="be2e3-179">Puede obtener una estimación del número de mensajes de una cola.</span><span class="sxs-lookup"><span data-stu-id="be2e3-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="be2e3-180">El método `FetchAttributes` pide al Queue service que recupere los atributos de la cola, incluido el recuento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="be2e3-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="be2e3-181">La propiedad `ApproximateMessageCount` devuelve el último valor recuperado por el método `FetchAttributes`, sin llamar a la Queue service.</span><span class="sxs-lookup"><span data-stu-id="be2e3-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="be2e3-182">Eliminar una cola</span><span class="sxs-lookup"><span data-stu-id="be2e3-182">Delete a queue</span></span>

<span data-ttu-id="be2e3-183">Para eliminar una cola y todos los mensajes contenidos en ella, llame al método `Delete` en el objeto Queue.</span><span class="sxs-lookup"><span data-stu-id="be2e3-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="be2e3-184">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="be2e3-184">Next steps</span></span>

<span data-ttu-id="be2e3-185">Ahora que ha aprendido los conceptos básicos de Queue Storage, siga estos vínculos para obtener más información sobre tareas de almacenamiento más complejas.</span><span class="sxs-lookup"><span data-stu-id="be2e3-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="be2e3-186">API de Azure Storage para .NET</span><span class="sxs-lookup"><span data-stu-id="be2e3-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="be2e3-187">Azure Storage proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="be2e3-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="be2e3-188">Blog del equipo de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="be2e3-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="be2e3-189">Configurar cadenas de conexión de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="be2e3-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="be2e3-190">Referencia de la API de REST de Azure Storage Services</span><span class="sxs-lookup"><span data-stu-id="be2e3-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
