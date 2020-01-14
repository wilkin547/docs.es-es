---
title: Introducción a Azure File Storage mediante F#
description: Almacene datos de archivo en la nube con el Almacenamiento de archivos de Azure y monte un recurso compartido de archivos de nube desde una máquina virtual (VM) de Azure o desde una aplicación local con Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: d58417e1e3161b958754e01423136a9cdd6a08a6
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935628"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Introducción a Azure File Storage mediante F\#

Almacenamiento de archivos de Azure es un servicio que ofrece recursos compartidos de archivos en la nube mediante el [protocolo Bloque de mensajes del servidor (SMB)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)estándar. Se admiten SMB 2.1 y SMB 3.0. Con Almacenamiento de archivos de Azure puede migrar aplicaciones heredadas basadas en recursos compartidos de archivos a Azure con rapidez y sin necesidad de costosas reescrituras. Las aplicaciones que se ejecutan en máquinas virtuales de Azure o en servicios en la nube o desde clientes locales pueden montar un recurso compartido de archivos en la nube, igual que una aplicación de escritorio monta un recurso compartido SMB típico. Cualquier número de componentes de aplicación puede montar y acceder simultáneamente al recurso compartido de Almacenamiento de archivos.

Para obtener información general conceptual sobre el almacenamiento de archivos, consulte [la guía de .net para el almacenamiento de archivos](/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Requisitos previos

Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account).
También necesitará la clave de acceso de almacenamiento para esta cuenta.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creación de F# un script e F# Inicio interactivo

Los ejemplos de este artículo se pueden usar en una F# aplicación o en un F# script. Para crear un F# script, cree un archivo con la extensión `.fsx`, por ejemplo `files.fsx`, en el F# entorno de desarrollo.

A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el paquete `WindowsAzure.Storage` y haga referencia `WindowsAzure.Storage.dll` en el script mediante una directiva `#r`.

### <a name="add-namespace-declarations"></a>Agregar declaraciones de espacios de nombres

Agregue las siguientes instrucciones `open` en la parte superior del archivo `files.fsx`:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Obtención de la cadena de conexión

Necesitará una cadena de conexión Azure Storage para este tutorial. Para obtener más información sobre las cadenas de conexión, consulte Configuración de las [cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).

En el tutorial, escribirá la cadena de conexión en el script, de la siguiente manera:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Sin embargo, esto **no se recomienda** para los proyectos reales. La clave de la cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento. Siempre debe proteger la clave de la cuenta de almacenamiento. Evite distribuirla a otros usuarios, codificarla de forma rígida o guardarla en un archivo de texto que sea accesible a otros usuarios. Puede volver a generar la clave mediante Azure portal si cree que puede estar en peligro.

En el caso de las aplicaciones reales, la mejor manera de mantener la cadena de conexión de almacenamiento se encuentra en un archivo de configuración. Para capturar la cadena de conexión de un archivo de configuración, puede hacer lo siguiente:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

El uso del Administrador de configuración Azure es opcional. También puede usar una API, como el tipo de `ConfigurationManager` del .NET Framework.

### <a name="parse-the-connection-string"></a>Análisis de la cadena de conexión

