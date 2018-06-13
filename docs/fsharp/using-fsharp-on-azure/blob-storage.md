---
title: 'Introducción al almacenamiento de blobs de Azure con F #'
description: Almacenar datos no estructurados en la nube con el almacenamiento de blobs de Azure.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 3ab08154bd374896fce777c7c373204c9048b65c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576160"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>Introducción al almacenamiento de blobs de Azure con F # #

Azure Blob Storage es un servicio que almacena datos no estructurados en la nube como objetos o blobs. El almacenamiento de blobs puede almacenar cualquier tipo de texto o datos binarios, como un documento, un archivo multimedia o un instalador de aplicación. El Almacenamiento de blobs también se conoce como "almacenamiento de objetos".

Este artículo muestra cómo realizar tareas comunes mediante el almacenamiento de blobs. Los ejemplos se escriben con F # mediante la biblioteca de cliente de almacenamiento de Azure para. NET. Entre las tareas incluyen cómo cargar, enumerar, descargar y eliminar los blobs.

Para obtener información conceptual de almacenamiento de blobs, vea [la Guía de .NET para el almacenamiento de blobs](/azure/storage/storage-dotnet-how-to-use-blobs).

## <a name="prerequisites"></a>Requisitos previos

Para utilizar esta guía, primero debe [crear una cuenta de almacenamiento de Azure](/azure/storage/storage-create-storage-account). También se necesita la clave de acceso de almacenamiento para esta cuenta.

## <a name="create-an-f-script-and-start-f-interactive"></a>Crear un Script de F # y el inicio de F # Interactive

Los ejemplos de este artículo pueden usarse en una aplicación de F # o un script de F #. Para crear un script de F #, cree un archivo con el `.fsx` extensión, por ejemplo `blobs.fsx`, en el entorno de desarrollo de F #.

