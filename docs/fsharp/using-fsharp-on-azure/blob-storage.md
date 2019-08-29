---
title: Introducción a Azure Blob Storage mediante F#
description: Almacene datos no estructurados en la nube con Azure BLOB Storage.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: c765f38cba7642e813a5966d3b7754c5ce45abbd
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107119"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="d013b-103">Introducción a Azure BLOB Storage mediante F\#</span><span class="sxs-lookup"><span data-stu-id="d013b-103">Get started with Azure Blob storage using F\#</span></span>

<span data-ttu-id="d013b-104">Azure Blob Storage es un servicio que almacena datos no estructurados en la nube como objetos o blobs.</span><span class="sxs-lookup"><span data-stu-id="d013b-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="d013b-105">El almacenamiento de blobs puede almacenar cualquier tipo de texto o datos binarios, como un documento, un archivo multimedia o un instalador de aplicación.</span><span class="sxs-lookup"><span data-stu-id="d013b-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="d013b-106">El Almacenamiento de blobs también se conoce como "almacenamiento de objetos".</span><span class="sxs-lookup"><span data-stu-id="d013b-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="d013b-107">En este artículo se muestra cómo realizar tareas comunes con el almacenamiento de blobs.</span><span class="sxs-lookup"><span data-stu-id="d013b-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="d013b-108">Los ejemplos se escriben F# mediante el uso de la biblioteca de cliente de Azure Storage para .net.</span><span class="sxs-lookup"><span data-stu-id="d013b-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="d013b-109">Entre las tareas descritas se incluyen cómo cargar, enumerar, descargar y eliminar BLOBs.</span><span class="sxs-lookup"><span data-stu-id="d013b-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="d013b-110">Para obtener información general conceptual sobre el almacenamiento de blobs, consulte [la guía de .net para BLOB Storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span><span class="sxs-lookup"><span data-stu-id="d013b-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d013b-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="d013b-111">Prerequisites</span></span>

<span data-ttu-id="d013b-112">Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="d013b-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="d013b-113">También necesitará la clave de acceso de almacenamiento para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="d013b-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="d013b-114">Creación de F# un script e F# Inicio interactivo</span><span class="sxs-lookup"><span data-stu-id="d013b-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="d013b-115">Los ejemplos de este artículo se pueden usar en una F# aplicación o en un F# script.</span><span class="sxs-lookup"><span data-stu-id="d013b-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="d013b-116">Para crear un F# script, cree un archivo con la `.fsx` extensión, por ejemplo `blobs.fsx`, en el F# entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="d013b-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="d013b-117">A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar `WindowsAzure.Storage` los `Microsoft.WindowsAzure.ConfigurationManager` paquetes y y `WindowsAzure.Storage.dll` la `Microsoft.WindowsAzure.Configuration.dll` referencia y en el script `#r` mediante una directiva.</span><span class="sxs-lookup"><span data-stu-id="d013b-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="d013b-118">Agregar declaraciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d013b-118">Add namespace declarations</span></span>

<span data-ttu-id="d013b-119">Agregue las siguientes `open` instrucciones a la parte superior `blobs.fsx` del archivo:</span><span class="sxs-lookup"><span data-stu-id="d013b-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="d013b-120">Obtener la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="d013b-120">Get your connection string</span></span>

<span data-ttu-id="d013b-121">Necesita una cadena de conexión Azure Storage para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="d013b-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="d013b-122">Para obtener más información sobre las cadenas de conexión, consulte Configuración de las [cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="d013b-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="d013b-123">En el tutorial, escriba la cadena de conexión en el script, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="d013b-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="d013b-124">Sin embargo, esto **no se recomienda** para los proyectos reales.</span><span class="sxs-lookup"><span data-stu-id="d013b-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="d013b-125">La clave de la cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d013b-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="d013b-126">Siempre debe proteger la clave de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d013b-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="d013b-127">Evite distribuirla a otros usuarios, codificarla de forma rígida o guardarla en un archivo de texto sin formato al que puedan acceder otras personas.</span><span class="sxs-lookup"><span data-stu-id="d013b-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="d013b-128">Puede volver a generar la clave mediante Azure portal si cree que puede estar en peligro.</span><span class="sxs-lookup"><span data-stu-id="d013b-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="d013b-129">En el caso de las aplicaciones reales, la mejor manera de mantener la cadena de conexión de almacenamiento se encuentra en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d013b-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="d013b-130">Para capturar la cadena de conexión de un archivo de configuración, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d013b-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="d013b-131">El uso de Azure Configuration Manager es opcional.</span><span class="sxs-lookup"><span data-stu-id="d013b-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="d013b-132">También puede usar una API, como el tipo de `ConfigurationManager` .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d013b-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="d013b-133">Analizar la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="d013b-133">Parse the connection string</span></span>

