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
ms.openlocfilehash: 8ec4652bab591dedc687d22c617b9466bc351f10
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2018
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="ef71a-105">Introducción al almacenamiento de cola de Azure con F #</span><span class="sxs-lookup"><span data-stu-id="ef71a-105">Get started with Azure Queue storage using F#</span></span> #

<span data-ttu-id="ef71a-106">Almacenamiento de la cola de Azure proporciona mensajería entre los componentes de la aplicación en la nube.</span><span class="sxs-lookup"><span data-stu-id="ef71a-106">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="ef71a-107">En el diseño de aplicaciones para la escala, a menudo se desvinculan componentes de la aplicación, por lo que puede escalar de forma independiente.</span><span class="sxs-lookup"><span data-stu-id="ef71a-107">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="ef71a-108">Almacenamiento de cola ofrece mensajería asincrónica para la comunicación entre componentes de aplicaciones, si se están ejecutando en la nube, en el escritorio, en un servidor local o en un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="ef71a-108">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="ef71a-109">Almacenamiento de cola también admite administrar tareas asincrónicas y generar flujos de trabajo de proceso.</span><span class="sxs-lookup"><span data-stu-id="ef71a-109">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="ef71a-110">Acerca de este tutorial</span><span class="sxs-lookup"><span data-stu-id="ef71a-110">About this tutorial</span></span>

<span data-ttu-id="ef71a-111">Este tutorial muestra cómo escribir código de F # para algunas tareas comunes mediante el almacenamiento de la cola de Azure.</span><span class="sxs-lookup"><span data-stu-id="ef71a-111">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="ef71a-112">Las tareas que se tratan incluyen creación y eliminación de colas y agregar, leer y eliminar mensajes de la cola.</span><span class="sxs-lookup"><span data-stu-id="ef71a-112">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="ef71a-113">Para obtener información conceptual de almacenamiento de cola, vea [la Guía de .NET para el almacenamiento de cola](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="ef71a-113">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ef71a-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ef71a-114">Prerequisites</span></span>

<span data-ttu-id="ef71a-115">Para utilizar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="ef71a-115">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="ef71a-116">También necesitará la clave de acceso de almacenamiento para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="ef71a-116">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="ef71a-117">Crear un Script de F # y el inicio de F # Interactive</span><span class="sxs-lookup"><span data-stu-id="ef71a-117">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="ef71a-118">Los ejemplos de este artículo pueden usarse en una aplicación de F # o un script de F #.</span><span class="sxs-lookup"><span data-stu-id="ef71a-118">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="ef71a-119">Para crear un script de F #, cree un archivo con el `.fsx` extensión, por ejemplo `queues.fsx`, en el entorno de desarrollo de F #.</span><span class="sxs-lookup"><span data-stu-id="ef71a-119">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="ef71a-120">A continuación, use un [el Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` paquete y referencia `WindowsAzure.Storage.dll` en el script mediante un `#r`directiva.</span><span class="sxs-lookup"><span data-stu-id="ef71a-120">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="ef71a-121">Agregue las declaraciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="ef71a-121">Add namespace declarations</span></span>

<span data-ttu-id="ef71a-122">Agregue el siguiente `open` instrucciones a la parte superior de la `queues.fsx` archivo:</span><span class="sxs-lookup"><span data-stu-id="ef71a-122">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="ef71a-123">Obtener la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="ef71a-123">Get your connection string</span></span>

