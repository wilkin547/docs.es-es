---
title: Introducción a Azure Blob Storage mediante F#
description: Almacene datos no estructurados en la nube con Azure BLOB Storage.
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: 91aec8fc2b57c71ce4ba47d62619912af6c71e59
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756252"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="e3ed2-103">Introducción a Azure BLOB Storage mediante F\#</span><span class="sxs-lookup"><span data-stu-id="e3ed2-103">Get started with Azure Blob storage using F\#</span></span>

<span data-ttu-id="e3ed2-104">Almacenamiento de blobs de Azure es un servicio que almacena datos no estructurados en la nube como objetos o blobs.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="e3ed2-105">El Almacenamiento de blobs puede almacenar cualquier tipo de datos binarios o texto, como un documento, un archivo multimedia o un instalador de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="e3ed2-106">El Almacenamiento de blobs a veces se conoce como "almacenamiento de objetos".</span><span class="sxs-lookup"><span data-stu-id="e3ed2-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="e3ed2-107">En este artículo se muestra cómo realizar tareas comunes con el almacenamiento de blobs.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="e3ed2-108">Los ejemplos se escriben con F # mediante la biblioteca de cliente de Azure Storage para .NET.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="e3ed2-109">Entre las tareas descritas se incluyen cómo cargar, enumerar, descargar y eliminar BLOBs.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="e3ed2-110">Para obtener información general conceptual sobre el almacenamiento de blobs, consulte [la guía de .net para BLOB Storage](/azure/storage/blobs/storage-quickstart-blobs-dotnet).</span><span class="sxs-lookup"><span data-stu-id="e3ed2-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/blobs/storage-quickstart-blobs-dotnet).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e3ed2-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="e3ed2-111">Prerequisites</span></span>

<span data-ttu-id="e3ed2-112">Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/common/storage-account-create).</span><span class="sxs-lookup"><span data-stu-id="e3ed2-112">To use this guide, you must first [create an Azure storage account](/azure/storage/common/storage-account-create).</span></span> <span data-ttu-id="e3ed2-113">También necesitará la clave de acceso de almacenamiento para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="e3ed2-114">Crear un script de F # e iniciar F# interactivo</span><span class="sxs-lookup"><span data-stu-id="e3ed2-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="e3ed2-115">Los ejemplos de este artículo se pueden usar en una aplicación de F # o en un script de F #.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="e3ed2-116">Para crear un script de F #, cree un archivo con la `.fsx` extensión, por ejemplo `blobs.fsx` , en el entorno de desarrollo de f #.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="e3ed2-117">A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar `WindowsAzure.Storage` los `Microsoft.WindowsAzure.ConfigurationManager` paquetes y y la referencia `WindowsAzure.Storage.dll` y `Microsoft.WindowsAzure.Configuration.dll` en el script mediante una `#r` Directiva.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="e3ed2-118">Incorporación de declaraciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="e3ed2-118">Add namespace declarations</span></span>

<span data-ttu-id="e3ed2-119">Agregue las siguientes instrucciones `open` en la parte superior del archivo `blobs.fsx`:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="e3ed2-120">Obtención de la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="e3ed2-120">Get your connection string</span></span>

