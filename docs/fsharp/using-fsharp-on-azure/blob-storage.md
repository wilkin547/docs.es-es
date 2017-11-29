---
title: "Introducción al almacenamiento de blobs de Azure con F #"
description: Almacenar datos no estructurados en la nube con el almacenamiento de blobs de Azure.
keywords: "Visual f #, f #, funcional de programación,. NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c5b74a4f-dcd1-4849-930c-904b6c8a04e1
ms.openlocfilehash: 92e26aff605d3bed89e388dd3616a2a9a3a96081
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="b0389-104">Introducción al almacenamiento de blobs de Azure con F #</span><span class="sxs-lookup"><span data-stu-id="b0389-104">Get started with Azure Blob storage using F#</span></span> #

<span data-ttu-id="b0389-105">Azure Blob Storage es un servicio que almacena datos no estructurados en la nube como objetos o blobs.</span><span class="sxs-lookup"><span data-stu-id="b0389-105">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="b0389-106">El almacenamiento de blobs puede almacenar cualquier tipo de texto o datos binarios, como un documento, un archivo multimedia o un instalador de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0389-106">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="b0389-107">El Almacenamiento de blobs también se conoce como "almacenamiento de objetos".</span><span class="sxs-lookup"><span data-stu-id="b0389-107">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="b0389-108">Este artículo muestra cómo realizar tareas comunes mediante el almacenamiento de blobs.</span><span class="sxs-lookup"><span data-stu-id="b0389-108">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="b0389-109">Los ejemplos se escriben con F # mediante la biblioteca de cliente de almacenamiento de Azure para. NET.</span><span class="sxs-lookup"><span data-stu-id="b0389-109">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="b0389-110">Entre las tareas incluyen cómo cargar, enumerar, descargar y eliminar los blobs.</span><span class="sxs-lookup"><span data-stu-id="b0389-110">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="b0389-111">Para obtener información conceptual de almacenamiento de blobs, vea [la Guía de .NET para el almacenamiento de blobs](/azure/storage/storage-dotnet-how-to-use-blobs).</span><span class="sxs-lookup"><span data-stu-id="b0389-111">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b0389-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b0389-112">Prerequisites</span></span>

<span data-ttu-id="b0389-113">Para utilizar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="b0389-113">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="b0389-114">También se necesita la clave de acceso de almacenamiento para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="b0389-114">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="b0389-115">Crear un Script de F # y el inicio de F # Interactive</span><span class="sxs-lookup"><span data-stu-id="b0389-115">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="b0389-116">Los ejemplos de este artículo pueden usarse en una aplicación de F # o un script de F #.</span><span class="sxs-lookup"><span data-stu-id="b0389-116">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="b0389-117">Para crear un script de F #, cree un archivo con el `.fsx` extensión, por ejemplo `blobs.fsx`, en el entorno de desarrollo de F #.</span><span class="sxs-lookup"><span data-stu-id="b0389-117">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="b0389-118">A continuación, use un [el Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` y `Microsoft.WindowsAzure.ConfigurationManager` paquetes y referencia `WindowsAzure.Storage.dll` y `Microsoft.WindowsAzure.Configuration.dll` en su secuencia de comandos mediante una `#r` directiva.</span><span class="sxs-lookup"><span data-stu-id="b0389-118">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="b0389-119">Agregue las declaraciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b0389-119">Add namespace declarations</span></span>

<span data-ttu-id="b0389-120">Agregue el siguiente `open` instrucciones a la parte superior de la `blobs.fsx` archivo:</span><span class="sxs-lookup"><span data-stu-id="b0389-120">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="b0389-121">Obtener la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="b0389-121">Get your connection string</span></span>

