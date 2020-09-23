---
title: Introducción a Azure File Storage mediante F#
description: Almacene datos de archivo en la nube con el Almacenamiento de archivos de Azure y monte un recurso compartido de archivos de nube desde una máquina virtual (VM) de Azure o desde una aplicación local con Windows.
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: dd19b156e73774f4eca63afd3f4c10a4a7b8d46c
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100131"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="b192f-103">Introducción a Azure File Storage mediante F\#</span><span class="sxs-lookup"><span data-stu-id="b192f-103">Get started with Azure File storage using F\#</span></span>

<span data-ttu-id="b192f-104">Almacenamiento de archivos de Azure es un servicio que ofrece recursos compartidos de archivos en la nube mediante el [protocolo Bloque de mensajes del servidor (SMB)](/windows/win32/fileio/microsoft-smb-protocol-and-cifs-protocol-overview)estándar.</span><span class="sxs-lookup"><span data-stu-id="b192f-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](/windows/win32/fileio/microsoft-smb-protocol-and-cifs-protocol-overview).</span></span> <span data-ttu-id="b192f-105">Se admiten SMB 2.1 y SMB 3.0.</span><span class="sxs-lookup"><span data-stu-id="b192f-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="b192f-106">Con Almacenamiento de archivos de Azure puede migrar aplicaciones heredadas basadas en recursos compartidos de archivos a Azure con rapidez y sin necesidad de costosas reescrituras.</span><span class="sxs-lookup"><span data-stu-id="b192f-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="b192f-107">Las aplicaciones que se ejecutan en máquinas virtuales de Azure o en servicios en la nube o desde clientes locales pueden montar un recurso compartido de archivos en la nube, igual que una aplicación de escritorio monta un recurso compartido SMB típico.</span><span class="sxs-lookup"><span data-stu-id="b192f-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="b192f-108">Cualquier número de componentes de aplicación puede montar y acceder simultáneamente al recurso compartido de Almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="b192f-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="b192f-109">Para obtener información general conceptual sobre el almacenamiento de archivos, consulte [la guía de .net para el almacenamiento de archivos](/azure/storage/storage-dotnet-how-to-use-files).</span><span class="sxs-lookup"><span data-stu-id="b192f-109">For a conceptual overview of file storage, see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b192f-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="b192f-110">Prerequisites</span></span>

<span data-ttu-id="b192f-111">Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="b192f-111">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="b192f-112">También necesitará la clave de acceso de almacenamiento para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="b192f-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="b192f-113">Crear un script de F # e iniciar F# interactivo</span><span class="sxs-lookup"><span data-stu-id="b192f-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="b192f-114">Los ejemplos de este artículo se pueden usar en una aplicación de F # o en un script de F #.</span><span class="sxs-lookup"><span data-stu-id="b192f-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="b192f-115">Para crear un script de F #, cree un archivo con la `.fsx` extensión, por ejemplo `files.fsx` , en el entorno de desarrollo de f #.</span><span class="sxs-lookup"><span data-stu-id="b192f-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="b192f-116">A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` paquete y la referencia `WindowsAzure.Storage.dll` en el script mediante una `#r` Directiva.</span><span class="sxs-lookup"><span data-stu-id="b192f-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="b192f-117">Incorporación de declaraciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b192f-117">Add namespace declarations</span></span>

<span data-ttu-id="b192f-118">Agregue las siguientes instrucciones `open` en la parte superior del archivo `files.fsx`:</span><span class="sxs-lookup"><span data-stu-id="b192f-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="b192f-119">Obtención de la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="b192f-119">Get your connection string</span></span>

<span data-ttu-id="b192f-120">Necesitará una cadena de conexión Azure Storage para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="b192f-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="b192f-121">Para obtener más información sobre las cadenas de conexión, consulte Configuración de las [cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="b192f-121">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="b192f-122">En el tutorial, escribirá la cadena de conexión en el script, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b192f-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="b192f-123">Sin embargo, esto **no se recomienda** para los proyectos reales.</span><span class="sxs-lookup"><span data-stu-id="b192f-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="b192f-124">La clave de la cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b192f-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="b192f-125">Siempre debe proteger la clave de la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b192f-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="b192f-126">Evite distribuirla a otros usuarios, codificarla de forma rígida o guardarla en un archivo de texto que sea accesible a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="b192f-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="b192f-127">Puede volver a generar la clave con el Azure Portal si cree que se ha puesto en peligro.</span><span class="sxs-lookup"><span data-stu-id="b192f-127">You can regenerate your key using the Azure portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="b192f-128">En el caso de las aplicaciones reales, la mejor manera de mantener la cadena de conexión de almacenamiento se encuentra en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b192f-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="b192f-129">Para capturar la cadena de conexión de un archivo de configuración, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b192f-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="b192f-130">El uso del Administrador de configuración Azure es opcional.</span><span class="sxs-lookup"><span data-stu-id="b192f-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="b192f-131">También puede usar una API, como el tipo de .NET Framework `ConfigurationManager` .</span><span class="sxs-lookup"><span data-stu-id="b192f-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="b192f-132">Análisis de la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="b192f-132">Parse the connection string</span></span>

