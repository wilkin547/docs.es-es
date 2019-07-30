---
title: Introducción a Azure Blob Storage mediante F#
description: Almacene datos no estructurados en la nube con Azure BLOB Storage.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: c8b42339ff1d76f262e956b5e34cc598e0fc855d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630514"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>Introducción a Azure BLOB Storage mediante F\#

Azure Blob Storage es un servicio que almacena datos no estructurados en la nube como objetos o blobs. El almacenamiento de blobs puede almacenar cualquier tipo de texto o datos binarios, como un documento, un archivo multimedia o un instalador de aplicación. El Almacenamiento de blobs también se conoce como "almacenamiento de objetos".

En este artículo se muestra cómo realizar tareas comunes con el almacenamiento de blobs. Los ejemplos se escriben F# mediante el uso de la biblioteca de cliente de Azure Storage para .net. Entre las tareas descritas se incluyen cómo cargar, enumerar, descargar y eliminar BLOBs.

Para obtener información general conceptual sobre el almacenamiento de blobs, consulte [la guía de .net para BLOB Storage](/azure/storage/storage-dotnet-how-to-use-blobs).

## <a name="prerequisites"></a>Requisitos previos

Para usar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account). También necesitará la clave de acceso de almacenamiento para esta cuenta.

## <a name="create-an-f-script-and-start-f-interactive"></a>Creación de F# un script e F# Inicio interactivo

Los ejemplos de este artículo se pueden usar en una F# aplicación o en un F# script. Para crear un F# script, cree un archivo con la `.fsx` extensión, por ejemplo `blobs.fsx`, en el F# entorno de desarrollo.