<span data-ttu-id="b0389-122">Necesita una cadena de conexión de almacenamiento de Azure para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="b0389-122">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="b0389-123">Para obtener más información acerca de las cadenas de conexión, vea [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="b0389-123">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="b0389-124">Para el tutorial, escriba la cadena de conexión en el script, así:</span><span class="sxs-lookup"><span data-stu-id="b0389-124">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="b0389-125">Sin embargo, esto es **no recomienda** proyectos de una manera real.</span><span class="sxs-lookup"><span data-stu-id="b0389-125">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="b0389-126">La clave de cuenta de almacenamiento es similar a la contraseña raíz para la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b0389-126">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="b0389-127">Tenga siempre cuidado proteger la clave de cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b0389-127">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="b0389-128">Evitar la distribución a otros usuarios, codificar de forma rígida, o guardarlo en un archivo de texto sin formato sea accesible a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="b0389-128">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="b0389-129">Puede volver a generar la clave mediante el Portal de Azure si cree que se han comprometido.</span><span class="sxs-lookup"><span data-stu-id="b0389-129">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="b0389-130">Las aplicaciones de una manera real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b0389-130">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="b0389-131">Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:</span><span class="sxs-lookup"><span data-stu-id="b0389-131">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="b0389-132">Con el Administrador de configuración de Azure es opcional.</span><span class="sxs-lookup"><span data-stu-id="b0389-132">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="b0389-133">También puede utilizar una API como .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="b0389-133">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="b0389-134">Analizar la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="b0389-134">Parse the connection string</span></span>

<span data-ttu-id="b0389-135">Para analizar la cadena de conexión, use:</span><span class="sxs-lookup"><span data-stu-id="b0389-135">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="b0389-136">Esto devuelve un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="b0389-136">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="b0389-137">Crear algunos datos ficticios locales</span><span class="sxs-lookup"><span data-stu-id="b0389-137">Create some local dummy data</span></span>

<span data-ttu-id="b0389-138">Antes de empezar, cree algunos datos ficticios locales en el directorio de la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="b0389-138">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="b0389-139">Más adelante, cargar estos datos.</span><span class="sxs-lookup"><span data-stu-id="b0389-139">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="b0389-140">Crear al cliente del servicio Blob</span><span class="sxs-lookup"><span data-stu-id="b0389-140">Create the Blob service client</span></span>

<span data-ttu-id="b0389-141">El `CloudBlobClient` tipo le permite recuperar los contenedores y blobs almacenados en almacenamiento de blobs.</span><span class="sxs-lookup"><span data-stu-id="b0389-141">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="b0389-142">Aquí es una manera de crear al cliente del servicio:</span><span class="sxs-lookup"><span data-stu-id="b0389-142">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="b0389-143">Ahora está listo para escribir código que lee datos de y escribe datos en almacenamiento de blobs.</span><span class="sxs-lookup"><span data-stu-id="b0389-143">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="b0389-144">Crear un contenedor</span><span class="sxs-lookup"><span data-stu-id="b0389-144">Create a container</span></span>

<span data-ttu-id="b0389-145">En este ejemplo se muestra cómo crear un contenedor si aún no existe:</span><span class="sxs-lookup"><span data-stu-id="b0389-145">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="b0389-146">De forma predeterminada, el nuevo contenedor es privado, lo que significa que debe especificar la clave de acceso de almacenamiento para descargar los blobs de este contenedor.</span><span class="sxs-lookup"><span data-stu-id="b0389-146">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="b0389-147">Si desea poner a disposición los archivos dentro del contenedor para todos los usuarios, puede establecer el contenedor como público con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b0389-147">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="b0389-148">Todos los usuarios de Internet pueden ver los blobs en un contenedor público, pero puede modificar o eliminarlos sólo si tiene la clave de acceso de cuenta correspondiente o una firma de acceso compartido.</span><span class="sxs-lookup"><span data-stu-id="b0389-148">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="b0389-149">Cargar un blob en un contenedor</span><span class="sxs-lookup"><span data-stu-id="b0389-149">Upload a blob into a container</span></span>

<span data-ttu-id="b0389-150">Almacenamiento de blobs de Azure es compatible con blobs en bloques y blobs en páginas.</span><span class="sxs-lookup"><span data-stu-id="b0389-150">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="b0389-151">En la mayoría de los casos, un blob en bloques es el tipo recomendado para usar.</span><span class="sxs-lookup"><span data-stu-id="b0389-151">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="b0389-152">Para cargar un archivo en un blob en bloques, obtener una referencia de contenedor y usarlo para obtener una referencia de blob de bloque.</span><span class="sxs-lookup"><span data-stu-id="b0389-152">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="b0389-153">Una vez que tenga una referencia de blob, puede cargar todos los flujos de datos a ella mediante una llamada a la `UploadFromFile` método.</span><span class="sxs-lookup"><span data-stu-id="b0389-153">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="b0389-154">Esta operación crea el blob si no existe previamente o sobrescribir si existe.</span><span class="sxs-lookup"><span data-stu-id="b0389-154">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="b0389-155">Enumerar los blobs en un contenedor</span><span class="sxs-lookup"><span data-stu-id="b0389-155">List the blobs in a container</span></span>

<span data-ttu-id="b0389-156">Para enumerar los blobs en un contenedor, primero hay que obtener una referencia de contenedor.</span><span class="sxs-lookup"><span data-stu-id="b0389-156">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="b0389-157">A continuación, puede usar el contenedor `ListBlobs` método para recuperar los blobs o directorios dentro de él.</span><span class="sxs-lookup"><span data-stu-id="b0389-157">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="b0389-158">Para tener acceso el amplio conjunto de propiedades y métodos para un devuelto `IListBlobItem`, debe convertirlo a un `CloudBlockBlob`, `CloudPageBlob`, o `CloudBlobDirectory` objeto.</span><span class="sxs-lookup"><span data-stu-id="b0389-158">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="b0389-159">Si el tipo es desconocido, puede usar una comprobación de tipo para determinar qué convertirlo a.</span><span class="sxs-lookup"><span data-stu-id="b0389-159">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="b0389-160">El código siguiente muestra cómo recuperar y salida el URI de cada elemento en el `mydata` contenedor:</span><span class="sxs-lookup"><span data-stu-id="b0389-160">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="b0389-161">También puede blobs de nombre con la información de ruta de acceso en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="b0389-161">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="b0389-162">Esto crea una estructura de directorios virtuales que se puede organizar y recorrer tal y como lo haría con un sistema de archivos tradicional.</span><span class="sxs-lookup"><span data-stu-id="b0389-162">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="b0389-163">Tenga en cuenta que la estructura de directorios es virtual solo, los únicos recursos disponibles en el almacenamiento de blobs son contenedores y blobs.</span><span class="sxs-lookup"><span data-stu-id="b0389-163">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="b0389-164">Sin embargo, la biblioteca de cliente de almacenamiento ofrece una `CloudBlobDirectory` objeto para hacer referencia a un directorio virtual y simplificar el proceso de trabajar con los blobs que se organizan de esta manera.</span><span class="sxs-lookup"><span data-stu-id="b0389-164">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="b0389-165">Por ejemplo, considere el siguiente conjunto de blobs en bloques en un contenedor denominado `photos`:</span><span class="sxs-lookup"><span data-stu-id="b0389-165">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="b0389-166">*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015 / arquitectura/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg* 
 *2016/architecture/description.txt*
*2016/photo7.jpg*</span><span class="sxs-lookup"><span data-stu-id="b0389-166">*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015/architecture/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg*
*2016/architecture/description.txt*
*2016/photo7.jpg*</span></span>

<span data-ttu-id="b0389-167">Cuando se llama a `ListBlobs` en un contenedor (como en el ejemplo anterior), se devuelve una lista jerárquica.</span><span class="sxs-lookup"><span data-stu-id="b0389-167">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="b0389-168">Si contiene dos `CloudBlobDirectory` y `CloudBlockBlob` objetos, que representan los directorios y los blobs del contenedor de respectivamente, a continuación, la salida resultante es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b0389-168">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="b0389-169">Si lo desea, puede establecer la `UseFlatBlobListing` parámetro de la `ListBlobs` método `true`.</span><span class="sxs-lookup"><span data-stu-id="b0389-169">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="b0389-170">En este caso, se devuelve cada blob del contenedor como una `CloudBlockBlob` objeto.</span><span class="sxs-lookup"><span data-stu-id="b0389-170">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="b0389-171">La llamada a `ListBlobs` para devolver una lista plana tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="b0389-171">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="b0389-172">y, según el contenido actual del contenedor, los resultados de un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="b0389-172">and, depending on the current contents of your container, the results look like this:</span></span>

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

## <a name="download-blobs"></a><span data-ttu-id="b0389-173">Descargar blobs</span><span class="sxs-lookup"><span data-stu-id="b0389-173">Download blobs</span></span>

<span data-ttu-id="b0389-174">Para descargar los blobs, recuperar primero una referencia de blob y, a continuación, llame a la `DownloadToStream` método.</span><span class="sxs-lookup"><span data-stu-id="b0389-174">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="b0389-175">En el ejemplo siguiente se usa el `DownloadToStream` método para transferir el contenido del blob en un objeto stream que, a continuación, puede hacer persistir para un archivo local.</span><span class="sxs-lookup"><span data-stu-id="b0389-175">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="b0389-176">También puede usar el `DownloadToStream` método para descargar el contenido de un blob como una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="b0389-176">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="b0389-177">Eliminar los blobs</span><span class="sxs-lookup"><span data-stu-id="b0389-177">Delete blobs</span></span>

<span data-ttu-id="b0389-178">Para eliminar un blob, primero hay que obtener una referencia de blob y, a continuación, llame a la `Delete` método en él.</span><span class="sxs-lookup"><span data-stu-id="b0389-178">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="b0389-179">Enumerar blobs en páginas de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="b0389-179">List blobs in pages asynchronously</span></span>

<span data-ttu-id="b0389-180">Si enumerar un gran número de blobs, o para controlar el número de resultados que devuelven en una sola operación de lista, puede enumerar blobs en páginas de resultados.</span><span class="sxs-lookup"><span data-stu-id="b0389-180">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="b0389-181">Este ejemplo muestra cómo devolver resultados en las páginas de forma asincrónica, por lo que no la ejecución se bloquea mientras se esperaba para devolver un conjunto grande de resultados.</span><span class="sxs-lookup"><span data-stu-id="b0389-181">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="b0389-182">Este ejemplo muestra una lista plana de blobs, pero también puede realizar una lista jerárquica, estableciendo el `useFlatBlobListing` parámetro de la `ListBlobsSegmentedAsync` método `false`.</span><span class="sxs-lookup"><span data-stu-id="b0389-182">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="b0389-183">El ejemplo define un método asincrónico, con un `async` bloque.</span><span class="sxs-lookup"><span data-stu-id="b0389-183">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="b0389-184">El ``let!`` palabra clave suspende la ejecución del método de ejemplo hasta que se complete la tarea de la lista.</span><span class="sxs-lookup"><span data-stu-id="b0389-184">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="b0389-185">Ahora podemos usar esta rutina asincrónica como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="b0389-185">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="b0389-186">Cargar primero algunos datos ficticios (mediante el archivo local que creó anteriormente en este tutorial).</span><span class="sxs-lookup"><span data-stu-id="b0389-186">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="b0389-187">Ahora, llame a la rutina.</span><span class="sxs-lookup"><span data-stu-id="b0389-187">Now, call the routine.</span></span> <span data-ttu-id="b0389-188">Utiliza ``Async.RunSynchronously`` para forzar la ejecución de la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="b0389-188">You use ``Async.RunSynchronously`` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="b0389-189">Escribir en un blob en anexos</span><span class="sxs-lookup"><span data-stu-id="b0389-189">Writing to an append blob</span></span>

<span data-ttu-id="b0389-190">Un blob en anexos está optimizado para las operaciones de anexado, como el registro.</span><span class="sxs-lookup"><span data-stu-id="b0389-190">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="b0389-191">Como un blob en bloques, un blob en anexos está formado por bloques, pero cuando agrega un nuevo bloque a un blob en anexos, siempre se anexa al final del blob.</span><span class="sxs-lookup"><span data-stu-id="b0389-191">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="b0389-192">No se puede actualizar o eliminar un bloque existente en un blob en anexos.</span><span class="sxs-lookup"><span data-stu-id="b0389-192">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="b0389-193">Los identificadores de bloque para un blob en anexos no se exponen como sirven como un blob en bloques.</span><span class="sxs-lookup"><span data-stu-id="b0389-193">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="b0389-194">Cada bloque de un blob en anexos puede tener un tamaño diferente, hasta un máximo de 4 MB, y un blob en anexos puede incluir un máximo de 50.000 bloques.</span><span class="sxs-lookup"><span data-stu-id="b0389-194">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="b0389-195">El tamaño máximo de un blob en anexos, por tanto, es un poco más de 195 GB (4 MB X 50.000 bloques).</span><span class="sxs-lookup"><span data-stu-id="b0389-195">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="b0389-196">En el ejemplo siguiente se crea un nuevo blob en anexos y anexa algunos datos, simular una operación de registro simple.</span><span class="sxs-lookup"><span data-stu-id="b0389-196">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="b0389-197">Vea [descripción Blobs en bloques, Blobs de página y anexar Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) para obtener más información sobre las diferencias entre los tres tipos de blobs.</span><span class="sxs-lookup"><span data-stu-id="b0389-197">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="b0389-198">Acceso simultáneo</span><span class="sxs-lookup"><span data-stu-id="b0389-198">Concurrent access</span></span>

<span data-ttu-id="b0389-199">Para permitir el acceso simultáneo a un blob desde varios clientes o varias instancias de proceso, puede usar **ETags** o **concesiones**.</span><span class="sxs-lookup"><span data-stu-id="b0389-199">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

* <span data-ttu-id="b0389-200">**ETag** -proporciona una manera de detectar que el blob o contenedor se ha modificado por otro proceso</span><span class="sxs-lookup"><span data-stu-id="b0389-200">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

* <span data-ttu-id="b0389-201">**Concesión** -proporciona una manera de obtener exclusivo, renovable, escribir o eliminar el acceso a un blob durante un período de tiempo</span><span class="sxs-lookup"><span data-stu-id="b0389-201">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="b0389-202">Para obtener más información, consulte [administrar la simultaneidad en el almacenamiento de Azure de Microsoft](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span><span class="sxs-lookup"><span data-stu-id="b0389-202">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="b0389-203">Nomenclatura de contenedores</span><span class="sxs-lookup"><span data-stu-id="b0389-203">Naming containers</span></span>

<span data-ttu-id="b0389-204">Cada blob en el almacenamiento de Azure debe residir en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="b0389-204">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="b0389-205">El contenedor forma parte del nombre del blob.</span><span class="sxs-lookup"><span data-stu-id="b0389-205">The container forms part of the blob name.</span></span> <span data-ttu-id="b0389-206">Por ejemplo, `mydata` es el nombre del contenedor en estos URI de blob de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b0389-206">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="b0389-207">Un nombre de contenedor debe ser un nombre DNS válido, conforme a las reglas de nomenclatura siguientes:</span><span class="sxs-lookup"><span data-stu-id="b0389-207">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="b0389-208">Los nombres de contenedor deben empezar por una letra o un número y pueden contener solo letras, números y el carácter de guión (-).</span><span class="sxs-lookup"><span data-stu-id="b0389-208">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="b0389-209">Deben estar precedido y seguido por una letra o un número; inmediatamente todos los caracteres guión (-) no se permiten guiones consecutivos en los nombres de contenedor.</span><span class="sxs-lookup"><span data-stu-id="b0389-209">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="b0389-210">Todas las letras de un nombre de contenedor deben estar en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="b0389-210">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="b0389-211">Los nombres de contenedor deben tener entre 3 y 63 caracteres.</span><span class="sxs-lookup"><span data-stu-id="b0389-211">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="b0389-212">Tenga en cuenta que el nombre de un contenedor siempre debe estar en minúscula.</span><span class="sxs-lookup"><span data-stu-id="b0389-212">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="b0389-213">Si incluye una letra mayúscula en un nombre de contenedor, o en caso contrario, infringe el reglas de nombres de contenedor, recibirá un error 400 (solicitud incorrecta).</span><span class="sxs-lookup"><span data-stu-id="b0389-213">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="b0389-214">Administrar la seguridad de blobs</span><span class="sxs-lookup"><span data-stu-id="b0389-214">Managing security for blobs</span></span>

<span data-ttu-id="b0389-215">De forma predeterminada, el almacenamiento de Azure se mantienen los datos seguros limitando el acceso al propietario de la cuenta, que está en posesión de las claves de acceso de cuenta.</span><span class="sxs-lookup"><span data-stu-id="b0389-215">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="b0389-216">Cuando necesite compartir los datos de blob en la cuenta de almacenamiento, es importante hacerlo sin poner en peligro la seguridad de las claves de acceso de cuenta.</span><span class="sxs-lookup"><span data-stu-id="b0389-216">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="b0389-217">Además, puede cifrar los datos de blob para asegurarse de que es seguro pasar a través de la conexión y el almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="b0389-217">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="b0389-218">Controlar el acceso a los datos blob</span><span class="sxs-lookup"><span data-stu-id="b0389-218">Controlling access to blob data</span></span>

<span data-ttu-id="b0389-219">De forma predeterminada, los datos blob en la cuenta de almacenamiento son accesibles únicamente al propietario de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b0389-219">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="b0389-220">Autenticar las solicitudes en el almacenamiento de blobs, requiere la clave de acceso de cuenta predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b0389-220">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="b0389-221">Sin embargo, puede que determinados datos de blob esté disponible para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="b0389-221">However, you might want to make certain blob data available to other users.</span></span>

<span data-ttu-id="b0389-222">Para obtener más información sobre cómo controlar el acceso al almacenamiento de blobs, vea [la Guía de .NET para la sección de almacenamiento de blobs en el control de acceso](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).</span><span class="sxs-lookup"><span data-stu-id="b0389-222">For details on how to control access to blob storage, see [the .NET guide for blob storage section on access control](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).</span></span>


### <a name="encrypting-blob-data"></a><span data-ttu-id="b0389-223">Cifrar los datos de blob</span><span class="sxs-lookup"><span data-stu-id="b0389-223">Encrypting blob data</span></span>

<span data-ttu-id="b0389-224">Almacenamiento de Azure admite el cifrado de datos de blob en el cliente y en el servidor.</span><span class="sxs-lookup"><span data-stu-id="b0389-224">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

<span data-ttu-id="b0389-225">Para obtener más información sobre cómo cifrar datos blob, vea [la Guía de .NET para la sección de almacenamiento blob cifrado](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).</span><span class="sxs-lookup"><span data-stu-id="b0389-225">For details on encrypting blob data, see [the .NET guide for blob storage section on encryption](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b0389-226">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b0389-226">Next steps</span></span>

<span data-ttu-id="b0389-227">Ahora que conoce los conceptos básicos de almacenamiento de blobs, siga estos vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b0389-227">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="b0389-228">Herramientas</span><span class="sxs-lookup"><span data-stu-id="b0389-228">Tools</span></span>
- <span data-ttu-id="b0389-229">[F # AzureStorageTypeProvider](http://fsprojects.github.io/AzureStorageTypeProvider/) un tipo de proveedor de F # que se puede usar para explorar recursos de Blob, tabla y cola de almacenamiento de Azure y aplicar las operaciones CRUD en ellos con más facilidad.</span><span class="sxs-lookup"><span data-stu-id="b0389-229">[F# AzureStorageTypeProvider](http://fsprojects.github.io/AzureStorageTypeProvider/) An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>
- <span data-ttu-id="b0389-230">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) una API de F # para usar el servicio de almacenamiento de tablas de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="b0389-230">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) An F# API for using Microsoft Azure Table Storage service</span></span>
- <span data-ttu-id="b0389-231">[Explorador de almacenamiento de Azure de Microsoft (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) es una aplicación independiente disponible, de Microsoft que le permite trabajar visualmente con datos del almacenamiento de Azure en Windows, OS X y Linux.</span><span class="sxs-lookup"><span data-stu-id="b0389-231">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) is a free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="b0389-232">Referencia de almacenamiento de blobs</span><span class="sxs-lookup"><span data-stu-id="b0389-232">Blob storage reference</span></span>

- [<span data-ttu-id="b0389-233">Biblioteca de cliente de almacenamiento para la referencia de .NET</span><span class="sxs-lookup"><span data-stu-id="b0389-233">Storage Client Library for .NET reference</span></span>](http://go.microsoft.com/fwlink/?LinkID=390731&clcid=0x409)
- [<span data-ttu-id="b0389-234">Referencia de la API de REST</span><span class="sxs-lookup"><span data-stu-id="b0389-234">REST API reference</span></span>](http://msdn.microsoft.com/library/azure/dd179355)

### <a name="related-guides"></a><span data-ttu-id="b0389-235">Guías relacionadas</span><span class="sxs-lookup"><span data-stu-id="b0389-235">Related guides</span></span>

- [<span data-ttu-id="b0389-236">Introducción a almacenamiento de blobs de Azure en C#</span><span class="sxs-lookup"><span data-stu-id="b0389-236">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/documentation/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="b0389-237">Transferencia de datos con la utilidad de línea de comandos de AzCopy</span><span class="sxs-lookup"><span data-stu-id="b0389-237">Transfer data with the AzCopy command-line utility</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="b0389-238">Configurar cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="b0389-238">Configuring Connection Strings</span></span>](http://msdn.microsoft.com/library/azure/ee758697.aspx)
- [<span data-ttu-id="b0389-239">Blog del equipo de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="b0389-239">Azure Storage Team Blog</span></span>](http://blogs.msdn.com/b/windowsazurestorage/)