<span data-ttu-id="b192f-133">Para analizar la cadena de conexión, use:</span><span class="sxs-lookup"><span data-stu-id="b192f-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="b192f-134">Esto devolverá un `CloudStorageAccount` .</span><span class="sxs-lookup"><span data-stu-id="b192f-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="b192f-135">Crear el cliente del servicio de archivos</span><span class="sxs-lookup"><span data-stu-id="b192f-135">Create the File service client</span></span>

<span data-ttu-id="b192f-136">El `CloudFileClient` tipo permite usar mediante programación los archivos almacenados en el almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="b192f-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="b192f-137">Esta es una forma de crear el cliente de servicio:</span><span class="sxs-lookup"><span data-stu-id="b192f-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="b192f-138">Ahora está listo para escribir código que lee datos de y escribe datos en el almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="b192f-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="b192f-139">Creación de un recurso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="b192f-139">Create a file share</span></span>

<span data-ttu-id="b192f-140">En este ejemplo se muestra cómo crear un recurso compartido de archivos si aún no existe:</span><span class="sxs-lookup"><span data-stu-id="b192f-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="b192f-141">Crear un directorio raíz y un subdirectorio</span><span class="sxs-lookup"><span data-stu-id="b192f-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="b192f-142">Aquí se obtiene el directorio raíz y se obtiene un subdirectorio de la raíz.</span><span class="sxs-lookup"><span data-stu-id="b192f-142">Here, you get the root directory and get a subdirectory of the root.</span></span> <span data-ttu-id="b192f-143">Puede crear ambos si aún no existen.</span><span class="sxs-lookup"><span data-stu-id="b192f-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="b192f-144">Cargar texto como un archivo</span><span class="sxs-lookup"><span data-stu-id="b192f-144">Upload text as a file</span></span>

<span data-ttu-id="b192f-145">En este ejemplo se muestra cómo cargar texto como un archivo.</span><span class="sxs-lookup"><span data-stu-id="b192f-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="b192f-146">Descargar un archivo en una copia local del archivo</span><span class="sxs-lookup"><span data-stu-id="b192f-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="b192f-147">Aquí puede descargar el archivo que acaba de crear, anexando el contenido a un archivo local.</span><span class="sxs-lookup"><span data-stu-id="b192f-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="b192f-148">Establecer el tamaño máximo para un recurso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="b192f-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="b192f-149">En el ejemplo siguiente se muestra cómo comprobar el uso actual de un recurso compartido y cómo establecer la cuota para el recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="b192f-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="b192f-150">`FetchAttributes` se debe llamar a para rellenar un recurso compartido `Properties` y `SetProperties` propagar los cambios locales a Azure File Storage.</span><span class="sxs-lookup"><span data-stu-id="b192f-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="b192f-151">Generar una firma de acceso compartido para un archivo o recurso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="b192f-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="b192f-152">Puede generar una firma de acceso compartido (SAS) para un recurso compartido de archivos o para un archivo individual.</span><span class="sxs-lookup"><span data-stu-id="b192f-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="b192f-153">También puede crear una directiva de acceso compartido en un recurso compartido de archivos para administrar firmas de acceso compartido.</span><span class="sxs-lookup"><span data-stu-id="b192f-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="b192f-154">Se recomienda la creación de una directiva de acceso compartido, ya que ofrece un medio de revocar la SAS si esta se encuentra en peligro.</span><span class="sxs-lookup"><span data-stu-id="b192f-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="b192f-155">En este caso, se crea una directiva de acceso compartido en un recurso compartido y, a continuación, se usa esa Directiva para proporcionar las restricciones para una SAS en un archivo del recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="b192f-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="b192f-156">Para más información sobre la creación y el uso de firmas de acceso compartido, consulte [Uso de firmas de acceso compartido (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) y [Creación y uso de una SAS con Blob Storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span><span class="sxs-lookup"><span data-stu-id="b192f-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="b192f-157">Copiar archivos</span><span class="sxs-lookup"><span data-stu-id="b192f-157">Copy files</span></span>

<span data-ttu-id="b192f-158">Puede copiar un archivo en otro archivo o en un BLOB, o un BLOB en un archivo.</span><span class="sxs-lookup"><span data-stu-id="b192f-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="b192f-159">Si va a copiar un BLOB en un archivo, o un archivo en un BLOB, *debe* usar una firma de acceso compartido (SAS) para autenticar el objeto de origen, incluso si está copiando dentro de la misma cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b192f-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="b192f-160">Copiar un archivo en otro</span><span class="sxs-lookup"><span data-stu-id="b192f-160">Copy a file to another file</span></span>