<span data-ttu-id="d013b-134">Para analizar la cadena de conexión, use:</span><span class="sxs-lookup"><span data-stu-id="d013b-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="d013b-135">Esto devuelve un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="d013b-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="d013b-136">Crear algunos datos ficticios locales</span><span class="sxs-lookup"><span data-stu-id="d013b-136">Create some local dummy data</span></span>

<span data-ttu-id="d013b-137">Antes de empezar, cree algunos datos locales ficticios en el directorio del script.</span><span class="sxs-lookup"><span data-stu-id="d013b-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="d013b-138">Más adelante se cargan estos datos.</span><span class="sxs-lookup"><span data-stu-id="d013b-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="d013b-139">Creación del cliente de Blob service</span><span class="sxs-lookup"><span data-stu-id="d013b-139">Create the Blob service client</span></span>

<span data-ttu-id="d013b-140">El `CloudBlobClient` tipo permite recuperar contenedores y blobs almacenados en el almacenamiento de blobs.</span><span class="sxs-lookup"><span data-stu-id="d013b-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="d013b-141">Esta es una forma de crear el cliente del servicio:</span><span class="sxs-lookup"><span data-stu-id="d013b-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="d013b-142">Ahora está listo para escribir código que lee datos de y escribe datos en el almacenamiento de blobs.</span><span class="sxs-lookup"><span data-stu-id="d013b-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="d013b-143">Crear un contenedor</span><span class="sxs-lookup"><span data-stu-id="d013b-143">Create a container</span></span>

<span data-ttu-id="d013b-144">En este ejemplo se muestra cómo crear un contenedor si aún no existe:</span><span class="sxs-lookup"><span data-stu-id="d013b-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="d013b-145">De forma predeterminada, el nuevo contenedor es privado, lo que significa que debe especificar la clave de acceso de almacenamiento para descargar los blobs de este contenedor.</span><span class="sxs-lookup"><span data-stu-id="d013b-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="d013b-146">Si desea que los archivos del contenedor estén disponibles para todos, puede establecer el contenedor para que sea público mediante el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="d013b-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="d013b-147">Cualquier usuario de Internet puede ver los blobs de un contenedor público, pero solo puede modificarlos o eliminarlos si dispone de la clave de acceso de la cuenta adecuada o de una firma de acceso compartido.</span><span class="sxs-lookup"><span data-stu-id="d013b-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="d013b-148">Carga de un BLOB en un contenedor</span><span class="sxs-lookup"><span data-stu-id="d013b-148">Upload a blob into a container</span></span>

<span data-ttu-id="d013b-149">Azure Blob Storage admite blobs en bloques y blobs en páginas.</span><span class="sxs-lookup"><span data-stu-id="d013b-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="d013b-150">En la mayoría de los casos, un BLOB en bloques es el tipo recomendado que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="d013b-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="d013b-151">Para cargar un archivo en un BLOB en bloques, obtenga una referencia de contenedor y Úsela para obtener una referencia de BLOB en bloques.</span><span class="sxs-lookup"><span data-stu-id="d013b-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="d013b-152">Una vez que tenga una referencia de BLOB, puede cargar cualquier secuencia de datos en ella llamando al `UploadFromFile` método.</span><span class="sxs-lookup"><span data-stu-id="d013b-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="d013b-153">Esta operación crea el BLOB si no existía anteriormente, o lo sobrescribe si existe.</span><span class="sxs-lookup"><span data-stu-id="d013b-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="d013b-154">Enumeración de los blobs de un contenedor</span><span class="sxs-lookup"><span data-stu-id="d013b-154">List the blobs in a container</span></span>