A continuación, use un [el Administrador de paquetes](package-management.md) como [Paket](https://fsprojects.github.io/Paket/) o [NuGet](https://www.nuget.org/) para instalar el `WindowsAzure.Storage` y `Microsoft.WindowsAzure.ConfigurationManager` paquetes y referencia `WindowsAzure.Storage.dll` y `Microsoft.WindowsAzure.Configuration.dll` en su secuencia de comandos mediante una `#r` directiva.

### <a name="add-namespace-declarations"></a>Agregue las declaraciones de espacio de nombres

Agregue el siguiente `open` instrucciones a la parte superior de la `blobs.fsx` archivo:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Obtener la cadena de conexión

Necesita una cadena de conexión de almacenamiento de Azure para este tutorial. Para obtener más información acerca de las cadenas de conexión, vea [configurar cadenas de conexión de almacenamiento](/azure/storage/storage-configure-connection-string).

Para el tutorial, escriba la cadena de conexión en el script, así:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

Sin embargo, esto es **no recomienda** proyectos de una manera real. La clave de cuenta de almacenamiento es similar a la contraseña raíz para la cuenta de almacenamiento. Tenga siempre cuidado proteger la clave de cuenta de almacenamiento. Evitar la distribución a otros usuarios, codificar de forma rígida, o guardarlo en un archivo de texto sin formato sea accesible a otros usuarios. Puede volver a generar la clave mediante el Portal de Azure si cree que se han comprometido.

Las aplicaciones de una manera real, la mejor manera de mantener la cadena de conexión de almacenamiento está en un archivo de configuración. Para capturar la cadena de conexión de un archivo de configuración, puede hacer esto:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

Con el Administrador de configuración de Azure es opcional. También puede utilizar una API como .NET Framework `ConfigurationManager` tipo.

### <a name="parse-the-connection-string"></a>Analizar la cadena de conexión

Para analizar la cadena de conexión, use:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

Esto devuelve un `CloudStorageAccount`.

### <a name="create-some-local-dummy-data"></a>Crear algunos datos ficticios locales

Antes de empezar, cree algunos datos ficticios locales en el directorio de la secuencia de comandos. Más adelante, cargar estos datos.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Crear al cliente del servicio Blob

El `CloudBlobClient` tipo le permite recuperar los contenedores y blobs almacenados en almacenamiento de blobs. Aquí es una manera de crear al cliente del servicio:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

Ahora está listo para escribir código que lee datos de y escribe datos en almacenamiento de blobs.

## <a name="create-a-container"></a>Crear un contenedor

En este ejemplo se muestra cómo crear un contenedor si aún no existe:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

De forma predeterminada, el nuevo contenedor es privado, lo que significa que debe especificar la clave de acceso de almacenamiento para descargar los blobs de este contenedor. Si desea poner a disposición los archivos dentro del contenedor para todos los usuarios, puede establecer el contenedor como público con el código siguiente:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

Todos los usuarios de Internet pueden ver los blobs en un contenedor público, pero puede modificar o eliminarlos sólo si tiene la clave de acceso de cuenta correspondiente o una firma de acceso compartido.

## <a name="upload-a-blob-into-a-container"></a>Cargar un blob en un contenedor

Almacenamiento de blobs de Azure es compatible con blobs en bloques y blobs en páginas. En la mayoría de los casos, un blob en bloques es el tipo recomendado para usar.

Para cargar un archivo en un blob en bloques, obtener una referencia de contenedor y usarlo para obtener una referencia de blob de bloque. Una vez que tenga una referencia de blob, puede cargar todos los flujos de datos a ella mediante una llamada a la `UploadFromFile` método. Esta operación crea el blob si no existe previamente o sobrescribir si existe.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>Enumerar los blobs en un contenedor

Para enumerar los blobs en un contenedor, primero hay que obtener una referencia de contenedor. A continuación, puede usar el contenedor `ListBlobs` método para recuperar los blobs o directorios dentro de él. Para tener acceso el amplio conjunto de propiedades y métodos para un devuelto `IListBlobItem`, debe convertirlo a un `CloudBlockBlob`, `CloudPageBlob`, o `CloudBlobDirectory` objeto. Si el tipo es desconocido, puede usar una comprobación de tipo para determinar qué convertirlo a. El código siguiente muestra cómo recuperar y salida el URI de cada elemento en el `mydata` contenedor:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

También puede blobs de nombre con la información de ruta de acceso en sus nombres. Esto crea una estructura de directorios virtuales que se puede organizar y recorrer tal y como lo haría con un sistema de archivos tradicional. Tenga en cuenta que la estructura de directorios es virtual solo, los únicos recursos disponibles en el almacenamiento de blobs son contenedores y blobs. Sin embargo, la biblioteca de cliente de almacenamiento ofrece una `CloudBlobDirectory` objeto para hacer referencia a un directorio virtual y simplificar el proceso de trabajar con los blobs que se organizan de esta manera.

Por ejemplo, considere el siguiente conjunto de blobs en bloques en un contenedor denominado `photos`:

*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015 / arquitectura/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg* 
 *2016/architecture/description.txt*
*2016/photo7.jpg*

Cuando se llama a `ListBlobs` en un contenedor (como en el ejemplo anterior), se devuelve una lista jerárquica. Si contiene dos `CloudBlobDirectory` y `CloudBlockBlob` objetos, que representan los directorios y los blobs del contenedor de respectivamente, a continuación, la salida resultante es similar al siguiente:

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

Si lo desea, puede establecer la `UseFlatBlobListing` parámetro de la `ListBlobs` método `true`. En este caso, se devuelve cada blob del contenedor como una `CloudBlockBlob` objeto. La llamada a `ListBlobs` para devolver una lista plana tiene el siguiente aspecto:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

y, según el contenido actual del contenedor, los resultados de un aspecto similar al siguiente:

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

Para descargar los blobs, recuperar primero una referencia de blob y, a continuación, llame a la `DownloadToStream` método. En el ejemplo siguiente se usa el `DownloadToStream` método para transferir el contenido del blob en un objeto stream que, a continuación, puede hacer persistir para un archivo local.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

También puede usar el `DownloadToStream` método para descargar el contenido de un blob como una cadena de texto.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Eliminar los blobs

Para eliminar un blob, primero hay que obtener una referencia de blob y, a continuación, llame a la `Delete` método en él.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>Enumerar blobs en páginas de forma asincrónica

Si enumerar un gran número de blobs, o para controlar el número de resultados que devuelven en una sola operación de lista, puede enumerar blobs en páginas de resultados. Este ejemplo muestra cómo devolver resultados en las páginas de forma asincrónica, por lo que no la ejecución se bloquea mientras se esperaba para devolver un conjunto grande de resultados.

Este ejemplo muestra una lista plana de blobs, pero también puede realizar una lista jerárquica, estableciendo el `useFlatBlobListing` parámetro de la `ListBlobsSegmentedAsync` método `false`.

El ejemplo define un método asincrónico, con un `async` bloque. El ``let!`` palabra clave suspende la ejecución del método de ejemplo hasta que se complete la tarea de la lista.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

Ahora podemos usar esta rutina asincrónica como se indica a continuación. Cargar primero algunos datos ficticios (mediante el archivo local que creó anteriormente en este tutorial).

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

Ahora, llame a la rutina. Utiliza ``Async.RunSynchronously`` para forzar la ejecución de la operación asincrónica.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>Escribir en un blob en anexos

Un blob en anexos está optimizado para las operaciones de anexado, como el registro. Como un blob en bloques, un blob en anexos está formado por bloques, pero cuando agrega un nuevo bloque a un blob en anexos, siempre se anexa al final del blob. No se puede actualizar o eliminar un bloque existente en un blob en anexos. Los identificadores de bloque para un blob en anexos no se exponen como sirven como un blob en bloques.

Cada bloque de un blob en anexos puede tener un tamaño diferente, hasta un máximo de 4 MB, y un blob en anexos puede incluir un máximo de 50.000 bloques. El tamaño máximo de un blob en anexos, por tanto, es un poco más de 195 GB (4 MB X 50.000 bloques).

En el ejemplo siguiente se crea un nuevo blob en anexos y anexa algunos datos, simular una operación de registro simple.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

Vea [descripción Blobs en bloques, Blobs de página y anexar Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) para obtener más información sobre las diferencias entre los tres tipos de blobs.

## <a name="concurrent-access"></a>Acceso simultáneo

Para permitir el acceso simultáneo a un blob desde varios clientes o varias instancias de proceso, puede usar **ETags** o **concesiones**.

* **ETag** -proporciona una manera de detectar que el blob o contenedor se ha modificado por otro proceso

* **Concesión** -proporciona una manera de obtener exclusivo, renovable, escribir o eliminar el acceso a un blob durante un período de tiempo

Para obtener más información, consulte [administrar la simultaneidad en el almacenamiento de Azure de Microsoft](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).

## <a name="naming-containers"></a>Nomenclatura de contenedores

Cada blob en el almacenamiento de Azure debe residir en un contenedor. El contenedor forma parte del nombre del blob. Por ejemplo, `mydata` es el nombre del contenedor en estos URI de blob de ejemplo:

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

Un nombre de contenedor debe ser un nombre DNS válido, conforme a las reglas de nomenclatura siguientes:

1. Los nombres de contenedor deben empezar por una letra o un número y pueden contener solo letras, números y el carácter de guión (-).
1. Deben estar precedido y seguido por una letra o un número; inmediatamente todos los caracteres guión (-) no se permiten guiones consecutivos en los nombres de contenedor.
1. Todas las letras de un nombre de contenedor deben estar en minúsculas.
1. Los nombres de contenedor deben tener entre 3 y 63 caracteres.

Tenga en cuenta que el nombre de un contenedor siempre debe estar en minúscula. Si incluye una letra mayúscula en un nombre de contenedor, o en caso contrario, infringe el reglas de nombres de contenedor, recibirá un error 400 (solicitud incorrecta).

## <a name="managing-security-for-blobs"></a>Administrar la seguridad de blobs

De forma predeterminada, el almacenamiento de Azure se mantienen los datos seguros limitando el acceso al propietario de la cuenta, que está en posesión de las claves de acceso de cuenta. Cuando necesite compartir los datos de blob en la cuenta de almacenamiento, es importante hacerlo sin poner en peligro la seguridad de las claves de acceso de cuenta. Además, puede cifrar los datos de blob para asegurarse de que es seguro pasar a través de la conexión y el almacenamiento de Azure.

### <a name="controlling-access-to-blob-data"></a>Controlar el acceso a los datos blob

De forma predeterminada, los datos blob en la cuenta de almacenamiento son accesibles únicamente al propietario de la cuenta de almacenamiento. Autenticar las solicitudes en el almacenamiento de blobs, requiere la clave de acceso de cuenta predeterminada. Sin embargo, puede que determinados datos de blob esté disponible para otros usuarios.

Para obtener más información sobre cómo controlar el acceso al almacenamiento de blobs, vea [la Guía de .NET para la sección de almacenamiento de blobs en el control de acceso](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).


### <a name="encrypting-blob-data"></a>Cifrar los datos de blob

Almacenamiento de Azure admite el cifrado de datos de blob en el cliente y en el servidor.

Para obtener más información sobre cómo cifrar datos blob, vea [la Guía de .NET para la sección de almacenamiento blob cifrado](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).

## <a name="next-steps"></a>Pasos siguientes

Ahora que conoce los conceptos básicos de almacenamiento de blobs, siga estos vínculos para obtener más información.

### <a name="tools"></a>Herramientas
- [F # AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/) un tipo de proveedor de F # que se puede usar para explorar recursos de Blob, tabla y cola de almacenamiento de Azure y aplicar las operaciones CRUD en ellos con más facilidad.
- [FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) una API de F # para usar el servicio de almacenamiento de tablas de Microsoft Azure
- [Explorador de almacenamiento de Azure de Microsoft (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) es una aplicación independiente disponible, de Microsoft que le permite trabajar visualmente con datos del almacenamiento de Azure en Windows, OS X y Linux.

### <a name="blob-storage-reference"></a>Referencia de almacenamiento de blobs

- [API de almacenamiento de Azure para .NET](/dotnet/api/overview/azure/storage)
- [Referencia de API de REST de servicios de almacenamiento de Azure](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a>Guías relacionadas

- [Introducción a almacenamiento de blobs de Azure en C#](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [Transferencia de datos con la utilidad de línea de comandos de AzCopy en Windows](/azure/storage/common/storage-use-azcopy)
- [Transferencia de datos con la utilidad de línea de comandos de AzCopy en Linux](/azure/storage/common/storage-use-azcopy-linux)
- [Configurar cadenas de conexión de almacenamiento de Azure](/azure/storage/common/storage-configure-connection-string)
- [Blog del equipo de almacenamiento de Azure](https://blogs.msdn.microsoft.com/windowsazurestorage/)