<span data-ttu-id="ef71a-124">Necesitará una cadena de conexión de almacenamiento de Azure para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="ef71a-124">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="ef71a-125">Para obtener más información acerca de las cadenas de conexión, vea [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="ef71a-125">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="ef71a-126">Para el tutorial, especificará la cadena de conexión en el script, similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef71a-126">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="ef71a-127">Sin embargo, esto es **no recomienda** proyectos de una manera real.</span><span class="sxs-lookup"><span data-stu-id="ef71a-127">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="ef71a-128">La clave de cuenta de almacenamiento es similar a la contraseña raíz para la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ef71a-128">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="ef71a-129">Tenga siempre cuidado proteger la clave de cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ef71a-129">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="ef71a-130">Evitar la distribución a otros usuarios, codificar de forma rígida, o guardarlo en un archivo de texto sin formato sea accesible a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="ef71a-130">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="ef71a-131">Puede volver a generar la clave mediante el Portal de Azure si cree que se han comprometido.</span><span class="sxs-lookup"><span data-stu-id="ef71a-131">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="ef71a-132">Las aplicaciones de una manera real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="ef71a-132">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="ef71a-133">Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:</span><span class="sxs-lookup"><span data-stu-id="ef71a-133">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="ef71a-134">Con el Administrador de configuración de Azure es opcional.</span><span class="sxs-lookup"><span data-stu-id="ef71a-134">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="ef71a-135">También puede utilizar una API como .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="ef71a-135">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="ef71a-136">Analizar la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="ef71a-136">Parse the connection string</span></span>

<span data-ttu-id="ef71a-137">Para analizar la cadena de conexión, use:</span><span class="sxs-lookup"><span data-stu-id="ef71a-137">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="ef71a-138">Esto devolverá una `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="ef71a-138">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="ef71a-139">Crear al cliente del servicio cola</span><span class="sxs-lookup"><span data-stu-id="ef71a-139">Create the Queue service client</span></span>

<span data-ttu-id="ef71a-140">La `CloudQueueClient` clase le permite recuperar las colas almacenadas en almacenamiento de la cola.</span><span class="sxs-lookup"><span data-stu-id="ef71a-140">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="ef71a-141">Aquí es una manera de crear al cliente del servicio:</span><span class="sxs-lookup"><span data-stu-id="ef71a-141">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="ef71a-142">Ahora está listo para escribir código que lee datos de y escribe datos en el almacenamiento de cola.</span><span class="sxs-lookup"><span data-stu-id="ef71a-142">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="ef71a-143">Crear una cola</span><span class="sxs-lookup"><span data-stu-id="ef71a-143">Create a queue</span></span>

<span data-ttu-id="ef71a-144">En este ejemplo se muestra cómo crear una cola si aún no existe:</span><span class="sxs-lookup"><span data-stu-id="ef71a-144">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="ef71a-145">Insertar un mensaje en una cola</span><span class="sxs-lookup"><span data-stu-id="ef71a-145">Insert a message into a queue</span></span>

<span data-ttu-id="ef71a-146">Para insertar un mensaje en una cola existente, primero debe crear un nuevo `CloudQueueMessage`.</span><span class="sxs-lookup"><span data-stu-id="ef71a-146">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="ef71a-147">A continuación, llame a la `AddMessage` método.</span><span class="sxs-lookup"><span data-stu-id="ef71a-147">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="ef71a-148">A `CloudQueueMessage` pueden crearse desde una cadena (en formato UTF-8) o un `byte` matriz, similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="ef71a-148">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="ef71a-149">Inspeccionar el mensaje siguiente</span><span class="sxs-lookup"><span data-stu-id="ef71a-149">Peek at the next message</span></span>

<span data-ttu-id="ef71a-150">Puede inspeccionar el mensaje del principio de una cola sin quitarlo de la cola, mediante una llamada a la `PeekMessage` método.</span><span class="sxs-lookup"><span data-stu-id="ef71a-150">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="ef71a-151">Obtener el siguiente mensaje de procesamiento</span><span class="sxs-lookup"><span data-stu-id="ef71a-151">Get the next message for processing</span></span>

<span data-ttu-id="ef71a-152">Puede recuperar el mensaje en la parte frontal de una cola para su procesamiento mediante una llamada a la `GetMessage` método.</span><span class="sxs-lookup"><span data-stu-id="ef71a-152">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="ef71a-153">Más adelante indican un procesamiento correcto del mensaje utilizando `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="ef71a-153">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="ef71a-154">Cambiar el contenido de un mensaje en cola</span><span class="sxs-lookup"><span data-stu-id="ef71a-154">Change the contents of a queued message</span></span>

<span data-ttu-id="ef71a-155">Puede cambiar el contenido de un mensaje recuperado en lugar de en la cola.</span><span class="sxs-lookup"><span data-stu-id="ef71a-155">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="ef71a-156">Si el mensaje representa una tarea de trabajo, puede utilizar esta característica para actualizar el estado de la tarea de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef71a-156">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="ef71a-157">El código siguiente actualiza el mensaje de la cola con nuevo contenido y establece el tiempo de espera de visibilidad para extender otro 60 segundos.</span><span class="sxs-lookup"><span data-stu-id="ef71a-157">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="ef71a-158">Esto guarda el estado de trabajo asociada al mensaje y le ofrece al cliente otro minuto para seguir trabajando en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ef71a-158">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="ef71a-159">Puede usar esta técnica para realizar el seguimiento de los flujos de trabajo de varios pasos en cola de mensajes, sin tener que empezar de nuevo desde el principio si se produce un error en un paso de procesamiento debido a un error de hardware o software.</span><span class="sxs-lookup"><span data-stu-id="ef71a-159">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="ef71a-160">Normalmente, se mantendría también un número de reintentos y si el mensaje se vuelve a intentar más de un número de veces, debería eliminarla.</span><span class="sxs-lookup"><span data-stu-id="ef71a-160">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="ef71a-161">Esto protege contra un mensaje que desencadena un error de aplicación cada vez que se procesa.</span><span class="sxs-lookup"><span data-stu-id="ef71a-161">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="ef71a-162">Eliminación de la cola el mensaje siguiente</span><span class="sxs-lookup"><span data-stu-id="ef71a-162">De-queue the next message</span></span>

<span data-ttu-id="ef71a-163">El código anular pone en cola un mensaje de una cola en dos pasos.</span><span class="sxs-lookup"><span data-stu-id="ef71a-163">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="ef71a-164">Cuando se llama a `GetMessage`, obtendrá el siguiente mensaje en una cola.</span><span class="sxs-lookup"><span data-stu-id="ef71a-164">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="ef71a-165">Un mensaje devuelto de `GetMessage` se convierte en invisible para cualquier otro código que lee mensajes de esta cola.</span><span class="sxs-lookup"><span data-stu-id="ef71a-165">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="ef71a-166">De forma predeterminada, este mensaje permanece visible durante 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="ef71a-166">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="ef71a-167">Para terminar de quitar el mensaje de la cola, también debe llamar a `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="ef71a-167">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="ef71a-168">Este proceso de dos pasos de la eliminación de un mensaje garantiza que si se produce un error en el código procesar un mensaje debido a un error de hardware o software, otra instancia de su código puede obtener el mismo mensaje y vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="ef71a-168">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="ef71a-169">Las llamadas de código `DeleteMessage` justo después de que se ha procesado el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ef71a-169">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="ef71a-170">Usar Async flujos de trabajo con las API de almacenamiento de cola común</span><span class="sxs-lookup"><span data-stu-id="ef71a-170">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="ef71a-171">Este ejemplo muestra cómo usar un flujo de trabajo asincrónico con las API de almacenamiento de cola común.</span><span class="sxs-lookup"><span data-stu-id="ef71a-171">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="ef71a-172">Opciones adicionales para quitando de la cola de mensajes</span><span class="sxs-lookup"><span data-stu-id="ef71a-172">Additional options for de-queuing messages</span></span>

<span data-ttu-id="ef71a-173">Hay dos maneras de personalizar la recuperación de mensajes de una cola.</span><span class="sxs-lookup"><span data-stu-id="ef71a-173">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="ef71a-174">En primer lugar, puede obtener un lote de mensajes (hasta 32).</span><span class="sxs-lookup"><span data-stu-id="ef71a-174">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="ef71a-175">En segundo lugar, puede establecer un tiempo de espera de invisibilidad mayores o menores, lo que permite el código más o menos tiempo para procesar completamente cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="ef71a-175">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="ef71a-176">El siguiente ejemplo de código usa `GetMessages` para obtener 20 mensajes en uno, llame a y, a continuación, procesa cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="ef71a-176">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="ef71a-177">También establece el tiempo de espera de invisibilidad en cinco minutos para cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="ef71a-177">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="ef71a-178">Tenga en cuenta que inicia los 5 minutos para todos los mensajes al mismo tiempo, se pasa después tiene 5 minutos desde la llamada a `GetMessages`, los mensajes que no se eliminaron estará visibles de nuevo.</span><span class="sxs-lookup"><span data-stu-id="ef71a-178">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="ef71a-179">Obtener la longitud de cola</span><span class="sxs-lookup"><span data-stu-id="ef71a-179">Get the queue length</span></span>

<span data-ttu-id="ef71a-180">Puede obtener una estimación del número de mensajes en una cola.</span><span class="sxs-lookup"><span data-stu-id="ef71a-180">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="ef71a-181">El `FetchAttributes` método solicita el servicio de cola para recuperar los atributos de la cola, incluido el número de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ef71a-181">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="ef71a-182">El `ApproximateMessageCount` propiedad devuelve el último valor recuperado por la `FetchAttributes` método sin llamar al servicio de cola.</span><span class="sxs-lookup"><span data-stu-id="ef71a-182">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="ef71a-183">Eliminar una cola</span><span class="sxs-lookup"><span data-stu-id="ef71a-183">Delete a queue</span></span>

<span data-ttu-id="ef71a-184">Para eliminar una cola y todos los mensajes contenidos en ella, llame a la `Delete` método en el objeto de cola.</span><span class="sxs-lookup"><span data-stu-id="ef71a-184">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="ef71a-185">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ef71a-185">Next steps</span></span>

<span data-ttu-id="ef71a-186">Ahora que conoce los conceptos básicos de almacenamiento de la cola, siga estos vínculos para obtener información acerca de las tareas más complejas de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ef71a-186">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="ef71a-187">API de almacenamiento de Azure para .NET</span><span class="sxs-lookup"><span data-stu-id="ef71a-187">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="ef71a-188">Proveedor de tipos de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="ef71a-188">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="ef71a-189">Blog del equipo de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="ef71a-189">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
- [<span data-ttu-id="ef71a-190">Configurar cadenas de conexión de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="ef71a-190">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="ef71a-191">Referencia de API de REST de servicios de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="ef71a-191">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