Para analizar la cadena de conexión, use:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Esto devolverá un `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Crear el cliente del servicio de archivos

El tipo de `CloudFileClient` permite usar mediante programación los archivos almacenados en el almacenamiento de archivos. Esta es una forma de crear el cliente de servicio:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Ahora está listo para escribir código que lee datos de y escribe datos en el almacenamiento de archivos.

## <a name="create-a-file-share"></a>Crear un recurso compartido de archivos

En este ejemplo se muestra cómo crear un recurso compartido de archivos si aún no existe:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Crear un directorio raíz y un subdirectorio

Aquí se obtiene el directorio raíz y se obtiene un subdirectorio de la raíz. Puede crear ambos si aún no existen.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Cargar texto como un archivo

En este ejemplo se muestra cómo cargar texto como un archivo.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Descargar un archivo en una copia local del archivo

Aquí puede descargar el archivo que acaba de crear, anexando el contenido a un archivo local.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Establecer el tamaño máximo para un recurso compartido de archivos

En el ejemplo siguiente se muestra cómo comprobar el uso actual de un recurso compartido y cómo establecer la cuota para el recurso compartido. se debe llamar a `FetchAttributes` para rellenar el `Properties`de un recurso compartido y `SetProperties` para propagar los cambios locales a Azure File Storage.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generar una firma de acceso compartido para un archivo o recurso compartido de archivos

Puede generar una firma de acceso compartido (SAS) para un recurso compartido de archivos o para un archivo individual. También puede crear una directiva de acceso compartido en un recurso compartido de archivos para administrar firmas de acceso compartido. Se recomienda la creación de una directiva de acceso compartido, ya que ofrece un medio de revocar la SAS si esta se encuentra en peligro.

En este caso, se crea una directiva de acceso compartido en un recurso compartido y, a continuación, se usa esa Directiva para proporcionar las restricciones para una SAS en un archivo del recurso compartido.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Para más información sobre la creación y el uso de firmas de acceso compartido, consulte [Uso de firmas de acceso compartido (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) y [Creación y uso de una SAS con Blob Storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Copia de archivos

Puede copiar un archivo en otro archivo o en un BLOB, o un BLOB en un archivo. Si va a copiar un BLOB en un archivo, o un archivo en un BLOB, *debe* usar una firma de acceso compartido (SAS) para autenticar el objeto de origen, incluso si está copiando dentro de la misma cuenta de almacenamiento.

### <a name="copy-a-file-to-another-file"></a>Copiar un archivo en otro

Aquí, se copia un archivo en otro archivo en el mismo recurso compartido. Dado que en esta operación de copia se copia entre archivos de la misma cuenta de almacenamiento, puede usar la autenticación de clave compartida para realizar la copia.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Copiar un archivo en un blob

Aquí se crea un archivo y se copia en un BLOB dentro de la misma cuenta de almacenamiento. Puede crear una SAS para el archivo de código fuente, que el servicio utiliza para autenticar el acceso al archivo de origen durante la operación de copia.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Puede copiar un blob en un archivo de la misma manera. Si el objeto de origen es un blob, cree una SAS para autenticar el acceso a dicho blob durante la operación de copia.

## <a name="troubleshooting-file-storage-using-metrics"></a>Solución de problemas de almacenamiento de archivos mediante métricas

Azure Storage Analytics admite métricas para el almacenamiento de archivos. Con los datos de las métricas, es posible seguir paso a paso las solicitudes y diagnosticar problemas.

Puede habilitar las métricas de file Storage desde [Azure portal](https://portal.azure.com), o bien puede hacerlo de F# la siguiente manera:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Pasos siguientes

Consulte los vínculos siguientes para obtener más información acerca Azure File Storage.

### <a name="conceptual-articles-and-videos"></a>Artículos y vídeos conceptuales

- [Almacenamiento de archivos de Azure: un sistema de archivos SMB en la nube sin dificultades para Windows y Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Uso de Azure File Storage con Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Compatibilidad de herramientas con el almacenamiento de archivos

- [Usar Azure PowerShell con Azure Storage](/azure/storage/storage-powershell-guide-full)
- [Uso de AzCopy con Microsoft Azure Storage](/azure/storage/storage-use-azcopy)
- [Uso de la CLI de Azure con Azure Storage](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Referencia

- [Referencia de la biblioteca de clientes de almacenamiento para .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Referencia de la API REST del servicio de archivos](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Entradas de blog

- [El almacenamiento de archivos de Azure ya está disponible de manera general](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Dentro de Azure File Storage](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [Introducing Microsoft Azure File Service (Introducción al servicio de archivos de Microsoft Azure)](https://docs.microsoft.com/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [Persisting connections to Microsoft Azure Files (Persistencia de conexiones en archivos de Microsoft Azure)](https://docs.microsoft.com/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