<span data-ttu-id="d013b-155">Para enumerar los blobs de un contenedor, primero obtenga una referencia de contenedor.</span><span class="sxs-lookup"><span data-stu-id="d013b-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="d013b-156">Después, puede usar el método del `ListBlobs` contenedor para recuperar los blobs o directorios que contiene.</span><span class="sxs-lookup"><span data-stu-id="d013b-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="d013b-157">Para tener acceso al conjunto completo de propiedades y métodos de un `IListBlobItem`devuelto, debe convertirlo en `CloudBlockBlob`un `CloudPageBlob`objeto, `CloudBlobDirectory` o.</span><span class="sxs-lookup"><span data-stu-id="d013b-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="d013b-158">Si el tipo es desconocido, puede usar una comprobación de tipo para determinar a qué se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="d013b-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="d013b-159">En el código siguiente se muestra cómo recuperar y generar el URI de cada elemento del `mydata` contenedor:</span><span class="sxs-lookup"><span data-stu-id="d013b-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="d013b-160">También puede asignar nombres a los blobs con la información de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="d013b-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="d013b-161">Esto crea una estructura de directorios virtuales que puede organizar y recorrer como lo haría con un sistema de archivos tradicional.</span><span class="sxs-lookup"><span data-stu-id="d013b-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="d013b-162">Tenga en cuenta que la estructura de directorios es solo virtual: los únicos recursos disponibles en BLOB Storage son contenedores y BLOBs.</span><span class="sxs-lookup"><span data-stu-id="d013b-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="d013b-163">Sin embargo, la biblioteca de cliente de `CloudBlobDirectory` almacenamiento ofrece un objeto para hacer referencia a un directorio virtual y simplificar el proceso de trabajar con blobs organizados de este modo.</span><span class="sxs-lookup"><span data-stu-id="d013b-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="d013b-164">Por ejemplo, considere el siguiente conjunto de blobs en bloques en un `photos`contenedor denominado:</span><span class="sxs-lookup"><span data-stu-id="d013b-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="d013b-165">*photo1.jpg*</span><span class="sxs-lookup"><span data-stu-id="d013b-165">*photo1.jpg*</span></span>\
<span data-ttu-id="d013b-166">*2015/architecture/description.txt*</span><span class="sxs-lookup"><span data-stu-id="d013b-166">*2015/architecture/description.txt*</span></span>\
<span data-ttu-id="d013b-167">*2015/Architecture/photo3. jpg*</span><span class="sxs-lookup"><span data-stu-id="d013b-167">*2015/architecture/photo3.jpg*</span></span>\
<span data-ttu-id="d013b-168">*2015/Architecture/photo4. jpg*</span><span class="sxs-lookup"><span data-stu-id="d013b-168">*2015/architecture/photo4.jpg*</span></span>\
<span data-ttu-id="d013b-169">*2016/architecture/photo5.jpg*</span><span class="sxs-lookup"><span data-stu-id="d013b-169">*2016/architecture/photo5.jpg*</span></span>\
<span data-ttu-id="d013b-170">*2016/architecture/photo6.jpg*</span><span class="sxs-lookup"><span data-stu-id="d013b-170">*2016/architecture/photo6.jpg*</span></span>\
<span data-ttu-id="d013b-171">*2016/architecture/description.txt*</span><span class="sxs-lookup"><span data-stu-id="d013b-171">*2016/architecture/description.txt*</span></span>\
<span data-ttu-id="d013b-172">*2016/photo7.jpg*</span><span class="sxs-lookup"><span data-stu-id="d013b-172">*2016/photo7.jpg*</span></span>\

<span data-ttu-id="d013b-173">Cuando se llama `ListBlobs` a en un contenedor (como en el ejemplo anterior), se devuelve una lista jerárquica.</span><span class="sxs-lookup"><span data-stu-id="d013b-173">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="d013b-174">Si contiene `CloudBlobDirectory` objetos y `CloudBlockBlob` , que representan los directorios y los blobs del contenedor, respectivamente, la salida resultante tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="d013b-174">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="d013b-175">Opcionalmente, puede establecer el `UseFlatBlobListing` parámetro `ListBlobs` del método en `true`.</span><span class="sxs-lookup"><span data-stu-id="d013b-175">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="d013b-176">En este caso, cada BLOB del contenedor se devuelve como un `CloudBlockBlob` objeto.</span><span class="sxs-lookup"><span data-stu-id="d013b-176">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="d013b-177">La llamada a `ListBlobs` para devolver una lista plana tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="d013b-177">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="d013b-178">y, en función del contenido actual del contenedor, los resultados son similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d013b-178">and, depending on the current contents of your container, the results look like this:</span></span>

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a><span data-ttu-id="d013b-179">Descargar blobs</span><span class="sxs-lookup"><span data-stu-id="d013b-179">Download blobs</span></span>