<span data-ttu-id="e3ed2-121">Necesita una cadena de conexión Azure Storage para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="e3ed2-122">Para obtener más información sobre las cadenas de conexión, consulte Configuración de las [cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="e3ed2-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="e3ed2-123">En el tutorial, escriba la cadena de conexión en el script, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="e3ed2-124">Sin embargo, esto **no se recomienda** para los proyectos reales.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="e3ed2-125">La clave de la cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="e3ed2-126">Siempre debe proteger la clave de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="e3ed2-127">Evite distribuirla a otros usuarios, codificarla de forma rígida o guardarla en un archivo de texto que sea accesible a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="e3ed2-128">Puede volver a generar la clave con el Azure Portal si cree que se ha puesto en peligro.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-128">You can regenerate your key using the Azure portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="e3ed2-129">En el caso de las aplicaciones reales, la mejor manera de mantener la cadena de conexión de almacenamiento se encuentra en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="e3ed2-130">Para capturar la cadena de conexión de un archivo de configuración, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="e3ed2-131">El uso del Administrador de configuración Azure es opcional.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="e3ed2-132">También puede usar una API, como el tipo de .NET Framework `ConfigurationManager` .</span><span class="sxs-lookup"><span data-stu-id="e3ed2-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="e3ed2-133">Análisis de la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="e3ed2-133">Parse the connection string</span></span>

<span data-ttu-id="e3ed2-134">Para analizar la cadena de conexión, use:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="e3ed2-135">Esto devuelve un `CloudStorageAccount` .</span><span class="sxs-lookup"><span data-stu-id="e3ed2-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="e3ed2-136">Crear algunos datos ficticios locales</span><span class="sxs-lookup"><span data-stu-id="e3ed2-136">Create some local dummy data</span></span>

<span data-ttu-id="e3ed2-137">Antes de empezar, cree algunos datos locales ficticios en el directorio del script.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="e3ed2-138">Más adelante se cargan estos datos.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="e3ed2-139">Creación del cliente de Blob service</span><span class="sxs-lookup"><span data-stu-id="e3ed2-139">Create the Blob service client</span></span>

<span data-ttu-id="e3ed2-140">El `CloudBlobClient` tipo permite recuperar contenedores y blobs almacenados en el almacenamiento de blobs.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="e3ed2-141">Esta es una forma de crear el cliente de servicio:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="e3ed2-142">Ahora ya puede escribir código que lee y escribe datos en el Almacenamiento de blobs.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="e3ed2-143">Crear un contenedor</span><span class="sxs-lookup"><span data-stu-id="e3ed2-143">Create a container</span></span>

<span data-ttu-id="e3ed2-144">En este ejemplo se muestra cómo crear un contenedor si todavía no existe:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="e3ed2-145">De manera predeterminada, el nuevo contenedor es privado, lo que significa que debe especificar su clave de acceso de almacenamiento para descargar blobs de él.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="e3ed2-146">Si desea poner los archivos del contenedor a disposición de todo el mundo, puede convertir el contenedor en público utilizando el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="e3ed2-147">Cualquier usuario de Internet puede ver los blobs de los contenedores públicos, pero solo es posible modificarlos o eliminarlos si se dispone de la clave de acceso apropiada o una firma de acceso compartido.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="e3ed2-148">Cargar un blob en un contenedor</span><span class="sxs-lookup"><span data-stu-id="e3ed2-148">Upload a blob into a container</span></span>

<span data-ttu-id="e3ed2-149">Azure Blob Storage admite blobs en bloques y en páginas.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="e3ed2-150">En la mayoría de los casos, un BLOB en bloques es el tipo recomendado que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="e3ed2-151">Para cargar un archivo en un blob en bloques, obtenga una referencia de contenedor y utilícela para obtener una referencia de blob en bloques.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="e3ed2-152">Una vez que tenga una referencia de BLOB, puede cargar cualquier secuencia de datos en ella llamando al `UploadFromFile` método.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="e3ed2-153">Esta operación crea el BLOB si no existía anteriormente, o lo sobrescribe si existe.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="e3ed2-154">Enumerar los blobs de un contenedor</span><span class="sxs-lookup"><span data-stu-id="e3ed2-154">List the blobs in a container</span></span>

<span data-ttu-id="e3ed2-155">Para enumerar los blobs de un contenedor, primero obtenga una referencia de contenedor.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="e3ed2-156">Después, puede usar el método del contenedor `ListBlobs` para recuperar los blobs o directorios que contiene.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="e3ed2-157">Para tener acceso al conjunto completo de propiedades y métodos de un devuelto `IListBlobItem` , debe convertirlo en `CloudBlockBlob` un `CloudPageBlob` objeto, o `CloudBlobDirectory` .</span><span class="sxs-lookup"><span data-stu-id="e3ed2-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="e3ed2-158">Si se desconoce el tipo, puede realizar una comprobación de tipo para determinar el formato al que se debe convertir.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="e3ed2-159">El código siguiente muestra cómo recuperar y consultar el URI de cada elemento del contenedor `mydata` :</span><span class="sxs-lookup"><span data-stu-id="e3ed2-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="e3ed2-160">También puede asignar nombres a los blobs con la información de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="e3ed2-161">De este modo crea una estructura de directorios virtuales que puede organizar y recorrer tal como lo haría en un sistema de archivos tradicional.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="e3ed2-162">La estructura de directorios es solo virtual: los únicos recursos disponibles en BLOB Storage son contenedores y BLOBs.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-162">The directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="e3ed2-163">Sin embargo, la biblioteca de cliente de almacenamiento ofrece un `CloudBlobDirectory` objeto para hacer referencia a un directorio virtual y simplificar el proceso de trabajar con blobs organizados de este modo.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="e3ed2-164">Por ejemplo, observe el siguiente conjunto de blobs en bloques incluidos en un contenedor denominado `photos`:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="e3ed2-165">*photo1.jpg*</span><span class="sxs-lookup"><span data-stu-id="e3ed2-165">*photo1.jpg*</span></span>\
<span data-ttu-id="e3ed2-166">*2015/arquitectura/description.txt*</span><span class="sxs-lookup"><span data-stu-id="e3ed2-166">*2015/architecture/description.txt*</span></span>\
<span data-ttu-id="e3ed2-167">*2015/arquitectura/photo3.jpg*</span><span class="sxs-lookup"><span data-stu-id="e3ed2-167">*2015/architecture/photo3.jpg*</span></span>\
<span data-ttu-id="e3ed2-168">*2015/arquitectura/photo4.jpg*</span><span class="sxs-lookup"><span data-stu-id="e3ed2-168">*2015/architecture/photo4.jpg*</span></span>\
<span data-ttu-id="e3ed2-169">*2016/arquitectura/photo5.jpg*</span><span class="sxs-lookup"><span data-stu-id="e3ed2-169">*2016/architecture/photo5.jpg*</span></span>\
<span data-ttu-id="e3ed2-170">*2016/arquitectura/photo6.jpg*</span><span class="sxs-lookup"><span data-stu-id="e3ed2-170">*2016/architecture/photo6.jpg*</span></span>\
<span data-ttu-id="e3ed2-171">*2016/arquitectura/description.txt*</span><span class="sxs-lookup"><span data-stu-id="e3ed2-171">*2016/architecture/description.txt*</span></span>\
<span data-ttu-id="e3ed2-172">*2016/photo7.jpg*</span><span class="sxs-lookup"><span data-stu-id="e3ed2-172">*2016/photo7.jpg*</span></span>\

<span data-ttu-id="e3ed2-173">Cuando se llama a `ListBlobs` en un contenedor (como en el ejemplo anterior), se devuelve una lista jerárquica.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-173">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="e3ed2-174">Si contiene `CloudBlobDirectory` `CloudBlockBlob` objetos y, que representan los directorios y los blobs del contenedor, respectivamente, la salida resultante tendrá un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-174">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="e3ed2-175">Opcionalmente, puede establecer el `UseFlatBlobListing` parámetro del `ListBlobs` método en `true` .</span><span class="sxs-lookup"><span data-stu-id="e3ed2-175">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="e3ed2-176">En este caso, cada BLOB del contenedor se devuelve como un `CloudBlockBlob` objeto.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-176">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="e3ed2-177">La llamada a `ListBlobs` para devolver una lista plana tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-177">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="e3ed2-178">y, en función del contenido actual del contenedor, los resultados son similares a los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-178">and, depending on the current contents of your container, the results look like this:</span></span>

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

## <a name="download-blobs"></a><span data-ttu-id="e3ed2-179">Descargar blobs</span><span class="sxs-lookup"><span data-stu-id="e3ed2-179">Download blobs</span></span>

<span data-ttu-id="e3ed2-180">Para descargar blobs, primero recupere una referencia de BLOB y, a continuación, llame al `DownloadToStream` método.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-180">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="e3ed2-181">En el ejemplo siguiente se usa el `DownloadToStream` método para transferir el contenido del BLOB a un objeto de secuencia que se puede guardar en un archivo local.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-181">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="e3ed2-182">También puede usar el `DownloadToStream` método para descargar el contenido de un BLOB como una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-182">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="e3ed2-183">Eliminar blobs</span><span class="sxs-lookup"><span data-stu-id="e3ed2-183">Delete blobs</span></span>

<span data-ttu-id="e3ed2-184">Para eliminar un BLOB, primero obtenga una referencia de BLOB y, a continuación, llame al `Delete` método en ella.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-184">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="e3ed2-185">Enumerar blobs en páginas de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="e3ed2-185">List blobs in pages asynchronously</span></span>

<span data-ttu-id="e3ed2-186">Si enumera un gran número de blobs o desea controlar el número de resultados que devuelve en una operación de listado, puede enumerar blobs en páginas de resultados.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-186">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="e3ed2-187">En este ejemplo se muestra cómo devolver resultados en páginas asincrónicamente de forma que la ejecución no se bloquee mientras se espera a devolver un conjunto grande de resultados.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-187">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="e3ed2-188">En este ejemplo se muestra una lista plana de blobs, pero también puede realizar una lista jerárquica estableciendo el `useFlatBlobListing` parámetro del `ListBlobsSegmentedAsync` método en `false` .</span><span class="sxs-lookup"><span data-stu-id="e3ed2-188">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="e3ed2-189">En el ejemplo se define un método asincrónico, mediante un `async` bloque.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-189">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="e3ed2-190">La ``let!`` palabra clave suspende la ejecución del método de ejemplo hasta que se completa la tarea de lista.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-190">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="e3ed2-191">Ahora podemos usar esta rutina asincrónica como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-191">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="e3ed2-192">En primer lugar, cargue algunos datos ficticios (mediante el archivo local creado anteriormente en este tutorial).</span><span class="sxs-lookup"><span data-stu-id="e3ed2-192">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="e3ed2-193">Ahora, llame a la rutina.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-193">Now, call the routine.</span></span> <span data-ttu-id="e3ed2-194">Se usa `Async.RunSynchronously` para forzar la ejecución de la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-194">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="e3ed2-195">Escritura en un blob en anexos</span><span class="sxs-lookup"><span data-stu-id="e3ed2-195">Writing to an append blob</span></span>

<span data-ttu-id="e3ed2-196">Un blob en anexos se optimiza para las operaciones de anexado, como el registro.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-196">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="e3ed2-197">Al igual que un BLOB en bloques, un BLOB en anexos se compone de bloques, pero al agregar un nuevo bloque a un BLOB en anexos, siempre se anexa al final del BLOB.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-197">Like a block blob, an append blob is composed of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="e3ed2-198">No se puede actualizar o eliminar un bloque existente en un blob en anexos.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-198">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="e3ed2-199">Los identificadores de bloque para un blob en anexos no está expuestos como lo están en el caso de los blobs en bloques.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-199">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="e3ed2-200">Cada bloque en un blob en anexos puede tener un tamaño diferente, hasta un máximo de 4 MB y el blob puede incluir un máximo de 50.000 bloques.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-200">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="e3ed2-201">El tamaño máximo de un blob en anexos es, por tanto, ligeramente superior a 195 GB (4 MB X 50.000 bloques).</span><span class="sxs-lookup"><span data-stu-id="e3ed2-201">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="e3ed2-202">En el ejemplo siguiente se crea un nuevo BLOB en anexos y se anexan algunos datos, simulando una operación de registro simple.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-202">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="e3ed2-203">Consulte [Descripción Blobs en bloques, en anexos y en páginas](/rest/api/storageservices/Understanding-Block-Blobs--Append-Blobs--and-Page-Blobs) para obtener más información acerca de las diferencias entre los tres tipos de blobs.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-203">See [Understanding Block Blobs, Page Blobs, and Append Blobs](/rest/api/storageservices/Understanding-Block-Blobs--Append-Blobs--and-Page-Blobs) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="e3ed2-204">simultáneo</span><span class="sxs-lookup"><span data-stu-id="e3ed2-204">Concurrent access</span></span>

<span data-ttu-id="e3ed2-205">Para permitir el acceso simultáneo a un blob desde varios clientes o varias instancias de proceso, puede usar etiquetas **ETag** o **concesiones**.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-205">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

- <span data-ttu-id="e3ed2-206">**Etag** : proporciona una manera de detectar que otro proceso ha modificado el blob o el contenedor</span><span class="sxs-lookup"><span data-stu-id="e3ed2-206">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

- <span data-ttu-id="e3ed2-207">**Concesión** : proporciona una manera de obtener acceso exclusivo, renovable, de escritura o de eliminación a un BLOB durante un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-207">**Lease** - provides a way to obtain exclusive, renewable, write, or delete access to a blob for a period of time</span></span>

<span data-ttu-id="e3ed2-208">Para obtener más información, vea [administrar la simultaneidad en Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span><span class="sxs-lookup"><span data-stu-id="e3ed2-208">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="e3ed2-209">Nomenclatura de contenedores</span><span class="sxs-lookup"><span data-stu-id="e3ed2-209">Naming containers</span></span>

<span data-ttu-id="e3ed2-210">Cada blob del almacenamiento de Azure debe residir en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-210">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="e3ed2-211">El contenedor forma parte del nombre del blob.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-211">The container forms part of the blob name.</span></span> <span data-ttu-id="e3ed2-212">Por ejemplo, `mydata` es el nombre del contenedor de estos URI de blob de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-212">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

- `https://storagesample.blob.core.windows.net/mydata/blob1.txt`
- `https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg`

<span data-ttu-id="e3ed2-213">Un nombre de contenedor debe ser un nombre DNS válido y cumplir las reglas de nomenclatura siguientes:</span><span class="sxs-lookup"><span data-stu-id="e3ed2-213">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="e3ed2-214">Los nombres de contenedor deben comenzar por una letra o un número, y pueden contener solo letras, números y el carácter de guión (-).</span><span class="sxs-lookup"><span data-stu-id="e3ed2-214">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="e3ed2-215">Todos los caracteres de guión (-) deben estar inmediatamente precedidos y seguidos por una letra o un número; no se permiten guiones consecutivos en nombres de contenedor.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-215">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="e3ed2-216">Todas las letras del nombre de un contenedor deben aparecer en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-216">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="e3ed2-217">Los nombres de contenedor deben tener entre 3 y 63 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-217">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="e3ed2-218">El nombre de un contenedor siempre debe estar en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-218">The name of a container must always be lowercase.</span></span> <span data-ttu-id="e3ed2-219">Si se incluye una letra mayúscula en un nombre de contenedor o se infringe de algún otro modo las reglas de nomenclatura de contenedores, recibirá un error 400 (solicitud incorrecta).</span><span class="sxs-lookup"><span data-stu-id="e3ed2-219">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="e3ed2-220">Administración de la seguridad para blobs</span><span class="sxs-lookup"><span data-stu-id="e3ed2-220">Managing security for blobs</span></span>

<span data-ttu-id="e3ed2-221">De forma predeterminada, Azure Storage protege sus datos al limitar el acceso al propietario de la cuenta, quien está en posesión de las claves de acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-221">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="e3ed2-222">Cuando necesite compartir datos Blob en su cuenta de almacenamiento, es importante hacerlo sin poner en peligro la seguridad de las claves de acceso de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-222">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="e3ed2-223">Además, puede cifrar los datos Blob para cerciorarse de que es seguro pasar por la red y Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-223">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="e3ed2-224">Control del acceso a datos Blob</span><span class="sxs-lookup"><span data-stu-id="e3ed2-224">Controlling access to blob data</span></span>

<span data-ttu-id="e3ed2-225">De forma predeterminada, los datos Blob de su cuenta de almacenamiento solo son accesibles para el propietario de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-225">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="e3ed2-226">Para autenticar las solicitudes en el Almacenamiento de blobs, se necesita la clave de acceso de la cuenta de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-226">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="e3ed2-227">Sin embargo, es posible que desee poner determinados datos de BLOB a disposición de otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-227">However, you might want to make certain blob data available to other users.</span></span>

### <a name="encrypting-blob-data"></a><span data-ttu-id="e3ed2-228">Cifrado de datos Blob</span><span class="sxs-lookup"><span data-stu-id="e3ed2-228">Encrypting blob data</span></span>

<span data-ttu-id="e3ed2-229">Azure Storage admite el cifrado de datos de BLOB tanto en el cliente como en el servidor.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-229">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e3ed2-230">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="e3ed2-230">Next steps</span></span>

<span data-ttu-id="e3ed2-231">Ahora que está familiarizado con los aspectos básicos del Almacenamiento de blobs, siga estos vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-231">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="e3ed2-232">Herramientas</span><span class="sxs-lookup"><span data-stu-id="e3ed2-232">Tools</span></span>

- <span data-ttu-id="e3ed2-233">[AzureStorageTypeProvider F #](https://fsprojects.github.io/AzureStorageTypeProvider/)</span><span class="sxs-lookup"><span data-stu-id="e3ed2-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)</span></span>\
<span data-ttu-id="e3ed2-234">Un proveedor de tipo de F # que se puede usar para explorar los recursos de Azure Storage de blobs, tablas y colas, y para aplicar fácilmente operaciones CRUD en ellos.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-234">An F# Type Provider that can be used to explore Blob, Table, and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>

- <span data-ttu-id="e3ed2-235">[FSharp. Azure. Storage](https://github.com/fsprojects/FSharp.Azure.Storage)</span><span class="sxs-lookup"><span data-stu-id="e3ed2-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)</span></span>\
<span data-ttu-id="e3ed2-236">Una API de F # para usar Microsoft Azure servicio Table Storage</span><span class="sxs-lookup"><span data-stu-id="e3ed2-236">An F# API for using Microsoft Azure Table Storage service</span></span>

- <span data-ttu-id="e3ed2-237">[Explorador de Microsoft Azure Storage (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="e3ed2-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)</span></span>\
<span data-ttu-id="e3ed2-238">Una aplicación independiente y gratuita de Microsoft que le permite trabajar visualmente con datos de Azure Storage en Windows, OS X y Linux.</span><span class="sxs-lookup"><span data-stu-id="e3ed2-238">A free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="e3ed2-239">Referencia de Almacenamiento de blobs</span><span class="sxs-lookup"><span data-stu-id="e3ed2-239">Blob storage reference</span></span>

- [<span data-ttu-id="e3ed2-240">API de Azure Storage para .NET</span><span class="sxs-lookup"><span data-stu-id="e3ed2-240">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- <span data-ttu-id="e3ed2-241">[Azure Storage Services REST API Reference](/rest/api/storageservices/) (Referencia de la API REST de los servicios de Azure Storage)</span><span class="sxs-lookup"><span data-stu-id="e3ed2-241">[Azure Storage Services REST API Reference](/rest/api/storageservices/)</span></span>

### <a name="related-guides"></a><span data-ttu-id="e3ed2-242">Guías relacionadas</span><span class="sxs-lookup"><span data-stu-id="e3ed2-242">Related guides</span></span>

- <span data-ttu-id="e3ed2-243">[Azure Blob Storage Samples for .NET](/samples/azure-samples/storage-blob-dotnet-getting-started/storage-blob-dotnet-getting-started/) (Ejemplos de Azure Blob Storage para .NET)</span><span class="sxs-lookup"><span data-stu-id="e3ed2-243">[Azure Blob Storage Samples for .NET](/samples/azure-samples/storage-blob-dotnet-getting-started/storage-blob-dotnet-getting-started/)</span></span>
- [<span data-ttu-id="e3ed2-244">Introducción a AzCopy</span><span class="sxs-lookup"><span data-stu-id="e3ed2-244">Get started with AzCopy</span></span>](/azure/storage/common/storage-use-azcopy-v10)
- [<span data-ttu-id="e3ed2-245">Configuración de las cadenas de conexión de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="e3ed2-245">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="e3ed2-246">Blog del equipo de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="e3ed2-246">Azure Storage Team Blog</span></span>](/archive/blogs/windowsazurestorage/)
- [<span data-ttu-id="e3ed2-247">Guía de inicio rápido: Uso de .NET para crear un blob en el almacenamiento de objetos</span><span class="sxs-lookup"><span data-stu-id="e3ed2-247">Quickstart: Use .NET to create a blob in object storage</span></span>](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
