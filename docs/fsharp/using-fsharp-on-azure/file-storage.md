---
title: 'Introducción a Azure File storage mediante F #'
description: Store los datos de archivos en la nube con Azure File storage y montar un recurso compartido de archivos de nube desde una máquina virtual (VM) de Azure o desde una aplicación local que ejecute Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: e772da5f81d2e6827295d0dfe150934a415eb3bb
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "33569348"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Introducción a Azure File storage mediante F # #

Azure File storage es un servicio que ofrece recursos compartidos de archivos en la nube mediante el estándar [protocolo bloque de mensajes del servidor (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx). Se admiten SMB 2.1 y SMB 3.0. Con Azure File storage, puede migrar aplicaciones heredadas que se basan en recursos compartidos de archivos en Azure rápidamente y sin necesidad de costosas reescrituras. Aplicaciones que se ejecutan en máquinas virtuales de Azure o servicios en la nube o desde clientes locales pueden montar un recurso compartido de archivos en la nube, igual que una aplicación de escritorio monta un recurso compartido SMB típico. Cualquier número de componentes de la aplicación puede montar y acceder simultáneamente el recurso compartido de File storage.

Para obtener una introducción conceptual de almacenamiento de archivos, consulte [la Guía de .NET para file storage](/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Requisitos previos

Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).
También necesitará la clave de acceso de almacenamiento para esta cuenta.

## <a name="create-an-f-script-and-start-f-interactive"></a>Crear un Script de F # y el inicio de F # Interactive

Los ejemplos de este artículo pueden usarse en una aplicación de F # o un script de F #. Para crear un script de F #, cree un archivo con el `.fsx` extensión, por ejemplo `files.fsx`, en el entorno de desarrollo de F #.

A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` paquete y referencia `WindowsAzure.Storage.dll` en el script mediante un `#r`directiva.

### <a name="add-namespace-declarations"></a>Agregue las declaraciones de espacio de nombres

Agregue el siguiente `open` instrucciones a la parte superior de la `files.fsx` archivo:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Obtener la cadena de conexión

Necesitará una cadena de conexión de Azure Storage para este tutorial. Para obtener más información acerca de las cadenas de conexión, consulte [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).

Para este tutorial, deberá escribir la cadena de conexión en el script, similar al siguiente:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Sin embargo, esto es **no recomienda** proyectos reales. La clave de cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento. Siempre debe proteger la clave de cuenta de almacenamiento. Evite distribuirla a otros usuarios, codificarla de forma o guardarlo en un archivo de texto sin formato que sea accesible a otros usuarios. Puede volver a generar la clave mediante Azure Portal si cree que puede verse comprometida.

Las aplicaciones para el real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración. Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Con el Administrador de configuración de Azure es opcional. También puede usar una API como .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizar la cadena de conexión

Para analizar la cadena de conexión, use:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Esto devolverá un `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Crear al cliente de servicios de archivo

El `CloudFileClient` tipo le permite usar mediante programación los archivos almacenados en almacenamiento de archivos. Aquí es una forma de crear al cliente del servicio:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Ahora está listo para escribir código que lee y escribe datos en almacenamiento de archivos.

## <a name="create-a-file-share"></a>Crear un recurso compartido de archivos

En este ejemplo se muestra cómo crear un recurso compartido de archivos si aún no existe:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Crear un directorio raíz y un subdirectorio

En este caso, obtendrá el directorio raíz y obtenga un subdirectorio de la raíz. Crear ambos si aún no existen.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Cargar texto como un archivo

En este ejemplo se muestra cómo cargar un archivo de texto.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Descargar un archivo en una copia local del archivo

Aquí se descargue el archivo que acaba de crear, anexar el contenido en un archivo local.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Establecer el tamaño máximo para un recurso compartido de archivos

El ejemplo siguiente muestra cómo comprobar el uso actual de un recurso compartido y cómo establecer la cuota para el recurso compartido. `FetchAttributes` debe llamarse para rellenar de un recurso compartido `Properties`, y `SetProperties` para propagar los cambios locales a Azure File storage.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generar una firma de acceso compartido para un archivo o recurso compartido de archivos

Puede generar una firma de acceso compartido (SAS) para un recurso compartido de archivos o para un archivo individual. También puede crear una directiva de acceso compartido en un recurso compartido de archivos para administrar firmas de acceso compartido. Se recomienda crear una directiva de acceso compartido, ya que proporciona un medio de revocar la SAS si debe estar en peligro.

En este caso, creará un compartido directiva en un recurso compartido de acceso y, a continuación, usar esa directiva para ofrecer las restricciones para una SAS en un archivo en el recurso compartido.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Para obtener más información sobre la creación y uso de firmas de acceso compartido, consulte [firmas de acceso compartido (SAS) utilizando](/azure/storage/storage-dotnet-shared-access-signature-part-1) y [creación y uso de una SAS con Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Copiar archivos

Puede copiar un archivo a otro archivo o en un blob o un blob en un archivo. Si va a copiar un blob en un archivo o un archivo en un blob, *debe* utilizar una firma de acceso compartido (SAS) para autenticar el objeto de origen, incluso si va a copiar en la misma cuenta de almacenamiento.

### <a name="copy-a-file-to-another-file"></a>Copiar un archivo en otro archivo

En este caso, copie un archivo a otro archivo en el mismo recurso compartido. Puesto que esta operación de copia copia entre archivos en la misma cuenta de almacenamiento, puede usar la autenticación de clave compartida para realizar la copia.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Copiar un archivo en un blob

En este caso, se crea un archivo y cópielo en un blob en la misma cuenta de almacenamiento. Crear una SAS para el archivo de origen, el servicio utiliza para autenticar el acceso al archivo de origen durante la operación de copia.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Puede copiar un blob en un archivo de la misma manera. Si el objeto de origen es un blob, a continuación, cree una SAS para autenticar el acceso a ese blob durante la operación de copia.

## <a name="troubleshooting-file-storage-using-metrics"></a>Solución de problemas de File storage mediante métricas

Análisis de Azure Storage admite métricas para File storage. Con datos de métricas, puede seguimiento de solicitudes y diagnosticar problemas.

Puede habilitar las métricas para File storage desde el [Portal de Azure](https://portal.azure.com), o puede hacerlo desde F# similar al siguiente:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Pasos siguientes

Consulte estos vínculos para obtener más información sobre Azure File storage.

### <a name="conceptual-articles-and-videos"></a>Artículos y vídeos conceptuales

- [Almacenamiento de Azure Files: una nube sin dificultades del sistema de archivos SMB para Windows y Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Cómo usar Azure File Storage con Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Compatibilidad con herramientas de almacenamiento de archivos

- [Uso de Azure PowerShell con Azure Storage](/azure/storage/storage-powershell-guide-full)
- [Uso de AzCopy con Microsoft Azure Storage](/azure/storage/storage-use-azcopy)
- [Uso de la CLI de Azure con Azure Storage](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Referencia

- [Biblioteca de cliente de almacenamiento para la referencia de .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Referencia de API de REST de servicios de archivo](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Entradas de blog

- [Azure File storage está ya disponible con carácter general](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Dentro de Azure File Storage](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [Introducción a servicios de archivo de Microsoft Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [Conexiones persistentes a Microsoft Azure Files](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