<span data-ttu-id="d013b-180">Para descargar blobs, primero recupere una referencia de BLOB y `DownloadToStream` , a continuación, llame al método.</span><span class="sxs-lookup"><span data-stu-id="d013b-180">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="d013b-181">En el ejemplo siguiente se `DownloadToStream` usa el método para transferir el contenido del BLOB a un objeto de secuencia que se puede guardar en un archivo local.</span><span class="sxs-lookup"><span data-stu-id="d013b-181">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="d013b-182">También puede usar el `DownloadToStream` método para descargar el contenido de un BLOB como una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="d013b-182">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="d013b-183">Eliminar blobs</span><span class="sxs-lookup"><span data-stu-id="d013b-183">Delete blobs</span></span>

<span data-ttu-id="d013b-184">Para eliminar un BLOB, primero obtenga una referencia de BLOB y, a `Delete` continuación, llame al método en ella.</span><span class="sxs-lookup"><span data-stu-id="d013b-184">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="d013b-185">Enumerar blobs en páginas de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="d013b-185">List blobs in pages asynchronously</span></span>

<span data-ttu-id="d013b-186">Si está enumerando un gran número de blobs o desea controlar el número de resultados que se devuelven en una operación de lista, puede enumerar los blobs en páginas de resultados.</span><span class="sxs-lookup"><span data-stu-id="d013b-186">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="d013b-187">En este ejemplo se muestra cómo devolver los resultados en páginas de forma asincrónica, de modo que la ejecución no se bloquee mientras se espera a devolver un conjunto grande de resultados.</span><span class="sxs-lookup"><span data-stu-id="d013b-187">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="d013b-188">En este ejemplo se muestra una lista plana `useFlatBlobListing` `ListBlobsSegmentedAsync` de blobs, pero también puede realizar una lista jerárquica estableciendo el parámetro del método en `false`.</span><span class="sxs-lookup"><span data-stu-id="d013b-188">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="d013b-189">En el ejemplo se define un método asincrónico, mediante `async` un bloque.</span><span class="sxs-lookup"><span data-stu-id="d013b-189">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="d013b-190">La ``let!`` palabra clave suspende la ejecución del método de ejemplo hasta que se completa la tarea de lista.</span><span class="sxs-lookup"><span data-stu-id="d013b-190">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="d013b-191">Ahora podemos usar esta rutina asincrónica como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="d013b-191">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="d013b-192">En primer lugar, cargue algunos datos ficticios (mediante el archivo local creado anteriormente en este tutorial).</span><span class="sxs-lookup"><span data-stu-id="d013b-192">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="d013b-193">Ahora, llame a la rutina.</span><span class="sxs-lookup"><span data-stu-id="d013b-193">Now, call the routine.</span></span> <span data-ttu-id="d013b-194">Se usa `Async.RunSynchronously` para forzar la ejecución de la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="d013b-194">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="d013b-195">Escribir en un BLOB en anexos</span><span class="sxs-lookup"><span data-stu-id="d013b-195">Writing to an append blob</span></span>

