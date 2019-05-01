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
# <a name="get-started-with-azure-blob-storage-using-f"></a>Introducción a Azure Blob storage mediante F\#

Azure Blob Storage es un servicio que almacena datos no estructurados en la nube como objetos o blobs. El almacenamiento de blobs puede almacenar cualquier tipo de texto o datos binarios, como un documento, un archivo multimedia o un instalador de aplicación. El Almacenamiento de blobs también se conoce como "almacenamiento de objetos".

Este artículo muestra cómo realizar tareas comunes con almacenamiento de blobs. Los ejemplos están escritos usando F# mediante la biblioteca de cliente de Azure Storage para. NET. Las tareas descritas incluyen cómo cargar, enumerar, descargar y eliminar blobs.

Información general conceptual de almacenamiento de blobs, consulte [la Guía de .NET para el almacenamiento de blobs](/azure/storage/storage-dotnet-how-to-use-blobs).

## <a name="prerequisites"></a>Requisitos previos

Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account). También necesitará la clave de acceso de almacenamiento para esta cuenta.

## <a name="create-an-f-script-and-start-f-interactive"></a>Crear un F# Script e iniciar F# interactivo

Los ejemplos de este artículo pueden usarse en cualquiera un F# aplicación o un F# secuencia de comandos. Para crear un F# de script, cree un archivo con el `.fsx` extensión, por ejemplo `blobs.fsx`, en su F# entorno de desarrollo.

A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` y `Microsoft.WindowsAzure.ConfigurationManager` referencia y paquetes `WindowsAzure.Storage.dll` y `Microsoft.WindowsAzure.Configuration.dll` en su secuencia de comandos con un `#r` directiva.

### <a name="add-namespace-declarations"></a>Agregue las declaraciones de espacio de nombres

Agregue el siguiente `open` instrucciones a la parte superior de la `blobs.fsx` archivo:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Obtener la cadena de conexión

En este tutorial, necesita una cadena de conexión de Azure Storage. Para obtener más información acerca de las cadenas de conexión, consulte [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).

Para el tutorial, escriba la cadena de conexión en la secuencia de comandos, así:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

Sin embargo, esto es **no recomienda** proyectos reales. La clave de cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento. Siempre debe proteger la clave de cuenta de almacenamiento. Evite distribuirla a otros usuarios, codificarla de forma o guardarlo en un archivo de texto sin formato que sea accesible a otros usuarios. Puede volver a generar la clave mediante Azure Portal si cree que puede verse comprometida.

Las aplicaciones para el real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración. Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

Con el Administrador de configuración de Azure es opcional. También puede usar una API como .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizar la cadena de conexión

Para analizar la cadena de conexión, use:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

Esto devuelve un `CloudStorageAccount`.

### <a name="create-some-local-dummy-data"></a>Crear algunos datos artificiales locales

Antes de comenzar, cree algunos datos artificiales locales en el directorio de la secuencia de comandos. Más tarde cargar estos datos.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Crear al cliente del servicio Blob

El `CloudBlobClient` tipo le permite recuperar contenedores y blobs almacenados en Blob storage. Aquí es una forma de crear al cliente del servicio:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

Ahora está listo para escribir código que lee y escribe datos en Blob storage.

## <a name="create-a-container"></a>Crear un contenedor

En este ejemplo se muestra cómo crear un contenedor si aún no existe:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

De forma predeterminada, el nuevo contenedor es privado, lo que significa que debe especificar la clave de acceso de almacenamiento para descargar blobs de este contenedor. Si desea que los archivos dentro del contenedor esté disponible para todos los usuarios, puede establecer el contenedor en público usando el código siguiente:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

Cualquier persona en Internet puede ver los blobs en un contenedor público, pero se puede modificarlos o eliminarlos solo si tiene la clave de acceso de la cuenta apropiada o una firma de acceso compartido.

## <a name="upload-a-blob-into-a-container"></a>Cargar un blob en un contenedor

Azure Blob Storage admite blobs en bloques y blobs en páginas. En la mayoría de los casos, un blob en bloques es el tipo recomendado para usar.

Para cargar un archivo en un blob en bloques, obtenga una referencia de contenedor y utilícela para obtener una referencia de blob en bloques. Una vez que tenga una referencia de blob, puede cargar cualquier flujo de datos a él mediante una llamada a la `UploadFromFile` método. Esta operación crea el blob si no existe previamente o sobrescribirlo si ya existe.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>Enumerar los blobs en un contenedor

