---
title: E/S de archivos y secuencias - .NET
description: Conozca los conceptos básicos de la E/S de archivos y secuencias, que es la transferencia de datos hacia o desde un medio de almacenamiento, en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- IO namespace
- files, I/O
- System.IO namespace
- I/O [.NET]
- streams, I/O
- data streams, I/O
ms.assetid: 4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2
ms.openlocfilehash: 4c6efc059423740f19460f24f12df81ac54f884a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825824"
---
# <a name="file-and-stream-io"></a>E/S de archivos y secuencias

La E/S (entrada/salida) de archivos y secuencias hace referencia a la transferencia de datos con destino u origen en un medio de almacenamiento. En .NET, los espacios de nombres `System.IO` contienen tipos que permiten la lectura y escritura, tanto sincrónica como asincrónica, en archivos y flujos de datos. Estos espacios de nombres también contienen tipos que realizan la compresión y la descompresión de archivos, así como tipos que permiten la comunicación a través de canalizaciones y puertos de serie.

Un archivo es una colección de bytes ordenada y con nombre que tiene un almacenamiento persistente. Cuando se trabaja con archivos, se opera con las rutas de acceso de directorios, almacenamiento en disco y nombres de archivo y de directorio. En cambio, una secuencia es una sucesión de bytes que se puede utilizar para leer y escribir en una memoria auxiliar, que puede ser uno de los distintos tipos de medios de almacenamiento (por ejemplo, discos o memoria). Al igual que hay varios tipos de memorias auxiliares distintas de los discos, existen varios tipos de secuencias distintas de las secuencias de archivo, como las secuencias de red, de memoria y de canalización.

## <a name="files-and-directories"></a>Archivos y directorios

Se pueden utilizar los tipos del espacio de nombres <xref:System.IO?displayProperty=nameWithType> para interactuar con archivos y directorios. Por ejemplo, se pueden obtener y establecer las propiedades de los archivos y directorios, y recuperar colecciones de archivos y de directorios basándose en criterios de búsqueda.

Para obtener las convenciones de nomenclatura de las rutas de acceso y las maneras de expresar una ruta de acceso de archivo para los sistemas Windows, incluidos con la sintaxis de dispositivo DOS compatible en .NET Core 1.1 y versiones posteriores, y .NET Framework 4.6.2 y versiones posteriores, consulte [Formatos de ruta de acceso de archivo en los sistemas Windows](file-path-formats.md).

Estas son algunas clases de archivo y directorio de uso general:

- <xref:System.IO.File>: proporciona métodos estáticos para crear, copiar, eliminar, mover y abrir archivos, y ayuda a crear un objeto <xref:System.IO.FileStream>.

- <xref:System.IO.FileInfo>: proporciona métodos de instancia para crear, copiar, eliminar, mover y abrir archivos, y ayuda a crear un objeto <xref:System.IO.FileStream>.

- <xref:System.IO.Directory>: proporciona métodos estáticos para crear, mover y enumerar directorios y subdirectorios.

- <xref:System.IO.DirectoryInfo>: proporciona métodos de instancia para crear, mover y enumerar directorios y subdirectorios.

- <xref:System.IO.Path>: proporciona métodos y propiedades para procesar cadenas de directorio entre plataformas.

Siempre debe proporcionar un control de excepciones sólido al llamar a métodos del sistema de archivos. Para más información, vea [Control de errores de E/S](handling-io-errors.md).

Además de usar estas clases, los usuarios de Visual Basic pueden usar los métodos y propiedades proporcionados por la clase <xref:Microsoft.VisualBasic.FileIO.FileSystem?displayProperty=nameWithType> para la E/S de archivos.

Vea [Cómo: Copiar directorios](how-to-copy-directories.md), [Cómo: Crear una lista de directorios](/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100)) y [Cómo: Enumerar directorios y archivos](how-to-enumerate-directories-and-files.md).

## <a name="streams"></a>Secuencias