<span data-ttu-id="d013b-196">Un BLOB en anexos está optimizado para operaciones de anexión, como el registro.</span><span class="sxs-lookup"><span data-stu-id="d013b-196">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="d013b-197">Al igual que un BLOB en bloques, un BLOB en anexos se compone de bloques, pero al agregar un nuevo bloque a un BLOB en anexos, siempre se anexa al final del BLOB.</span><span class="sxs-lookup"><span data-stu-id="d013b-197">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="d013b-198">No se puede actualizar o eliminar un bloque existente en un BLOB en anexos.</span><span class="sxs-lookup"><span data-stu-id="d013b-198">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="d013b-199">Los identificadores de bloque de un BLOB en anexos no se exponen como son para un BLOB en bloques.</span><span class="sxs-lookup"><span data-stu-id="d013b-199">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="d013b-200">Cada bloque de un BLOB en anexos puede tener un tamaño diferente, hasta un máximo de 4 MB, y un BLOB en anexos puede incluir un máximo de 50.000 bloques.</span><span class="sxs-lookup"><span data-stu-id="d013b-200">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="d013b-201">Por lo tanto, el tamaño máximo de un BLOB en anexos es ligeramente superior a 195 GB (bloques de 4 MB X 50.000).</span><span class="sxs-lookup"><span data-stu-id="d013b-201">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="d013b-202">En el ejemplo siguiente se crea un nuevo BLOB en anexos y se anexan algunos datos, simulando una operación de registro simple.</span><span class="sxs-lookup"><span data-stu-id="d013b-202">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="d013b-203">Vea Descripción de los blobs en [bloques, los blobs en páginas y](https://msdn.microsoft.com/library/azure/ee691964.aspx) los blobs en anexos para obtener más información sobre las diferencias entre los tres tipos de blobs.</span><span class="sxs-lookup"><span data-stu-id="d013b-203">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="d013b-204">Acceso simultáneo</span><span class="sxs-lookup"><span data-stu-id="d013b-204">Concurrent access</span></span>

<span data-ttu-id="d013b-205">Para admitir el acceso simultáneo a un BLOB desde varios clientes o varias instancias de proceso, puede usar **etags** o **concesiones**.</span><span class="sxs-lookup"><span data-stu-id="d013b-205">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

- <span data-ttu-id="d013b-206">**ETag** : proporciona una manera de detectar que otro proceso ha modificado el BLOB o el contenedor.</span><span class="sxs-lookup"><span data-stu-id="d013b-206">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

- <span data-ttu-id="d013b-207">**Concesión** : proporciona una manera de obtener acceso exclusivo, renovable, de escritura o eliminación a un BLOB durante un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="d013b-207">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="d013b-208">Para obtener más información, vea [administrar la simultaneidad en Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span><span class="sxs-lookup"><span data-stu-id="d013b-208">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="d013b-209">Nomenclatura de contenedores</span><span class="sxs-lookup"><span data-stu-id="d013b-209">Naming containers</span></span>

<span data-ttu-id="d013b-210">Cada BLOB de Azure Storage debe residir en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="d013b-210">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="d013b-211">El contenedor forma parte del nombre del BLOB.</span><span class="sxs-lookup"><span data-stu-id="d013b-211">The container forms part of the blob name.</span></span> <span data-ttu-id="d013b-212">Por ejemplo, `mydata` es el nombre del contenedor en estos URI de BLOB de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d013b-212">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

- https://storagesample.blob.core.windows.net/mydata/blob1.txt
- https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="d013b-213">Un nombre de contenedor debe ser un nombre DNS válido, conforme a las siguientes reglas de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="d013b-213">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="d013b-214">Los nombres de contenedor deben comenzar por una letra o un número y solo pueden contener letras, números y el carácter de guion (-).</span><span class="sxs-lookup"><span data-stu-id="d013b-214">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="d013b-215">Cada carácter de guion (-) debe ir precedido y seguido inmediatamente de una letra o un número; los guiones consecutivos no se permiten en los nombres de contenedor.</span><span class="sxs-lookup"><span data-stu-id="d013b-215">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="d013b-216">Todas las letras de un nombre de contenedor deben estar en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d013b-216">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="d013b-217">Los nombres de contenedor deben tener entre 3 y 63 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="d013b-217">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="d013b-218">Tenga en cuenta que el nombre de un contenedor siempre debe estar en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="d013b-218">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="d013b-219">Si incluye una letra mayúscula en un nombre de contenedor o infringe las reglas de nomenclatura de contenedores, es posible que reciba un error 400 (solicitud incorrecta).</span><span class="sxs-lookup"><span data-stu-id="d013b-219">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="d013b-220">Administrar la seguridad de los blobs</span><span class="sxs-lookup"><span data-stu-id="d013b-220">Managing security for blobs</span></span>

<span data-ttu-id="d013b-221">De forma predeterminada, Azure Storage protege los datos al limitar el acceso al propietario de la cuenta, quien está en posesión de las claves de acceso de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="d013b-221">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="d013b-222">Cuando necesite compartir datos de blobs en su cuenta de almacenamiento, es importante hacerlo sin poner en peligro la seguridad de las claves de acceso de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="d013b-222">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="d013b-223">Además, puede cifrar los datos de BLOB para asegurarse de que es seguro pasar por la conexión y Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="d013b-223">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="d013b-224">Controlar el acceso a los datos de BLOB</span><span class="sxs-lookup"><span data-stu-id="d013b-224">Controlling access to blob data</span></span>

<span data-ttu-id="d013b-225">De forma predeterminada, solo el propietario de la cuenta de almacenamiento puede acceder a los datos de BLOB de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="d013b-225">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="d013b-226">La autenticación de solicitudes en BLOB Storage requiere la clave de acceso de la cuenta de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d013b-226">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="d013b-227">Sin embargo, es posible que desee poner determinados datos de BLOB a disposición de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="d013b-227">However, you might want to make certain blob data available to other users.</span></span>

### <a name="encrypting-blob-data"></a><span data-ttu-id="d013b-228">Cifrado de datos de blobs</span><span class="sxs-lookup"><span data-stu-id="d013b-228">Encrypting blob data</span></span>

<span data-ttu-id="d013b-229">Azure Storage admite el cifrado de datos de BLOB tanto en el cliente como en el servidor.</span><span class="sxs-lookup"><span data-stu-id="d013b-229">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d013b-230">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="d013b-230">Next steps</span></span>

<span data-ttu-id="d013b-231">Ahora que ha aprendido los aspectos básicos del almacenamiento de blobs, siga estos vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d013b-231">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="d013b-232">Herramientas</span><span class="sxs-lookup"><span data-stu-id="d013b-232">Tools</span></span>

- <span data-ttu-id="d013b-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)</span><span class="sxs-lookup"><span data-stu-id="d013b-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)</span></span>\
<span data-ttu-id="d013b-234">Un F# proveedor de tipo que se puede usar para explorar blobs, tablas y colas Azure Storage activos y aplicar fácilmente operaciones CRUD en ellos.</span><span class="sxs-lookup"><span data-stu-id="d013b-234">An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>

- <span data-ttu-id="d013b-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)</span><span class="sxs-lookup"><span data-stu-id="d013b-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)</span></span>\
<span data-ttu-id="d013b-236">Una F# API para usar Microsoft Azure servicio Table Storage</span><span class="sxs-lookup"><span data-stu-id="d013b-236">An F# API for using Microsoft Azure Table Storage service</span></span>