Para enumerar los blobs en un contenedor, primero obtenga una referencia de contenedor. A continuación, puede usar el contenedor `ListBlobs` método para recuperar los blobs o directorios dentro de él. Para acceder al conjunto enriquecido de propiedades y métodos de una `IListBlobItem`, debe convertirla en una `CloudBlockBlob`, `CloudPageBlob`, o `CloudBlobDirectory` objeto. Si el tipo es desconocido, puede usar una comprobación de tipo para determinar que se va a convertir. El código siguiente muestra cómo recuperar y consultar el URI de cada elemento en el `mydata` contenedor:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

También puede blobs de nombre de la información de ruta de acceso en sus nombres. Esto crea una estructura de directorios virtuales que puede organizar y recorrer tal como lo haría con un sistema de archivos tradicional. Tenga en cuenta que la estructura de directorios es solo virtual, los únicos recursos disponibles en Blob storage son contenedores y blobs. Sin embargo, la biblioteca de cliente de almacenamiento ofrece un `CloudBlobDirectory` objeto para hacer referencia a un directorio virtual y simplificar el proceso de trabajo con blobs organizados de este modo.

Por ejemplo, considere el siguiente conjunto de blobs en bloques en un contenedor denominado `photos`:

*photo1.jpg*\
*2015/architecture/description.txt*\
*2015/architecture/photo3.jpg*\
*2015/architecture/photo4.jpg*\
*2016/architecture/photo5.jpg*\
*2016/architecture/photo6.jpg*\
*2016/architecture/description.txt*\
*2016/photo7.jpg*\

Cuando se llama a `ListBlobs` en un contenedor (como se muestra en el ejemplo anterior), se devuelve una lista jerárquica. Si contiene ambos `CloudBlobDirectory` y `CloudBlockBlob` objetos, que representan los directorios y los blobs del contenedor, de respectivamente, a continuación, el resultado tendrá un aspecto similar al siguiente:

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

Opcionalmente, puede establecer el `UseFlatBlobListing` parámetro de la `ListBlobs` método `true`. En este caso, se devuelven todos los blobs del contenedor como un `CloudBlockBlob` objeto. La llamada a `ListBlobs` para devolver una lista plana tiene este aspecto:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

y, según el contenido actual del contenedor, los resultados de este aspecto:

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

## <a name="download-blobs"></a>Descarga de blobs

Para descargar blobs, primero recupere una referencia de blob y, a continuación, llame a la `DownloadToStream` método. En el ejemplo siguiente se usa el `DownloadToStream` método para transferir el contenido del blob a un objeto de secuencia que, a continuación, puede guardar en un archivo local.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

También puede usar el `DownloadToStream` método para descargar el contenido de un blob como una cadena de texto.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Eliminar blobs

Para eliminar un blob, primero obtenga una referencia de blob y, a continuación, llame a la `Delete` método en él.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>Enumerar blobs en páginas de forma asincrónica

Si enumerar un gran número de blobs o desea controlar el número de resultados que devuelve en una operación de listado, puede enumerar blobs en páginas de resultados. Este ejemplo muestra cómo devolver resultados en páginas asincrónicamente, para que la ejecución no se bloquee mientras espera a devolver un conjunto grande de resultados.

En este ejemplo se muestra un listado de blobs plano, pero también puede realizar un listado jerárquico estableciendo el `useFlatBlobListing` parámetro de la `ListBlobsSegmentedAsync` método `false`.

El ejemplo define un método asincrónico, con un `async` bloque. El ``let!`` palabra clave suspende la ejecución del método de ejemplo hasta que se complete la tarea de enumeración.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

Ahora podemos usar esta rutina asincrónica como sigue. En primer lugar cargar algunos datos artificiales (mediante el archivo local que creó anteriormente en este tutorial).

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

Ahora, llame a la rutina. Usa `Async.RunSynchronously` para forzar la ejecución de la operación asincrónica.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>Escribir en un blob en anexos

Un blob en anexos se optimiza para las operaciones de anexado, como el registro. Como un blob en bloques, un blob en anexos está formado por bloques, pero cuando se agrega un nuevo bloque a un blob en anexos, siempre se anexa al final del blob. No se puede actualizar o eliminar un bloque existente en un blob en anexos. Los identificadores de bloque para un blob en anexos no se exponen como aparecen en un blob en bloques.

Cada bloque en un blob en anexos puede tener un tamaño diferente, hasta un máximo de 4 MB, y un blob en anexos puede incluir un máximo de 50.000 bloques. Por lo tanto, el tamaño máximo de un blob en anexos es un poco más de 195 GB (4 MB × 50 000 bloques).