A continuación, use un [Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar `WindowsAzure.Storage` los `Microsoft.WindowsAzure.ConfigurationManager` paquetes y y `WindowsAzure.Storage.dll` la `Microsoft.WindowsAzure.Configuration.dll` referencia y en el script `#r` mediante una directiva.

### <a name="add-namespace-declarations"></a>Agregar declaraciones de espacio de nombres

Agregue las siguientes `open` instrucciones a la parte superior `blobs.fsx` del archivo:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Obtener la cadena de conexión

Necesita una cadena de conexión Azure Storage para este tutorial. Para obtener más información sobre las cadenas de conexión, consulte Configuración de las [cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).

En el tutorial, escriba la cadena de conexión en el script, como se indica a continuación:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

Sin embargo, esto **no se recomienda** para los proyectos reales. La clave de la cuenta de almacenamiento es similar a la contraseña raíz de la cuenta de almacenamiento. Siempre debe proteger la clave de la cuenta de almacenamiento. Evite distribuirla a otros usuarios, codificarla de forma rígida o guardarla en un archivo de texto sin formato al que puedan acceder otras personas. Puede volver a generar la clave mediante Azure portal si cree que puede estar en peligro.

En el caso de las aplicaciones reales, la mejor manera de mantener la cadena de conexión de almacenamiento se encuentra en un archivo de configuración. Para capturar la cadena de conexión de un archivo de configuración, puede hacer lo siguiente:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

El uso de Azure Configuration Manager es opcional. También puede usar una API, como el tipo de `ConfigurationManager` .NET Framework.

### <a name="parse-the-connection-string"></a>Analizar la cadena de conexión

Para analizar la cadena de conexión, use:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

Esto devuelve un `CloudStorageAccount`.

### <a name="create-some-local-dummy-data"></a>Crear algunos datos ficticios locales

Antes de empezar, cree algunos datos locales ficticios en el directorio del script. Más adelante se cargan estos datos.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Creación del cliente de Blob service

El `CloudBlobClient` tipo permite recuperar contenedores y blobs almacenados en el almacenamiento de blobs. Esta es una forma de crear el cliente del servicio:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

Ahora está listo para escribir código que lee datos de y escribe datos en el almacenamiento de blobs.

## <a name="create-a-container"></a>Crear un contenedor

En este ejemplo se muestra cómo crear un contenedor si aún no existe:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

De forma predeterminada, el nuevo contenedor es privado, lo que significa que debe especificar la clave de acceso de almacenamiento para descargar los blobs de este contenedor. Si desea que los archivos del contenedor estén disponibles para todos, puede establecer el contenedor para que sea público mediante el código siguiente:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

Cualquier usuario de Internet puede ver los blobs de un contenedor público, pero solo puede modificarlos o eliminarlos si dispone de la clave de acceso de la cuenta adecuada o de una firma de acceso compartido.

## <a name="upload-a-blob-into-a-container"></a>Carga de un BLOB en un contenedor

Azure Blob Storage admite blobs en bloques y blobs en páginas. En la mayoría de los casos, un BLOB en bloques es el tipo recomendado que se va a usar.

Para cargar un archivo en un BLOB en bloques, obtenga una referencia de contenedor y Úsela para obtener una referencia de BLOB en bloques. Una vez que tenga una referencia de BLOB, puede cargar cualquier secuencia de datos en ella llamando al `UploadFromFile` método. Esta operación crea el BLOB si no existía anteriormente, o lo sobrescribe si existe.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>Enumeración de los blobs de un contenedor

Para enumerar los blobs de un contenedor, primero obtenga una referencia de contenedor. Después, puede usar el método del `ListBlobs` contenedor para recuperar los blobs o directorios que contiene. Para tener acceso al conjunto completo de propiedades y métodos de un `IListBlobItem`devuelto, debe convertirlo en `CloudBlockBlob`un `CloudPageBlob`objeto, `CloudBlobDirectory` o. Si el tipo es desconocido, puede usar una comprobación de tipo para determinar a qué se va a convertir. En el código siguiente se muestra cómo recuperar y generar el URI de cada elemento del `mydata` contenedor:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

También puede asignar nombres a los blobs con la información de la ruta de acceso. Esto crea una estructura de directorios virtuales que puede organizar y recorrer como lo haría con un sistema de archivos tradicional. Tenga en cuenta que la estructura de directorios es solo virtual: los únicos recursos disponibles en BLOB Storage son contenedores y BLOBs. Sin embargo, la biblioteca de cliente de `CloudBlobDirectory` almacenamiento ofrece un objeto para hacer referencia a un directorio virtual y simplificar el proceso de trabajar con blobs organizados de este modo.

Por ejemplo, considere el siguiente conjunto de blobs en bloques en un `photos`contenedor denominado:

*photo1.jpg*\
*2015/architecture/description.txt*\
*2015/Architecture/photo3. jpg*\
*2015/Architecture/photo4. jpg*\
*2016/architecture/photo5.jpg*\
*2016/architecture/photo6.jpg*\
*2016/architecture/description.txt*\
*2016/photo7.jpg*\

Cuando se llama `ListBlobs` a en un contenedor (como en el ejemplo anterior), se devuelve una lista jerárquica. Si contiene `CloudBlobDirectory` objetos y `CloudBlockBlob` , que representan los directorios y los blobs del contenedor, respectivamente, la salida resultante tendrá un aspecto similar al siguiente:

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

Opcionalmente, puede establecer el `UseFlatBlobListing` parámetro `ListBlobs` del método en `true`. En este caso, cada BLOB del contenedor se devuelve como un `CloudBlockBlob` objeto. La llamada a `ListBlobs` para devolver una lista plana tiene el siguiente aspecto:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

y, en función del contenido actual del contenedor, los resultados son similares a los siguientes:

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

## <a name="download-blobs"></a>Descargar blobs

Para descargar blobs, primero recupere una referencia de BLOB y `DownloadToStream` , a continuación, llame al método. En el ejemplo siguiente se `DownloadToStream` usa el método para transferir el contenido del BLOB a un objeto de secuencia que se puede guardar en un archivo local.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

También puede usar el `DownloadToStream` método para descargar el contenido de un BLOB como una cadena de texto.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Eliminar blobs

Para eliminar un BLOB, primero obtenga una referencia de BLOB y, a `Delete` continuación, llame al método en ella.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>Enumerar blobs en páginas de forma asincrónica

Si está enumerando un gran número de blobs o desea controlar el número de resultados que se devuelven en una operación de lista, puede enumerar los blobs en páginas de resultados. En este ejemplo se muestra cómo devolver los resultados en páginas de forma asincrónica, de modo que la ejecución no se bloquee mientras se espera a devolver un conjunto grande de resultados.

En este ejemplo se muestra una lista plana `useFlatBlobListing` `ListBlobsSegmentedAsync` de blobs, pero también puede realizar una lista jerárquica estableciendo el parámetro del método en `false`.

En el ejemplo se define un método asincrónico, mediante `async` un bloque. La ``let!`` palabra clave suspende la ejecución del método de ejemplo hasta que se completa la tarea de lista.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

Ahora podemos usar esta rutina asincrónica como se indica a continuación. En primer lugar, cargue algunos datos ficticios (mediante el archivo local creado anteriormente en este tutorial).

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

Ahora, llame a la rutina. Se usa `Async.RunSynchronously` para forzar la ejecución de la operación asincrónica.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>Escribir en un BLOB en anexos

Un BLOB en anexos está optimizado para operaciones de anexión, como el registro. Al igual que un BLOB en bloques, un BLOB en anexos se compone de bloques, pero al agregar un nuevo bloque a un BLOB en anexos, siempre se anexa al final del BLOB. No se puede actualizar o eliminar un bloque existente en un BLOB en anexos. Los identificadores de bloque de un BLOB en anexos no se exponen como son para un BLOB en bloques.

Cada bloque de un BLOB en anexos puede tener un tamaño diferente, hasta un máximo de 4 MB, y un BLOB en anexos puede incluir un máximo de 50.000 bloques. Por lo tanto, el tamaño máximo de un BLOB en anexos es ligeramente superior a 195 GB (bloques de 4 MB X 50.000).

En el ejemplo siguiente se crea un nuevo BLOB en anexos y se anexan algunos datos, simulando una operación de registro simple.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

Vea Descripción de los blobs en [bloques, los blobs en páginas y](https://msdn.microsoft.com/library/azure/ee691964.aspx) los blobs en anexos para obtener más información sobre las diferencias entre los tres tipos de blobs.

## <a name="concurrent-access"></a>Acceso simultáneo

Para admitir el acceso simultáneo a un BLOB desde varios clientes o varias instancias de proceso, puede usar **etags** o **concesiones**.

* **ETag** : proporciona una manera de detectar que otro proceso ha modificado el BLOB o el contenedor.

* **Concesión** : proporciona una manera de obtener acceso exclusivo, renovable, de escritura o eliminación a un BLOB durante un período de tiempo.

Para obtener más información, vea [administrar la simultaneidad en Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).

## <a name="naming-containers"></a>Nomenclatura de contenedores

Cada BLOB de Azure Storage debe residir en un contenedor. El contenedor forma parte del nombre del BLOB. Por ejemplo, `mydata` es el nombre del contenedor en estos URI de BLOB de ejemplo:

- https://storagesample.blob.core.windows.net/mydata/blob1.txt
- https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

Un nombre de contenedor debe ser un nombre DNS válido, conforme a las siguientes reglas de nomenclatura:

1. Los nombres de contenedor deben comenzar por una letra o un número y solo pueden contener letras, números y el carácter de guion (-).
1. Cada carácter de guion (-) debe ir precedido y seguido inmediatamente de una letra o un número; los guiones consecutivos no se permiten en los nombres de contenedor.
1. Todas las letras de un nombre de contenedor deben estar en minúsculas.
1. Los nombres de contenedor deben tener entre 3 y 63 caracteres de longitud.

Tenga en cuenta que el nombre de un contenedor siempre debe estar en minúsculas. Si incluye una letra mayúscula en un nombre de contenedor o infringe las reglas de nomenclatura de contenedores, es posible que reciba un error 400 (solicitud incorrecta).

## <a name="managing-security-for-blobs"></a>Administrar la seguridad de los blobs

De forma predeterminada, Azure Storage protege los datos al limitar el acceso al propietario de la cuenta, quien está en posesión de las claves de acceso de la cuenta. Cuando necesite compartir datos de blobs en su cuenta de almacenamiento, es importante hacerlo sin poner en peligro la seguridad de las claves de acceso de la cuenta. Además, puede cifrar los datos de BLOB para asegurarse de que es seguro pasar por la conexión y Azure Storage.

### <a name="controlling-access-to-blob-data"></a>Controlar el acceso a los datos de BLOB

De forma predeterminada, solo el propietario de la cuenta de almacenamiento puede acceder a los datos de BLOB de la cuenta de almacenamiento. La autenticación de solicitudes en BLOB Storage requiere la clave de acceso de la cuenta de forma predeterminada. Sin embargo, es posible que desee poner determinados datos de BLOB a disposición de otros usuarios.

### <a name="encrypting-blob-data"></a>Cifrado de datos de blobs

Azure Storage admite el cifrado de datos de BLOB tanto en el cliente como en el servidor.

## <a name="next-steps"></a>Pasos siguientes

Ahora que ha aprendido los aspectos básicos del almacenamiento de blobs, siga estos vínculos para obtener más información.

### <a name="tools"></a>Herramientas

- [F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\
Un F# proveedor de tipo que se puede usar para explorar blobs, tablas y colas Azure Storage activos y aplicar fácilmente operaciones CRUD en ellos.

- [FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\
Una F# API para usar Microsoft Azure servicio Table Storage

- [Explorador de Microsoft Azure Storage (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\
Una aplicación independiente y gratuita de Microsoft que le permite trabajar visualmente con datos de Azure Storage en Windows, OS X y Linux.

### <a name="blob-storage-reference"></a>Referencia de almacenamiento de blobs

- [API de Azure Storage para .NET](/dotnet/api/overview/azure/storage)
- [Referencia de la API de REST de Azure Storage Services](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a>Guías relacionadas

- [Introducción con Azure Blob Storage enC#](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [Transferencia de datos con la utilidad de línea de comandos AzCopy en Windows](/azure/storage/common/storage-use-azcopy)
- [Transferencia de datos con la utilidad de línea de comandos AzCopy en Linux](/azure/storage/common/storage-use-azcopy-linux)
- [Configurar cadenas de conexión de Azure Storage](/azure/storage/common/storage-configure-connection-string)
- [Blog del equipo de Azure Storage](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Inicio rápido: Usar .NET para crear un BLOB en el almacenamiento de objetos](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
