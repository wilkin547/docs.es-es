---
title: "Introducción al almacenamiento de archivos de Azure con F #"
description: "Almacenar datos de archivos en la nube con el almacenamiento de archivos de Azure y montar el recurso compartido de archivos de nube desde una máquina virtual (VM) de Azure o desde una aplicación local que ejecute Windows."
keywords: "Visual f #, f #, funcional de programación,. NET, .NET Core, Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5c26a0aa-186e-476c-9f87-e0191754579e
ms.openlocfilehash: 66b2503744e9024deac3d6dabea57da4fd393bd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="10544-104">Introducción al almacenamiento de archivos de Azure con F #</span><span class="sxs-lookup"><span data-stu-id="10544-104">Get started with Azure File storage using F#</span></span> #

<span data-ttu-id="10544-105">Almacenamiento de archivos de Azure es un servicio que ofrece el uso compartido de archivos en la nube mediante el estándar [protocolo de bloque de mensajes del servidor (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span><span class="sxs-lookup"><span data-stu-id="10544-105">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="10544-106">Se admiten SMB 2.1 y SMB 3.0.</span><span class="sxs-lookup"><span data-stu-id="10544-106">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="10544-107">Con el almacenamiento de archivos de Azure, puede migrar las aplicaciones heredadas que se basan en recursos compartidos de archivos en Azure rápidamente y sin costosas de escribir de nuevo.</span><span class="sxs-lookup"><span data-stu-id="10544-107">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="10544-108">Aplicaciones que se ejecutan en máquinas virtuales de Azure o servicios en la nube o de los clientes locales pueden montar un recurso compartido de archivos en la nube, tal y como una aplicación de escritorio monta un recurso compartido SMB típico.</span><span class="sxs-lookup"><span data-stu-id="10544-108">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="10544-109">Cualquier número de componentes de la aplicación puede, a continuación, monte y tener acceso a recurso compartido de almacenamiento de archivos al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="10544-109">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="10544-110">Para obtener información conceptual del almacenamiento de archivos, vea [la Guía de .NET para almacenar archivos](/azure/storage/storage-dotnet-how-to-use-files).</span><span class="sxs-lookup"><span data-stu-id="10544-110">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="10544-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="10544-111">Prerequisites</span></span>

<span data-ttu-id="10544-112">Para utilizar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="10544-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="10544-113">También necesitará la clave de acceso de almacenamiento para esta cuenta.</span><span class="sxs-lookup"><span data-stu-id="10544-113">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="10544-114">Crear un Script de F # y el inicio de F # Interactive</span><span class="sxs-lookup"><span data-stu-id="10544-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="10544-115">Los ejemplos de este artículo pueden usarse en una aplicación de F # o un script de F #.</span><span class="sxs-lookup"><span data-stu-id="10544-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="10544-116">Para crear un script de F #, cree un archivo con el `.fsx` extensión, por ejemplo `files.fsx`, en el entorno de desarrollo de F #.</span><span class="sxs-lookup"><span data-stu-id="10544-116">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="10544-117">A continuación, use un [el Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` paquete y referencia `WindowsAzure.Storage.dll` en el script mediante un `#r`directiva.</span><span class="sxs-lookup"><span data-stu-id="10544-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="10544-118">Agregue las declaraciones de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="10544-118">Add namespace declarations</span></span>

<span data-ttu-id="10544-119">Agregue el siguiente `open` instrucciones a la parte superior de la `files.fsx` archivo:</span><span class="sxs-lookup"><span data-stu-id="10544-119">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="10544-120">Obtener la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="10544-120">Get your connection string</span></span>

<span data-ttu-id="10544-121">Necesitará una cadena de conexión de almacenamiento de Azure para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="10544-121">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="10544-122">Para obtener más información acerca de las cadenas de conexión, vea [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="10544-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="10544-123">Para el tutorial, especificará la cadena de conexión en el script, similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="10544-123">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="10544-124">Sin embargo, esto es **no recomienda** proyectos de una manera real.</span><span class="sxs-lookup"><span data-stu-id="10544-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="10544-125">La clave de cuenta de almacenamiento es similar a la contraseña raíz para la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="10544-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="10544-126">Tenga siempre cuidado proteger la clave de cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="10544-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="10544-127">Evitar la distribución a otros usuarios, codificar de forma rígida, o guardarlo en un archivo de texto sin formato sea accesible a otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="10544-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="10544-128">Puede volver a generar la clave mediante el Portal de Azure si cree que se han comprometido.</span><span class="sxs-lookup"><span data-stu-id="10544-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="10544-129">Las aplicaciones de una manera real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="10544-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="10544-130">Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:</span><span class="sxs-lookup"><span data-stu-id="10544-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="10544-131">Con el Administrador de configuración de Azure es opcional.</span><span class="sxs-lookup"><span data-stu-id="10544-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="10544-132">También puede utilizar una API como .NET Framework `ConfigurationManager` tipo.</span><span class="sxs-lookup"><span data-stu-id="10544-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="10544-133">Analizar la cadena de conexión</span><span class="sxs-lookup"><span data-stu-id="10544-133">Parse the connection string</span></span>

<span data-ttu-id="10544-134">Para analizar la cadena de conexión, use:</span><span class="sxs-lookup"><span data-stu-id="10544-134">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="10544-135">Esto devolverá una `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="10544-135">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="10544-136">Crear al cliente de servicios de archivo</span><span class="sxs-lookup"><span data-stu-id="10544-136">Create the File service client</span></span>

<span data-ttu-id="10544-137">El `CloudFileClient` tipo le permite usar mediante programación los archivos almacenados en almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="10544-137">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="10544-138">Aquí es una manera de crear al cliente del servicio:</span><span class="sxs-lookup"><span data-stu-id="10544-138">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="10544-139">Ahora está listo para escribir código que lee datos de y escribe los datos al almacenamiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="10544-139">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="10544-140">Crear un recurso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="10544-140">Create a file share</span></span>

<span data-ttu-id="10544-141">En este ejemplo se muestra cómo crear un recurso compartido de archivos si aún no existe:</span><span class="sxs-lookup"><span data-stu-id="10544-141">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="10544-142">Crear un directorio raíz y un subdirectorio</span><span class="sxs-lookup"><span data-stu-id="10544-142">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="10544-143">En este caso, obtendrá el directorio raíz y obtener un subdirectorio de la raíz.</span><span class="sxs-lookup"><span data-stu-id="10544-143">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="10544-144">Crear ambos si aún no existen.</span><span class="sxs-lookup"><span data-stu-id="10544-144">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="10544-145">Cargar texto como un archivo</span><span class="sxs-lookup"><span data-stu-id="10544-145">Upload text as a file</span></span>

<span data-ttu-id="10544-146">Este ejemplo muestra cómo cargar un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="10544-146">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="10544-147">Descargar un archivo en una copia local del archivo</span><span class="sxs-lookup"><span data-stu-id="10544-147">Download a file to a local copy of the file</span></span>

<span data-ttu-id="10544-148">Aquí se descargue el archivo que acaba de crear, anexar el contenido a un archivo local.</span><span class="sxs-lookup"><span data-stu-id="10544-148">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="10544-149">Establecer el tamaño máximo para un recurso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="10544-149">Set the maximum size for a file share</span></span>

<span data-ttu-id="10544-150">El ejemplo siguiente muestra cómo comprobar el uso actual de un recurso compartido y cómo establecer la cuota para el recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="10544-150">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="10544-151">`FetchAttributes`se debe llamar para rellenar de un recurso compartido `Properties`, y `SetProperties` para propagar los cambios locales al almacenamiento de archivos de Azure.</span><span class="sxs-lookup"><span data-stu-id="10544-151">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="10544-152">Generar una firma de acceso compartido para un archivo o recurso compartido de archivos</span><span class="sxs-lookup"><span data-stu-id="10544-152">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="10544-153">Puede generar una firma de acceso compartido (SAS) para un recurso compartido de archivos o un archivo individual.</span><span class="sxs-lookup"><span data-stu-id="10544-153">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="10544-154">También puede crear una directiva de acceso compartido en un recurso compartido de archivos para administrar firmas de acceso compartido.</span><span class="sxs-lookup"><span data-stu-id="10544-154">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="10544-155">Se recomienda crear una directiva de acceso compartido, ya que proporciona un medio para revocar la SAS si debe estar en peligro.</span><span class="sxs-lookup"><span data-stu-id="10544-155">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="10544-156">En este caso, creará un compartido directiva en un recurso compartido de acceso y, a continuación, utilizar esa directiva para proporcionar las restricciones de una SAS en un archivo en el recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="10544-156">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="10544-157">Para obtener más información sobre cómo crear y utilizar firmas de acceso compartido, consulte [firmas de acceso compartido (SAS) usando](/azure/storage/storage-dotnet-shared-access-signature-part-1) y [crear y usar una SAS con almacenamiento de blobs](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span><span class="sxs-lookup"><span data-stu-id="10544-157">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="10544-158">Copiar archivos</span><span class="sxs-lookup"><span data-stu-id="10544-158">Copy files</span></span>

<span data-ttu-id="10544-159">Puede copiar un archivo a otro archivo o a un blob o un blob en un archivo.</span><span class="sxs-lookup"><span data-stu-id="10544-159">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="10544-160">Si va a copiar un blob en un archivo o un archivo en un blob se *debe* utilizar una firma de acceso compartido (SAS) para autenticar el objeto de origen, incluso si va a copiar en la misma cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="10544-160">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="10544-161">Copiar un archivo en otro archivo</span><span class="sxs-lookup"><span data-stu-id="10544-161">Copy a file to another file</span></span>

<span data-ttu-id="10544-162">A continuación, copie un archivo a otro archivo en el mismo recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="10544-162">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="10544-163">Puesto que esta operación de copia copia entre archivos en la misma cuenta de almacenamiento, puede utilizar autenticación de clave compartida para realizar la copia.</span><span class="sxs-lookup"><span data-stu-id="10544-163">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="10544-164">Copiar un archivo en un blob</span><span class="sxs-lookup"><span data-stu-id="10544-164">Copy a file to a blob</span></span>

<span data-ttu-id="10544-165">En este caso, se crea un archivo y cópielo en un blob en la misma cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="10544-165">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="10544-166">Crear una SAS para el archivo de origen, que utiliza el servicio para autenticar el acceso al archivo de origen durante la operación de copia.</span><span class="sxs-lookup"><span data-stu-id="10544-166">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="10544-167">Puede copiar un blob en un archivo de la misma manera.</span><span class="sxs-lookup"><span data-stu-id="10544-167">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="10544-168">Si el objeto de origen es un blob, a continuación, crear una SAS para autenticar el acceso a ese blob durante la operación de copia.</span><span class="sxs-lookup"><span data-stu-id="10544-168">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="10544-169">Usar las métricas de almacenamiento de archivos de solución de problemas</span><span class="sxs-lookup"><span data-stu-id="10544-169">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="10544-170">Análisis de almacenamiento de Azure admite las métricas para el almacenamiento de archivo.</span><span class="sxs-lookup"><span data-stu-id="10544-170">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="10544-171">Con datos de métricas, puede las solicitudes de seguimiento y diagnosticar problemas.</span><span class="sxs-lookup"><span data-stu-id="10544-171">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="10544-172">Puede habilitar las métricas para almacenamiento de archivos de la [Portal de Azure](https://portal.azure.com), o puede hacerlo desde F # como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="10544-172">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="10544-173">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="10544-173">Next steps</span></span>

<span data-ttu-id="10544-174">Vea los siguientes vínculos para obtener más información sobre el almacenamiento de archivos de Azure.</span><span class="sxs-lookup"><span data-stu-id="10544-174">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="10544-175">Vídeos y artículos conceptuales</span><span class="sxs-lookup"><span data-stu-id="10544-175">Conceptual articles and videos</span></span>

- [<span data-ttu-id="10544-176">Almacenamiento de archivos de Azure: una nube sin dificultades sistema de archivos SMB para Windows y Linux</span><span class="sxs-lookup"><span data-stu-id="10544-176">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="10544-177">Cómo utilizar el almacenamiento de archivos de Azure con Linux</span><span class="sxs-lookup"><span data-stu-id="10544-177">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="10544-178">Compatibilidad con herramientas de almacenamiento de archivos</span><span class="sxs-lookup"><span data-stu-id="10544-178">Tooling support for File storage</span></span>

- [<span data-ttu-id="10544-179">Uso de PowerShell de Azure con el almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="10544-179">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="10544-180">Cómo usar AzCopy con almacenamiento de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="10544-180">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="10544-181">Mediante la CLI de Azure con el almacenamiento de Azure</span><span class="sxs-lookup"><span data-stu-id="10544-181">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="10544-182">Referencia</span><span class="sxs-lookup"><span data-stu-id="10544-182">Reference</span></span>

- [<span data-ttu-id="10544-183">Biblioteca de cliente de almacenamiento para la referencia de .NET</span><span class="sxs-lookup"><span data-stu-id="10544-183">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="10544-184">Referencia de API de REST de servicios de archivo</span><span class="sxs-lookup"><span data-stu-id="10544-184">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="10544-185">Entradas de blog</span><span class="sxs-lookup"><span data-stu-id="10544-185">Blog posts</span></span>

- [<span data-ttu-id="10544-186">Almacenamiento de archivos de Azure ahora está disponible con carácter general</span><span class="sxs-lookup"><span data-stu-id="10544-186">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="10544-187">Almacenamiento de archivos dentro de Azure</span><span class="sxs-lookup"><span data-stu-id="10544-187">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [<span data-ttu-id="10544-188">Introducción a servicios de archivo de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="10544-188">Introducing Microsoft Azure File Service</span></span>](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/05/12/introducing-microsoft-azure-file-service.aspx)
- [<span data-ttu-id="10544-189">Conexiones persistentes a archivos de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="10544-189">Persisting connections to Microsoft Azure Files</span></span>](http://blogs.msdn.com/b/windowsazurestorage/archive/2014/05/27/persisting-connections-to-microsoft-azure-files.aspx)