La clase base abstracta <xref:System.IO.Stream> es compatible con bytes de lectura y escritura. Todas las clases que representan secuencias heredan de la clase <xref:System.IO.Stream>. La clase <xref:System.IO.Stream> y sus clases derivadas proporcionan una visión genérica de los repositorios y los orígenes de datos, y evitan que el programador tenga que ocuparse de los detalles específicos del sistema operativo y los dispositivos subyacentes.

Las secuencias comprenden tres operaciones fundamentales:

- Lectura: transferencia de datos desde una secuencia a una estructura de datos como, por ejemplo, una matriz de bytes.

- Escritura: transferencia de datos a una secuencia desde un origen de datos.

- Búsqueda: consulta y modificación de la posición actual en una secuencia.

Dependiendo del repositorio o el origen de datos subyacente, una secuencia puede admitir solo algunas de estas características. Por ejemplo, la clase <xref:System.IO.Pipes.PipeStream> no admite operaciones de búsqueda. Las propiedades <xref:System.IO.Stream.CanRead%2A>, <xref:System.IO.Stream.CanWrite%2A> y <xref:System.IO.Stream.CanSeek%2A> de una secuencia especifican las operaciones que admite.

Estas son algunas de las clases de secuencias de uso general:

- <xref:System.IO.FileStream>: para leer y escribir en un archivo.

- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>: para leer y escribir en un archivo en almacenamiento aislado.

- <xref:System.IO.MemoryStream>: para leer y escribir en la memoria como una memoria auxiliar.

- <xref:System.IO.BufferedStream>: para mejorar el rendimiento de las operaciones de lectura y escritura.

- <xref:System.Net.Sockets.NetworkStream>: para leer y escribir sobre los sockets de red.

- <xref:System.IO.Pipes.PipeStream>: para leer y escribir sobre canalizaciones anónimas y con nombre.

- <xref:System.Security.Cryptography.CryptoStream>: para vincular secuencias de datos con transformaciones criptográficas.

Para obtener un ejemplo de cómo trabajar con flujos de forma asincrónica, vea [E/S de archivos asincrónica](asynchronous-file-i-o.md).

## <a name="readers-and-writers"></a>Lectores y escritores

El espacio de nombres <xref:System.IO?displayProperty=nameWithType> también proporciona tipos para leer los caracteres codificados de las secuencias y escribirlos en ellas. Normalmente, las secuencias están diseñadas para la entrada y salida de bytes. Los tipos de lectura y escritura controlan la conversión de caracteres codificados en bytes y a la inversa, para que la secuencia pueda completar la operación. Cada clase de lectura y escritura se asocia a una secuencia, que se puede recuperar mediante la propiedad `BaseStream` de la clase.

Estas son algunas clases de lectura y escritura de uso general:

- <xref:System.IO.BinaryReader> y <xref:System.IO.BinaryWriter>: para leer y escribir tipos de datos primitivos como valores binarios.

- <xref:System.IO.StreamReader> y <xref:System.IO.StreamWriter>: para leer y escribir caracteres utilizando un valor de codificación para convertir los caracteres en bytes y a la inversa.

- <xref:System.IO.StringReader> y <xref:System.IO.StringWriter>: para leer y escribir caracteres en cadenas.

- <xref:System.IO.TextReader> y <xref:System.IO.TextWriter>: sirven como clases base abstractas para otros lectores y escritores que leen y escriben caracteres y cadenas, pero no datos binarios.

Vea [Cómo: Leer texto de un archivo](how-to-read-text-from-a-file.md), [Cómo: Escribir texto en un archivo](how-to-write-text-to-a-file.md), [Cómo: Leer caracteres de una cadena](how-to-read-characters-from-a-string.md) y [Cómo: Escribir caracteres en una cadena](how-to-write-characters-to-a-string.md).

## <a name="asynchronous-io-operations"></a>Operaciones de E/S asincrónicas