El ejemplo siguiente crea un nuevo blob en anexos y le anexa algunos datos, simular una operación de registro simple.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

Consulte [descripción Blobs en bloques, Blobs en páginas y Blobs en anexos](https://msdn.microsoft.com/library/azure/ee691964.aspx) para obtener más información sobre las diferencias entre los tres tipos de blobs.

## <a name="concurrent-access"></a>Acceso simultáneo

Para admitir el acceso simultáneo a un blob desde varios clientes o varias instancias de proceso, puede usar **ETags** o **concesiones**.

* **ETag** -proporciona una manera de detectar que se ha modificado el blob o contenedor por otro proceso

* **Concesión** -proporciona una manera de obtener exclusivo y renovable de escritura o eliminación de acceso a un blob durante un período de tiempo

Para obtener más información, consulte [administración de la simultaneidad en Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).

## <a name="naming-containers"></a>Nomenclatura de contenedores

Todos los blobs de Azure storage deben residir en un contenedor. El contenedor forma parte del nombre del blob. Por ejemplo, `mydata` es el nombre del contenedor de estos URI de blob de ejemplo:

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

Un nombre de contenedor debe ser un nombre DNS válido, que se ajuste a las reglas de nomenclatura siguientes:

1. Los nombres de contenedor deben empezar por una letra o un número y pueden contener solo letras, números y guiones (-).
1. Deben estar precedido y seguido por una letra o un número; inmediatamente todos los caracteres de guión (-) no se permiten guiones consecutivos en nombres de contenedor.
1. Todas las letras de un nombre de contenedor deben estar en minúsculas.
1. Los nombres de contenedor deben tener entre 3 y 63 caracteres.

Tenga en cuenta que el nombre de un contenedor siempre debe estar en minúscula. Si se incluye una letra mayúscula en un nombre de contenedor o infringen los reglas de nomenclatura de contenedores, recibirá un error 400 (solicitud incorrecta).

## <a name="managing-security-for-blobs"></a>Administrar la seguridad de blobs

De forma predeterminada, Azure Storage protege sus datos al limitar el acceso al propietario de la cuenta, quien está en posesión de las claves de acceso de cuenta. Cuando necesite compartir datos blob en la cuenta de almacenamiento, es importante hacerlo sin poner en peligro la seguridad de las claves de acceso de cuenta. Además, puede cifrar los datos de blob para asegurarse de que es seguro pasar a través del cable y el almacenamiento de Azure.

### <a name="controlling-access-to-blob-data"></a>Controlar el acceso a datos blob

De forma predeterminada, los datos de blob en la cuenta de almacenamiento están accesibles solo al propietario de la cuenta de almacenamiento. Autenticar las solicitudes en el almacenamiento de blobs, requiere la clave de acceso de la cuenta de forma predeterminada. Sin embargo, es posible que desee que determinados datos blob esté disponible para otros usuarios.

### <a name="encrypting-blob-data"></a>Cifrado de datos blob

Azure Storage admite el cifrado de datos de blob en el cliente y en el servidor.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha aprendido los conceptos básicos del almacenamiento de blobs, siga estos vínculos para obtener más información.

### <a name="tools"></a>Herramientas

- [F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\
Un F# proveedor de tipos que se puede usar para explorar los recursos Blob, tabla y cola de Azure Storage y aplicar fácilmente las operaciones CRUD en ellos.

- [FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\
Un F# API para usar el servicio de Microsoft Azure Table Storage

- [Explorador de Microsoft Azure Storage (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\
Una aplicación independiente y gratuita de Microsoft que le permite trabajar visualmente con datos de Azure Storage en Windows, OS X y Linux.

### <a name="blob-storage-reference"></a>Referencia de BLOB storage

- [API de Azure Storage para .NET](/dotnet/api/overview/azure/storage)
- [Referencia de API de REST de servicios de Azure Storage](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a>Guías relacionadas

- [Introducción a Azure Blob Storage en C#](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [Transferencia de datos con la utilidad de línea de comandos de AzCopy en Windows](/azure/storage/common/storage-use-azcopy)
- [Transferencia de datos con la utilidad de línea de comandos de AzCopy en Linux](/azure/storage/common/storage-use-azcopy-linux)
- [Configurar cadenas de conexión de Azure Storage](/azure/storage/common/storage-configure-connection-string)
- [Blog del equipo de almacenamiento de Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Inicio rápido: Usar .NET para crear un blob en almacenamiento de objetos](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
