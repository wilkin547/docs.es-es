---
title: Introducción a Azure Blob storage medianteF#
description: Store datos no estructurados en la nube con Azure Blob storage.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 62178edf22ad48d0388f34488b68d135068d50a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982519"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="1d5ae-103">Introducción a Azure Blob storage mediante F\#</span><span class="sxs-lookup"><span data-stu-id="1d5ae-103">Get started with Azure Blob storage using F\#</span></span>

<span data-ttu-id="1d5ae-104">Azure Blob Storage es un servicio que almacena datos no estructurados en la nube como objetos o blobs.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="1d5ae-105">El almacenamiento de blobs puede almacenar cualquier tipo de texto o datos binarios, como un documento, un archivo multimedia o un instalador de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="1d5ae-106">El Almacenamiento de blobs también se conoce como "almacenamiento de objetos".</span><span class="sxs-lookup"><span data-stu-id="1d5ae-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="1d5ae-107">Este artículo muestra cómo realizar tareas comunes con almacenamiento de blobs.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="1d5ae-108">Los ejemplos están escritos usando F# mediante la biblioteca de cliente de Azure Storage para. NET.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="1d5ae-109">Las tareas descritas incluyen cómo cargar, enumerar, descargar y eliminar blobs.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="1d5ae-110">Información general conceptual de almacenamiento de blobs, consulte [la Guía de .NET para el almacenamiento de blobs](/azure/storage/storage-dotnet-how-to-use-blobs).</span><span class="sxs-lookup"><span data-stu-id="1d5ae-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1d5ae-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="1d5ae-111">Prerequisites</span></span>

<span data-ttu-id="1d5ae-112">Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="1d5ae-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="1d5ae-113">También necesitará la clave de acceso de almacenamiento para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="1d5ae-114">Crear un F# Script e iniciar F# interactivo</span><span class="sxs-lookup"><span data-stu-id="1d5ae-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="1d5ae-115">Los ejemplos de este artículo pueden usarse en cualquiera un F# aplicación o un F# secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="1d5ae-116">Para crear un F# de script, cree un archivo con el `.fsx` extensión, por ejemplo `blobs.fsx`, en su F# entorno de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="1d5ae-117">A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` y `Microsoft.WindowsAzure.ConfigurationManager` referencia y paquetes `WindowsAzure.Storage.dll` y `Microsoft.WindowsAzure.Configuration.dll` en su secuencia de comandos con un `#r` directiva.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="1d5ae-118">Agregue las declaraciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1d5ae-118">Add namespace declarations</span></span>

<span data-ttu-id="1d5ae-119">Agregue el siguiente `open` instrucciones a la parte superior de la `blobs.fsx` archivo:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="1d5ae-120">Obtener la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="1d5ae-120">Get your connection string</span></span>