Leer o escribir una gran cantidad de datos puede requerir muchos recursos. Estas tareas se deben realizar de forma asincrónica si la aplicación necesita seguir respondiendo al usuario. Con las operaciones de E/S sincrónicas, el subproceso de la interfaz de usuario está bloqueado hasta que se completa la operación que usa gran cantidad de recursos.  Use operaciones de E/S asincrónicas al desarrollar aplicaciones para la Tienda Windows 8.x y, de este modo, evitar crear la impresión de que la aplicación ya no funciona.

Los miembros asincrónicos contienen `Async` en sus nombres, como los métodos <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> y <xref:System.IO.Stream.WriteAsync%2A>. Estos métodos se usan con las palabras clave `async` y `await`.

Para más información, consulte [E/S de archivos asincrónica](asynchronous-file-i-o.md).

## <a name="compression"></a>Compresión

La compresión se refiere al proceso de reducir el tamaño de un archivo para su almacenamiento. La descompresión es el proceso de extraer el contenido de un archivo comprimido para que esté en un formato utilizable. El espacio de nombres <xref:System.IO.Compression?displayProperty=nameWithType> contiene tipos para comprimir y descomprimir archivos y secuencias.

Las clases siguientes se utilizan con frecuencia al comprimir y descomprimir archivos y secuencias:

- <xref:System.IO.Compression.ZipArchive>: para crear y recuperar entradas en el archivo zip.

- <xref:System.IO.Compression.ZipArchiveEntry>: para representar un archivo comprimido.

- <xref:System.IO.Compression.ZipFile>: para crear, extraer y abrir un paquete comprimido.

- <xref:System.IO.Compression.ZipFileExtensions>: para crear y extraer entradas en un paquete comprimido.

- <xref:System.IO.Compression.DeflateStream>: para comprimir y descomprimir secuencias utilizando el algoritmo de deflación (Deflate).

- <xref:System.IO.Compression.GZipStream>: para comprimir y descomprimir secuencias con formato de datos gzip.

Vea [Cómo: Comprimir y extraer archivos](how-to-compress-and-extract-files.md).

## <a name="isolated-storage"></a>Almacenamiento aislado

El almacenamiento aislado es un mecanismo de almacenamiento de datos que proporciona aislamiento y seguridad mediante la definición de modos estándar de asociar código a los datos guardados. El almacenamiento proporciona un sistema de archivos virtual que está aislado para cada usuario, ensamblado y (opcionalmente) dominio. El almacenamiento aislado es especialmente útil cuando la aplicación no tiene permiso para obtener acceso a los archivos del usuario. Se pueden guardar los valores o los archivos de la aplicación de una forma controlada por la directiva de seguridad del equipo.

El almacenamiento aislado no está disponible para aplicaciones de la Tienda Windows 8.x, sino que deben usarse las clases de datos de aplicaciones del espacio de nombres <xref:Windows.Storage?displayProperty=nameWithType>. Para más información, vea [Datos de la aplicación](/previous-versions/windows/apps/hh464917(v=win.10)).

Las clases siguientes se utilizan con frecuencia al implementar el almacenamiento aislado:

- <xref:System.IO.IsolatedStorage.IsolatedStorage>: proporciona la clase base para las implementaciones de almacenamiento aislado.

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>: proporciona un área de almacenamiento aislado que contiene archivos y directorios.

- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>: expone un archivo dentro del almacenamiento aislado.

Vea [Almacenamiento aislado](isolated-storage.md).

## <a name="io-operations-in-windows-store-apps"></a>Operaciones de E/S en aplicaciones de Microsoft Store

El conjunto de .NET para las aplicaciones de la Tienda Windows 8.x contiene muchos de los tipos necesarios para leer y escribir en secuencias. Sin embargo, dicho conjunto no incluye todos los tipos de E/S de .NET.

Estas son algunas diferencias importantes que se deben tener en cuenta al utilizar operaciones de E/S en las aplicaciones de la Tienda Windows 8.x:

- Los tipos relacionados específicamente con las operaciones de archivo, como <xref:System.IO.File>, <xref:System.IO.FileInfo>, <xref:System.IO.Directory> y <xref:System.IO.DirectoryInfo>, no se incluyen en el conjunto de .NET para las aplicaciones de la Tienda Windows 8.x. En su lugar, use los tipos en el espacio de nombres <xref:Windows.Storage?displayProperty=nameWithType> de Windows Runtime, como <xref:Windows.Storage.StorageFile> y <xref:Windows.Storage.StorageFolder>.

- El almacenamiento aislado no está disponible; use en su lugar [datos de aplicaciones](/previous-versions/windows/apps/hh464917(v=win.10)).

- Use métodos asincrónicos, como <xref:System.IO.Stream.ReadAsync%2A> y <xref:System.IO.Stream.WriteAsync%2A>, para evitar bloquear el subproceso de interfaz de usuario.

- Los tipos de compresión que se basan en rutas de acceso <xref:System.IO.Compression.ZipFile> y <xref:System.IO.Compression.ZipFileExtensions> no están disponibles. En su lugar, use los tipos del espacio de nombres <xref:Windows.Storage.Compression?displayProperty=nameWithType>.

Si es necesario, puede convertir entre las secuencias de .NET Framework y las secuencias de Windows Runtime. Para obtener más información, vea [Cómo: Convertir flujos de .NET Framework en flujos de Windows Runtime y viceversa](how-to-convert-between-dotnet-streams-and-winrt-streams.md) o <xref:System.IO.WindowsRuntimeStreamExtensions>.

Para obtener más información sobre las operaciones de E/S en una aplicación de la Tienda Windows 8.x, vea [Inicio rápido: lectura y escritura de un archivo](/previous-versions/windows/apps/hh758325(v=win.10)).

## <a name="io-and-security"></a>E/S y seguridad

Cuando se utilizan las clases del espacio de nombres <xref:System.IO?displayProperty=nameWithType>, se deben seguir los requisitos de seguridad del sistema operativo como las listas de control de acceso (ACL) para controlar el acceso a los archivos y directorios. Este requisito es adicional a cualquier requisito <xref:System.Security.Permissions.FileIOPermission>. Se pueden administrar las listas de control de acceso mediante programación. Para obtener más información, vea [Cómo: Agregar o quitar entradas de la lista de control de acceso](how-to-add-or-remove-access-control-list-entries.md).

Las políticas de seguridad predeterminadas impiden que las aplicaciones de intranet o Internet obtengan acceso a los archivos del equipo del usuario. Por lo tanto, no use las clases de E/S que requieren una ruta a un archivo físico al escribir el código que se descarga a través de Internet o una intranet. En su lugar, use el [almacenamiento aislado](isolated-storage.md) para aplicaciones .NET.

Solo se realiza una comprobación de seguridad cuando se construye la secuencia. Por consiguiente, no abra una secuencia y se la pase al código o a los dominios de aplicación de menos confianza.

## <a name="related-topics"></a>Temas relacionados

- [Tareas de E/S comunes](common-i-o-tasks.md)\
Proporciona una lista de tareas de E/S asociadas a los archivos, directorios y secuencias, y vínculos al contenido y los ejemplos pertinentes para cada tarea.

- [E/S de archivos asincrónica](asynchronous-file-i-o.md)\
Describe las ventajas de rendimiento y el funcionamiento básico de la E/S asincrónica.

- [Almacenamiento aislado](isolated-storage.md)\
Describe un mecanismo de almacenamiento de datos que proporciona aislamiento y seguridad mediante la definición de las formas estándar de asociar código a los datos guardados.

- [Canalizaciones](pipe-operations.md)\
Describe las operaciones anónimas y de canalización con nombre de .NET.

- [Archivos asignados a memoria](memory-mapped-files.md)\
Describe los archivos asignados a memoria, que incluyen el contenido de archivos en disco en memoria virtual. Puede usar archivos asignados a memoria para editar archivos muy grandes y crear memoria compartida para la comunicación entre procesos.
