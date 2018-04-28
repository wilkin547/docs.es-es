---
title: 'Introducción al almacenamiento de archivos de Azure con F #'
description: Almacenar datos de archivos en la nube con el almacenamiento de archivos de Azure y montar el recurso compartido de archivos de nube desde una máquina virtual (VM) de Azure o desde una aplicación local que ejecute Windows.
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: conceptual
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: f4eb02bc3e4aca0653a4fa991c1593f988f1d1af
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Introducción al almacenamiento de archivos de Azure con F # #

Almacenamiento de archivos de Azure es un servicio que ofrece el uso compartido de archivos en la nube mediante el estándar [protocolo de bloque de mensajes del servidor (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx). Se admiten SMB 2.1 y SMB 3.0. Con el almacenamiento de archivos de Azure, puede migrar las aplicaciones heredadas que se basan en recursos compartidos de archivos en Azure rápidamente y sin costosas de escribir de nuevo. Aplicaciones que se ejecutan en máquinas virtuales de Azure o servicios en la nube o de los clientes locales pueden montar un recurso compartido de archivos en la nube, tal y como una aplicación de escritorio monta un recurso compartido SMB típico. Cualquier número de componentes de la aplicación puede, a continuación, monte y tener acceso a recurso compartido de almacenamiento de archivos al mismo tiempo.

Para obtener información conceptual del almacenamiento de archivos, vea [la Guía de .NET para almacenar archivos](/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Requisitos previos

Para utilizar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).
También necesitará la clave de acceso de almacenamiento para esta cuenta.

## <a name="create-an-f-script-and-start-f-interactive"></a>Crear un Script de F # y el inicio de F # Interactive

Los ejemplos de este artículo pueden usarse en una aplicación de F # o un script de F #. Para crear un script de F #, cree un archivo con el `.fsx` extensión, por ejemplo `files.fsx`, en el entorno de desarrollo de F #.

A continuación, use un [el Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` paquete y referencia `WindowsAzure.Storage.dll` en el script mediante un `#r`directiva.

### <a name="add-namespace-declarations"></a>Agregue las declaraciones de espacio de nombres

Agregue el siguiente `open` instrucciones a la parte superior de la `files.fsx` archivo:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Obtener la cadena de conexión

Necesitará una cadena de conexión de almacenamiento de Azure para este tutorial. Para obtener más información acerca de las cadenas de conexión, vea [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).

Para el tutorial, especificará la cadena de conexión en el script, similar al siguiente:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Sin embargo, esto es **no recomienda** proyectos de una manera real. La clave de cuenta de almacenamiento es similar a la contraseña raíz para la cuenta de almacenamiento. Tenga siempre cuidado proteger la clave de cuenta de almacenamiento. Evitar la distribución a otros usuarios, codificar de forma rígida, o guardarlo en un archivo de texto sin formato sea accesible a otros usuarios. Puede volver a generar la clave mediante el Portal de Azure si cree que se han comprometido.

Las aplicaciones de una manera real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración. Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Con el Administrador de configuración de Azure es opcional. También puede utilizar una API como .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizar la cadena de conexión

Para analizar la cadena de conexión, use:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Esto devolverá una `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Crear al cliente de servicios de archivo

El `CloudFileClient` tipo le permite usar mediante programación los archivos almacenados en almacenamiento de archivos. Aquí es una manera de crear al cliente del servicio:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Ahora está listo para escribir código que lee datos de y escribe los datos al almacenamiento de archivos.

## <a name="create-a-file-share"></a>Crear un recurso compartido de archivos

En este ejemplo se muestra cómo crear un recurso compartido de archivos si aún no existe:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Crear un directorio raíz y un subdirectorio

En este caso, obtendrá el directorio raíz y obtener un subdirectorio de la raíz. Crear ambos si aún no existen.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Cargar texto como un archivo

Este ejemplo muestra cómo cargar un archivo de texto.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Descargar un archivo en una copia local del archivo

Aquí se descargue el archivo que acaba de crear, anexar el contenido a un archivo local.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Establecer el tamaño máximo para un recurso compartido de archivos

El ejemplo siguiente muestra cómo comprobar el uso actual de un recurso compartido y cómo establecer la cuota para el recurso compartido. `FetchAttributes` se debe llamar para rellenar de un recurso compartido `Properties`, y `SetProperties` para propagar los cambios locales al almacenamiento de archivos de Azure.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generar una firma de acceso compartido para un archivo o recurso compartido de archivos

Puede generar una firma de acceso compartido (SAS) para un recurso compartido de archivos o un archivo individual. También puede crear una directiva de acceso compartido en un recurso compartido de archivos para administrar firmas de acceso compartido. Se recomienda crear una directiva de acceso compartido, ya que proporciona un medio para revocar la SAS si debe estar en peligro.

En este caso, creará un compartido directiva en un recurso compartido de acceso y, a continuación, utilizar esa directiva para proporcionar las restricciones de una SAS en un archivo en el recurso compartido.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Para obtener más información sobre cómo crear y utilizar firmas de acceso compartido, consulte [firmas de acceso compartido (SAS) usando](/azure/storage/storage-dotnet-shared-access-signature-part-1) y [crear y usar una SAS con almacenamiento de blobs](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Copiar archivos

Puede copiar un archivo a otro archivo o a un blob o un blob en un archivo. Si va a copiar un blob en un archivo o un archivo en un blob se *debe* utilizar una firma de acceso compartido (SAS) para autenticar el objeto de origen, incluso si va a copiar en la misma cuenta de almacenamiento.

### <a name="copy-a-file-to-another-file"></a>Copiar un archivo en otro archivo

A continuación, copie un archivo a otro archivo en el mismo recurso compartido. Puesto que esta operación de copia copia entre archivos en la misma cuenta de almacenamiento, puede utilizar autenticación de clave compartida para realizar la copia.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Copiar un archivo en un blob

En este caso, se crea un archivo y cópielo en un blob en la misma cuenta de almacenamiento. Crear una SAS para el archivo de origen, que utiliza el servicio para autenticar el acceso al archivo de origen durante la operación de copia.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Puede copiar un blob en un archivo de la misma manera. Si el objeto de origen es un blob, a continuación, crear una SAS para autenticar el acceso a ese blob durante la operación de copia.

## <a name="troubleshooting-file-storage-using-metrics"></a>Usar las métricas de almacenamiento de archivos de solución de problemas

Análisis de almacenamiento de Azure admite las métricas para el almacenamiento de archivo. Con datos de métricas, puede las solicitudes de seguimiento y diagnosticar problemas.

Puede habilitar las métricas para almacenamiento de archivos de la [Portal de Azure](https://portal.azure.com), o puede hacerlo desde F # como el siguiente:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Pasos siguientes

Vea los siguientes vínculos para obtener más información sobre el almacenamiento de archivos de Azure.

### <a name="conceptual-articles-and-videos"></a>Vídeos y artículos conceptuales

- [Almacenamiento de archivos de Azure: una nube sin dificultades sistema de archivos SMB para Windows y Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Cómo utilizar el almacenamiento de archivos de Azure con Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Compatibilidad con herramientas de almacenamiento de archivos

- [Uso de PowerShell de Azure con el almacenamiento de Azure](/azure/storage/storage-powershell-guide-full)
- [Cómo usar AzCopy con almacenamiento de Microsoft Azure](/azure/storage/storage-use-azcopy)
- [Mediante la CLI de Azure con el almacenamiento de Azure](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Referencia

- [Biblioteca de cliente de almacenamiento para la referencia de .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Referencia de API de REST de servicios de archivo](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Entradas de blog

- [Almacenamiento de archivos de Azure ahora está disponible con carácter general](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Almacenamiento de archivos dentro de Azure](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [Introducción a servicios de archivo de Microsoft Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [Conexiones persistentes a archivos de Microsoft Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