<span data-ttu-id="1d5ae-121">En este tutorial, necesita una cadena de conexión de Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="1d5ae-122">Para obtener más información acerca de las cadenas de conexión, consulte [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="1d5ae-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="1d5ae-123">Para el tutorial, escriba la cadena de conexión en la secuencia de comandos, así:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="1d5ae-124">Sin embargo, esto es **no recomienda** proyectos reales.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="1d5ae-125">La clave de cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="1d5ae-126">Siempre debe proteger la clave de cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="1d5ae-127">Evite distribuirla a otros usuarios, codificarla de forma o guardarlo en un archivo de texto sin formato que sea accesible a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="1d5ae-128">Puede volver a generar la clave mediante Azure Portal si cree que puede verse comprometida.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="1d5ae-129">Las aplicaciones para el real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="1d5ae-130">Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="1d5ae-131">Con el Administrador de configuración de Azure es opcional.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="1d5ae-132">También puede usar una API como .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="1d5ae-133">Analizar la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="1d5ae-133">Parse the connection string</span></span>

<span data-ttu-id="1d5ae-134">Para analizar la cadena de conexión, use:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="1d5ae-135">Esto devuelve un `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="1d5ae-136">Crear algunos datos artificiales locales</span><span class="sxs-lookup"><span data-stu-id="1d5ae-136">Create some local dummy data</span></span>

<span data-ttu-id="1d5ae-137">Antes de comenzar, cree algunos datos artificiales locales en el directorio de la secuencia de comandos.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="1d5ae-138">Más tarde cargar estos datos.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="1d5ae-139">Crear al cliente del servicio Blob</span><span class="sxs-lookup"><span data-stu-id="1d5ae-139">Create the Blob service client</span></span>

<span data-ttu-id="1d5ae-140">El `CloudBlobClient` tipo le permite recuperar contenedores y blobs almacenados en Blob storage.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="1d5ae-141">Aquí es una forma de crear al cliente del servicio:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="1d5ae-142">Ahora está listo para escribir código que lee y escribe datos en Blob storage.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="1d5ae-143">Crear un contenedor</span><span class="sxs-lookup"><span data-stu-id="1d5ae-143">Create a container</span></span>

<span data-ttu-id="1d5ae-144">En este ejemplo se muestra cómo crear un contenedor si aún no existe:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="1d5ae-145">De forma predeterminada, el nuevo contenedor es privado, lo que significa que debe especificar la clave de acceso de almacenamiento para descargar blobs de este contenedor.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="1d5ae-146">Si desea que los archivos dentro del contenedor esté disponible para todos los usuarios, puede establecer el contenedor en público usando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="1d5ae-147">Cualquier persona en Internet puede ver los blobs en un contenedor público, pero se puede modificarlos o eliminarlos solo si tiene la clave de acceso de la cuenta apropiada o una firma de acceso compartido.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="1d5ae-148">Cargar un blob en un contenedor</span><span class="sxs-lookup"><span data-stu-id="1d5ae-148">Upload a blob into a container</span></span>

<span data-ttu-id="1d5ae-149">Azure Blob Storage admite blobs en bloques y blobs en páginas.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="1d5ae-150">En la mayoría de los casos, un blob en bloques es el tipo recomendado para usar.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="1d5ae-151">Para cargar un archivo en un blob en bloques, obtenga una referencia de contenedor y utilícela para obtener una referencia de blob en bloques.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="1d5ae-152">Una vez que tenga una referencia de blob, puede cargar cualquier flujo de datos a él mediante una llamada a la `UploadFromFile` método.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="1d5ae-153">Esta operación crea el blob si no existe previamente o sobrescribirlo si ya existe.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="1d5ae-154">Enumerar los blobs en un contenedor</span><span class="sxs-lookup"><span data-stu-id="1d5ae-154">List the blobs in a container</span></span>

<span data-ttu-id="1d5ae-155">Para enumerar los blobs en un contenedor, primero obtenga una referencia de contenedor.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="1d5ae-156">A continuación, puede usar el contenedor `ListBlobs` método para recuperar los blobs o directorios dentro de él.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="1d5ae-157">Para acceder al conjunto enriquecido de propiedades y métodos de una `IListBlobItem`, debe convertirla en una `CloudBlockBlob`, `CloudPageBlob`, o `CloudBlobDirectory` objeto.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="1d5ae-158">Si el tipo es desconocido, puede usar una comprobación de tipo para determinar que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="1d5ae-159">El código siguiente muestra cómo recuperar y consultar el URI de cada elemento en el `mydata` contenedor:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="1d5ae-160">También puede blobs de nombre de la información de ruta de acceso en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="1d5ae-161">Esto crea una estructura de directorios virtuales que puede organizar y recorrer tal como lo haría con un sistema de archivos tradicional.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="1d5ae-162">Tenga en cuenta que la estructura de directorios es solo virtual, los únicos recursos disponibles en Blob storage son contenedores y blobs.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="1d5ae-163">Sin embargo, la biblioteca de cliente de almacenamiento ofrece un `CloudBlobDirectory` objeto para hacer referencia a un directorio virtual y simplificar el proceso de trabajo con blobs organizados de este modo.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="1d5ae-164">Por ejemplo, considere el siguiente conjunto de blobs en bloques en un contenedor denominado `photos`:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="1d5ae-165">*photo1.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="1d5ae-165">*photo1.jpg*\\</span></span>
<span data-ttu-id="1d5ae-166">*2015/architecture/description.txt*\\</span><span class="sxs-lookup"><span data-stu-id="1d5ae-166">*2015/architecture/description.txt*\\</span></span>
<span data-ttu-id="1d5ae-167">*2015/architecture/photo3.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="1d5ae-167">*2015/architecture/photo3.jpg*\\</span></span>
<span data-ttu-id="1d5ae-168">*2015/architecture/photo4.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="1d5ae-168">*2015/architecture/photo4.jpg*\\</span></span>
<span data-ttu-id="1d5ae-169">*2016/architecture/photo5.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="1d5ae-169">*2016/architecture/photo5.jpg*\\</span></span>
<span data-ttu-id="1d5ae-170">*2016/architecture/photo6.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="1d5ae-170">*2016/architecture/photo6.jpg*\\</span></span>
<span data-ttu-id="1d5ae-171">*2016/architecture/description.txt*\\</span><span class="sxs-lookup"><span data-stu-id="1d5ae-171">*2016/architecture/description.txt*\\</span></span>
<span data-ttu-id="1d5ae-172">*2016/photo7.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="1d5ae-172">*2016/photo7.jpg*\\</span></span>

<span data-ttu-id="1d5ae-173">Cuando se llama a `ListBlobs` en un contenedor (como se muestra en el ejemplo anterior), se devuelve una lista jerárquica.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-173">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="1d5ae-174">Si contiene ambos `CloudBlobDirectory` y `CloudBlockBlob` objetos, que representan los directorios y los blobs del contenedor, de respectivamente, a continuación, el resultado tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-174">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="1d5ae-175">Opcionalmente, puede establecer el `UseFlatBlobListing` parámetro de la `ListBlobs` método `true`.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-175">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="1d5ae-176">En este caso, se devuelven todos los blobs del contenedor como un `CloudBlockBlob` objeto.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-176">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="1d5ae-177">La llamada a `ListBlobs` para devolver una lista plana tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-177">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="1d5ae-178">y, según el contenido actual del contenedor, los resultados de este aspecto:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-178">and, depending on the current contents of your container, the results look like this:</span></span>

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

## <a name="download-blobs"></a><span data-ttu-id="1d5ae-179">Descarga de blobs</span><span class="sxs-lookup"><span data-stu-id="1d5ae-179">Download blobs</span></span>

<span data-ttu-id="1d5ae-180">Para descargar blobs, primero recupere una referencia de blob y, a continuación, llame a la `DownloadToStream` método.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-180">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="1d5ae-181">En el ejemplo siguiente se usa el `DownloadToStream` método para transferir el contenido del blob a un objeto de secuencia que, a continuación, puede guardar en un archivo local.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-181">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="1d5ae-182">También puede usar el `DownloadToStream` método para descargar el contenido de un blob como una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-182">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="1d5ae-183">Eliminar blobs</span><span class="sxs-lookup"><span data-stu-id="1d5ae-183">Delete blobs</span></span>

<span data-ttu-id="1d5ae-184">Para eliminar un blob, primero obtenga una referencia de blob y, a continuación, llame a la `Delete` método en él.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-184">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="1d5ae-185">Enumerar blobs en páginas de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="1d5ae-185">List blobs in pages asynchronously</span></span>

<span data-ttu-id="1d5ae-186">Si enumerar un gran número de blobs o desea controlar el número de resultados que devuelve en una operación de listado, puede enumerar blobs en páginas de resultados.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-186">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="1d5ae-187">Este ejemplo muestra cómo devolver resultados en páginas asincrónicamente, para que la ejecución no se bloquee mientras espera a devolver un conjunto grande de resultados.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-187">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="1d5ae-188">En este ejemplo se muestra un listado de blobs plano, pero también puede realizar un listado jerárquico estableciendo el `useFlatBlobListing` parámetro de la `ListBlobsSegmentedAsync` método `false`.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-188">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="1d5ae-189">El ejemplo define un método asincrónico, con un `async` bloque.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-189">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="1d5ae-190">El ``let!`` palabra clave suspende la ejecución del método de ejemplo hasta que se complete la tarea de enumeración.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-190">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="1d5ae-191">Ahora podemos usar esta rutina asincrónica como sigue.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-191">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="1d5ae-192">En primer lugar cargar algunos datos artificiales (mediante el archivo local que creó anteriormente en este tutorial).</span><span class="sxs-lookup"><span data-stu-id="1d5ae-192">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="1d5ae-193">Ahora, llame a la rutina.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-193">Now, call the routine.</span></span> <span data-ttu-id="1d5ae-194">Usa `Async.RunSynchronously` para forzar la ejecución de la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-194">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="1d5ae-195">Escribir en un blob en anexos</span><span class="sxs-lookup"><span data-stu-id="1d5ae-195">Writing to an append blob</span></span>

<span data-ttu-id="1d5ae-196">Un blob en anexos se optimiza para las operaciones de anexado, como el registro.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-196">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="1d5ae-197">Como un blob en bloques, un blob en anexos está formado por bloques, pero cuando se agrega un nuevo bloque a un blob en anexos, siempre se anexa al final del blob.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-197">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="1d5ae-198">No se puede actualizar o eliminar un bloque existente en un blob en anexos.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-198">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="1d5ae-199">Los identificadores de bloque para un blob en anexos no se exponen como aparecen en un blob en bloques.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-199">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="1d5ae-200">Cada bloque en un blob en anexos puede tener un tamaño diferente, hasta un máximo de 4 MB, y un blob en anexos puede incluir un máximo de 50.000 bloques.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-200">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="1d5ae-201">Por lo tanto, el tamaño máximo de un blob en anexos es un poco más de 195 GB (4 MB × 50 000 bloques).</span><span class="sxs-lookup"><span data-stu-id="1d5ae-201">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="1d5ae-202">El ejemplo siguiente crea un nuevo blob en anexos y le anexa algunos datos, simular una operación de registro simple.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-202">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="1d5ae-203">Consulte [descripción Blobs en bloques, Blobs en páginas y Blobs en anexos](https://msdn.microsoft.com/library/azure/ee691964.aspx) para obtener más información sobre las diferencias entre los tres tipos de blobs.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-203">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="1d5ae-204">Acceso simultáneo</span><span class="sxs-lookup"><span data-stu-id="1d5ae-204">Concurrent access</span></span>

<span data-ttu-id="1d5ae-205">Para admitir el acceso simultáneo a un blob desde varios clientes o varias instancias de proceso, puede usar **ETags** o **concesiones**.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-205">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

* <span data-ttu-id="1d5ae-206">**ETag** -proporciona una manera de detectar que se ha modificado el blob o contenedor por otro proceso</span><span class="sxs-lookup"><span data-stu-id="1d5ae-206">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

* <span data-ttu-id="1d5ae-207">**Concesión** -proporciona una manera de obtener exclusivo y renovable de escritura o eliminación de acceso a un blob durante un período de tiempo</span><span class="sxs-lookup"><span data-stu-id="1d5ae-207">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="1d5ae-208">Para obtener más información, consulte [administración de la simultaneidad en Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span><span class="sxs-lookup"><span data-stu-id="1d5ae-208">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="1d5ae-209">Nomenclatura de contenedores</span><span class="sxs-lookup"><span data-stu-id="1d5ae-209">Naming containers</span></span>

<span data-ttu-id="1d5ae-210">Todos los blobs de Azure storage deben residir en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-210">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="1d5ae-211">El contenedor forma parte del nombre del blob.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-211">The container forms part of the blob name.</span></span> <span data-ttu-id="1d5ae-212">Por ejemplo, `mydata` es el nombre del contenedor de estos URI de blob de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-212">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="1d5ae-213">Un nombre de contenedor debe ser un nombre DNS válido, que se ajuste a las reglas de nomenclatura siguientes:</span><span class="sxs-lookup"><span data-stu-id="1d5ae-213">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="1d5ae-214">Los nombres de contenedor deben empezar por una letra o un número y pueden contener solo letras, números y guiones (-).</span><span class="sxs-lookup"><span data-stu-id="1d5ae-214">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="1d5ae-215">Deben estar precedido y seguido por una letra o un número; inmediatamente todos los caracteres de guión (-) no se permiten guiones consecutivos en nombres de contenedor.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-215">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="1d5ae-216">Todas las letras de un nombre de contenedor deben estar en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-216">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="1d5ae-217">Los nombres de contenedor deben tener entre 3 y 63 caracteres.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-217">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="1d5ae-218">Tenga en cuenta que el nombre de un contenedor siempre debe estar en minúscula.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-218">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="1d5ae-219">Si se incluye una letra mayúscula en un nombre de contenedor o infringen los reglas de nomenclatura de contenedores, recibirá un error 400 (solicitud incorrecta).</span><span class="sxs-lookup"><span data-stu-id="1d5ae-219">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="1d5ae-220">Administrar la seguridad de blobs</span><span class="sxs-lookup"><span data-stu-id="1d5ae-220">Managing security for blobs</span></span>

<span data-ttu-id="1d5ae-221">De forma predeterminada, Azure Storage protege sus datos al limitar el acceso al propietario de la cuenta, quien está en posesión de las claves de acceso de cuenta.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-221">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="1d5ae-222">Cuando necesite compartir datos blob en la cuenta de almacenamiento, es importante hacerlo sin poner en peligro la seguridad de las claves de acceso de cuenta.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-222">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="1d5ae-223">Además, puede cifrar los datos de blob para asegurarse de que es seguro pasar a través del cable y el almacenamiento de Azure.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-223">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="1d5ae-224">Controlar el acceso a datos blob</span><span class="sxs-lookup"><span data-stu-id="1d5ae-224">Controlling access to blob data</span></span>

<span data-ttu-id="1d5ae-225">De forma predeterminada, los datos de blob en la cuenta de almacenamiento están accesibles solo al propietario de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-225">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="1d5ae-226">Autenticar las solicitudes en el almacenamiento de blobs, requiere la clave de acceso de la cuenta de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-226">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="1d5ae-227">Sin embargo, es posible que desee que determinados datos blob esté disponible para otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-227">However, you might want to make certain blob data available to other users.</span></span>

### <a name="encrypting-blob-data"></a><span data-ttu-id="1d5ae-228">Cifrado de datos blob</span><span class="sxs-lookup"><span data-stu-id="1d5ae-228">Encrypting blob data</span></span>

<span data-ttu-id="1d5ae-229">Azure Storage admite el cifrado de datos de blob en el cliente y en el servidor.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-229">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1d5ae-230">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1d5ae-230">Next steps</span></span>

<span data-ttu-id="1d5ae-231">Ahora que ha aprendido los conceptos básicos del almacenamiento de blobs, siga estos vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-231">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="1d5ae-232">Herramientas</span><span class="sxs-lookup"><span data-stu-id="1d5ae-232">Tools</span></span>

- <span data-ttu-id="1d5ae-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\\</span><span class="sxs-lookup"><span data-stu-id="1d5ae-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\\</span></span>
<span data-ttu-id="1d5ae-234">Un F# proveedor de tipos que se puede usar para explorar los recursos Blob, tabla y cola de Azure Storage y aplicar fácilmente las operaciones CRUD en ellos.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-234">An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>

- <span data-ttu-id="1d5ae-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\\</span><span class="sxs-lookup"><span data-stu-id="1d5ae-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\\</span></span>
<span data-ttu-id="1d5ae-236">Un F# API para usar el servicio de Microsoft Azure Table Storage</span><span class="sxs-lookup"><span data-stu-id="1d5ae-236">An F# API for using Microsoft Azure Table Storage service</span></span>

- <span data-ttu-id="1d5ae-237">[Explorador de Microsoft Azure Storage (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\\</span><span class="sxs-lookup"><span data-stu-id="1d5ae-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\\</span></span>
<span data-ttu-id="1d5ae-238">Una aplicación independiente y gratuita de Microsoft que le permite trabajar visualmente con datos de Azure Storage en Windows, OS X y Linux.</span><span class="sxs-lookup"><span data-stu-id="1d5ae-238">A free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="1d5ae-239">Referencia de BLOB storage</span><span class="sxs-lookup"><span data-stu-id="1d5ae-239">Blob storage reference</span></span>

- [<span data-ttu-id="1d5ae-240">API de Azure Storage para .NET</span><span class="sxs-lookup"><span data-stu-id="1d5ae-240">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="1d5ae-241">Referencia de API de REST de servicios de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="1d5ae-241">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="1d5ae-242">Guías relacionadas</span><span class="sxs-lookup"><span data-stu-id="1d5ae-242">Related guides</span></span>

- [<span data-ttu-id="1d5ae-243">Introducción a Azure Blob Storage en C#</span><span class="sxs-lookup"><span data-stu-id="1d5ae-243">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="1d5ae-244">Transferencia de datos con la utilidad de línea de comandos de AzCopy en Windows</span><span class="sxs-lookup"><span data-stu-id="1d5ae-244">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="1d5ae-245">Transferencia de datos con la utilidad de línea de comandos de AzCopy en Linux</span><span class="sxs-lookup"><span data-stu-id="1d5ae-245">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="1d5ae-246">Configurar cadenas de conexión de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="1d5ae-246">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="1d5ae-247">Blog del equipo de almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="1d5ae-247">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="1d5ae-248">Inicio rápido: Usar .NET para crear un blob en almacenamiento de objetos</span><span class="sxs-lookup"><span data-stu-id="1d5ae-248">Quickstart: Use .NET to create a blob in object storage</span></span>](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