<span data-ttu-id="b192f-161">Aquí, se copia un archivo en otro archivo en el mismo recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="b192f-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="b192f-162">Dado que en esta operación de copia se copia entre archivos de la misma cuenta de almacenamiento, puede usar la autenticación de clave compartida para realizar la copia.</span><span class="sxs-lookup"><span data-stu-id="b192f-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="b192f-163">Copiar un archivo en un blob</span><span class="sxs-lookup"><span data-stu-id="b192f-163">Copy a file to a blob</span></span>

<span data-ttu-id="b192f-164">Aquí se crea un archivo y se copia en un BLOB dentro de la misma cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="b192f-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="b192f-165">Puede crear una SAS para el archivo de código fuente, que el servicio utiliza para autenticar el acceso al archivo de origen durante la operación de copia.</span><span class="sxs-lookup"><span data-stu-id="b192f-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="b192f-166">Puede copiar un blob en un archivo de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="b192f-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="b192f-167">Si el objeto de origen es un blob, cree una SAS para autenticar el acceso a dicho blob durante la operación de copia.</span><span class="sxs-lookup"><span data-stu-id="b192f-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="b192f-168">Solución de problemas de almacenamiento de archivos mediante métricas</span><span class="sxs-lookup"><span data-stu-id="b192f-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="b192f-169">Azure Storage Analytics admite métricas para el almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="b192f-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="b192f-170">Con los datos de las métricas, es posible seguir paso a paso las solicitudes y diagnosticar problemas.</span><span class="sxs-lookup"><span data-stu-id="b192f-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="b192f-171">Puede habilitar las métricas para el almacenamiento de archivos desde el [Azure portal](https://portal.azure.com)o puede hacerlo desde F # de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b192f-171">You can enable metrics for File storage from the [Azure portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="b192f-172">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b192f-172">Next steps</span></span>

<span data-ttu-id="b192f-173">Para obtener más información sobre Azure File Storage, consulte estos vínculos.</span><span class="sxs-lookup"><span data-stu-id="b192f-173">For more information about Azure File storage, see these links.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="b192f-174">Artículos y vídeos conceptuales</span><span class="sxs-lookup"><span data-stu-id="b192f-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="b192f-175">Almacenamiento de archivos de Azure: un sistema de archivos SMB en la nube sin dificultades para Windows y Linux</span><span class="sxs-lookup"><span data-stu-id="b192f-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="b192f-176">Uso de Azure File Storage con Linux</span><span class="sxs-lookup"><span data-stu-id="b192f-176">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="b192f-177">Compatibilidad de herramientas con el almacenamiento de archivos</span><span class="sxs-lookup"><span data-stu-id="b192f-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="b192f-178">Usar Azure PowerShell con Azure Storage</span><span class="sxs-lookup"><span data-stu-id="b192f-178">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="b192f-179">Uso de AzCopy con Microsoft Azure Storage</span><span class="sxs-lookup"><span data-stu-id="b192f-179">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="b192f-180">Creación, descarga y enumeración de blobs mediante la CLI de Azure</span><span class="sxs-lookup"><span data-stu-id="b192f-180">Create, download, and list blobs with Azure CLI</span></span>](/azure/storage/blobs/storage-quickstart-blobs-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="b192f-181">Referencia</span><span class="sxs-lookup"><span data-stu-id="b192f-181">Reference</span></span>

- [<span data-ttu-id="b192f-182">Referencia de la biblioteca de clientes de almacenamiento para .NET</span><span class="sxs-lookup"><span data-stu-id="b192f-182">Storage Client Library for .NET reference</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="b192f-183">Referencia de la API REST del servicio de archivos</span><span class="sxs-lookup"><span data-stu-id="b192f-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="b192f-184">Publicaciones de blog</span><span class="sxs-lookup"><span data-stu-id="b192f-184">Blog posts</span></span>

- [<span data-ttu-id="b192f-185">El almacenamiento de archivos de Azure ya está disponible de manera general</span><span class="sxs-lookup"><span data-stu-id="b192f-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="b192f-186">Dentro de Azure File Storage</span><span class="sxs-lookup"><span data-stu-id="b192f-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [<span data-ttu-id="b192f-187">Introducing Microsoft Azure File Service (Introducción al servicio de archivos de Microsoft Azure)</span><span class="sxs-lookup"><span data-stu-id="b192f-187">Introducing Microsoft Azure File Service</span></span>](/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [<span data-ttu-id="b192f-188">Persisting connections to Microsoft Azure Files (Persistencia de conexiones en archivos de Microsoft Azure)</span><span class="sxs-lookup"><span data-stu-id="b192f-188">Persisting connections to Microsoft Azure Files</span></span>](/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