- <span data-ttu-id="d013b-237">[Explorador de Microsoft Azure Storage (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="d013b-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)</span></span>\
<span data-ttu-id="d013b-238">Una aplicación independiente y gratuita de Microsoft que le permite trabajar visualmente con datos de Azure Storage en Windows, OS X y Linux.</span><span class="sxs-lookup"><span data-stu-id="d013b-238">A free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="d013b-239">Referencia de almacenamiento de blobs</span><span class="sxs-lookup"><span data-stu-id="d013b-239">Blob storage reference</span></span>

- [<span data-ttu-id="d013b-240">API de Azure Storage para .NET</span><span class="sxs-lookup"><span data-stu-id="d013b-240">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="d013b-241">Referencia de la API de REST de Azure Storage Services</span><span class="sxs-lookup"><span data-stu-id="d013b-241">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="d013b-242">Guías relacionadas</span><span class="sxs-lookup"><span data-stu-id="d013b-242">Related guides</span></span>

- [<span data-ttu-id="d013b-243">Introducción con Azure Blob Storage enC#</span><span class="sxs-lookup"><span data-stu-id="d013b-243">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="d013b-244">Transferencia de datos con la utilidad de línea de comandos AzCopy en Windows</span><span class="sxs-lookup"><span data-stu-id="d013b-244">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="d013b-245">Transferencia de datos con la utilidad de línea de comandos AzCopy en Linux</span><span class="sxs-lookup"><span data-stu-id="d013b-245">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="d013b-246">Configurar cadenas de conexión de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="d013b-246">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="d013b-247">Blog del equipo de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="d013b-247">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="d013b-248">Inicio rápido: Usar .NET para crear un BLOB en el almacenamiento de objetos</span><span class="sxs-lookup"><span data-stu-id="d013b-248">Quickstart: Use .NET to create a blob in object storage</span></span>](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
