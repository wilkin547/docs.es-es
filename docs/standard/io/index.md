---
title: E/S de archivos y flujos | Microsoft Docs
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IO namespace
- files, I/O
- System.IO namespace
- I/O [.NET Framework]
- streams, I/O
- data streams, I/O
ms.assetid: 4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2
caps.latest.revision: 33
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 1fabc43044b6e0fa765a7c2f225add8b7eb923f5
ms.openlocfilehash: 1d0c203313b33aeba26aded268467b1a1b181118
ms.lasthandoff: 05/02/2017

---
# <a name="file-and-stream-io"></a>E/S de archivos y secuencias
La E/S (entrada/salida) de archivos y secuencias hace referencia a la transferencia de datos con destino u origen en un medio de almacenamiento. En .NET Framework, los espacios de nombres [System.IO](http://go.microsoft.com/fwlink/?LinkId=231142) contienen tipos que permiten la lectura y escritura, tanto sincrónica como asincrónica, en archivos y flujos de datos. Estos espacios de nombres también contienen tipos que realizan la compresión y la descompresión de archivos, así como tipos que permiten la comunicación a través de canalizaciones y puertos de serie.  
  
 Un archivo es una colección de bytes ordenada y con nombre que tiene un almacenamiento persistente. Cuando se trabaja con archivos, se opera con las rutas de acceso de directorios, almacenamiento en disco y nombres de archivo y de directorio. En cambio, una secuencia es una sucesión de bytes que se puede utilizar para leer y escribir en una memoria auxiliar, que puede ser uno de los distintos tipos de medios de almacenamiento (por ejemplo, discos o memoria). Al igual que hay varios tipos de memorias auxiliares distintas de los discos, existen varios tipos de secuencias distintas de las secuencias de archivo, como las secuencias de red, de memoria y de canalización.  
  
## <a name="files-and-directories"></a>Archivos y directorios  
 Se pueden utilizar los tipos del espacio de nombres <xref:System.IO?displayProperty=fullName> para interactuar con archivos y directorios. Por ejemplo, se pueden obtener y establecer las propiedades de los archivos y directorios, y recuperar colecciones de archivos y de directorios basándose en criterios de búsqueda.  
  
 Estas son algunas clases de archivo y directorio de uso general:  
  
-   <xref:System.IO.File>: proporciona métodos estáticos para crear, copiar, eliminar, mover y abrir archivos, y ayuda a crear un objeto <xref:System.IO.FileStream>.  
  
-   <xref:System.IO.FileInfo>: proporciona métodos estáticos para crear, copiar, eliminar, mover y abrir archivos, y ayuda a crear un objeto <xref:System.IO.FileStream>.  
  
-   <xref:System.IO.Directory>: proporciona métodos estáticos para crear, mover y enumerar en directorios y subdirectorios.  
  
-   <xref:System.IO.DirectoryInfo>: : proporciona métodos de instancia para crear, mover y enumerar en directorios y subdirectorios.  
  
-   <xref:System.IO.Path>: proporciona métodos y propiedades para procesar cadenas de directorio entre plataformas.  
  
 Además de estas clases, los usuarios de Visual Basic pueden usar los métodos y propiedades proporcionados por la clase <xref:Microsoft.VisualBasic.FileIO.FileSystem?displayProperty=fullName> para la E/S de archivos.  
  
 Vea [How to: Copy Directories](../../../docs/standard/io/how-to-copy-directories.md)(Cómo: Copiar directorios), [Cómo: Crear una lista de directorios](http://msdn.microsoft.com/en-us/4d2772b1-b991-4532-a8a6-6ef733277e69) y [How to: Enumerate Directories and Files](../../../docs/standard/io/how-to-enumerate-directories-and-files.md) (Cómo: Enumerar directorios y archivos).  
  
## <a name="streams"></a>Secuencias  
 La clase base abstracta <xref:System.IO.Stream> es compatible con bytes de lectura y escritura. Todas las clases que representan flujos se heredan de la clase <xref:System.IO.Stream>. La clase <xref:System.IO.Stream> y sus clases derivadas proporcionan una visión genérica de los repositorios y los orígenes de datos, y evitan que el programador tenga que ocuparse de los detalles específicos del sistema operativo y los dispositivos subyacentes.  
  
 Las secuencias comprenden tres operaciones fundamentales:  
  
-   Lectura: transferencia de datos desde una secuencia a una estructura de datos como, por ejemplo, una matriz de bytes.  
  
-   Escritura: transferencia de datos a una secuencia desde un origen de datos.  
  
-   Búsqueda: consulta y modificación de la posición actual en una secuencia.  
  
 Dependiendo del repositorio o el origen de datos subyacente, una secuencia puede admitir solo algunas de estas características. Por ejemplo, la clase <xref:System.IO.Pipes.PipeStream> no admite búsquedas. Las propiedades <xref:System.IO.Stream.CanRead%2A>, <xref:System.IO.Stream.CanWrite%2A> y <xref:System.IO.Stream.CanSeek%2A> de un flujo especifican las operaciones que el flujo admite.  
  
 Estas son algunas de las clases de secuencias de uso general:  
  
-   <xref:System.IO.FileStream>: para leer y escribir en un archivo.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>: para leer y escribir en un archivo en almacenamiento aislado.  
  
-   <xref:System.IO.MemoryStream>: para leer y escribir en la memoria como memoria auxiliar.  
  
-   <xref:System.IO.BufferedStream>: para mejorar el rendimiento de las operaciones de lectura y escritura.  
  
-   <xref:System.Net.Sockets.NetworkStream>: para leer y escribir sobre sockets de red.  
  
-   <xref:System.IO.Pipes.PipeStream>: para leer y escribir sobre canalizaciones anónimas y con nombre.  
  
-   <xref:System.Security.Cryptography.CryptoStream>: para vincular flujos de datos a transformaciones criptográficas.  
  
 Para obtener un ejemplo de cómo trabajar con flujos de forma asincrónica, vea [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica).  
  
## <a name="readers-and-writers"></a>Lectores y escritores  
 El espacio de nombres <xref:System.IO?displayProperty=fullName> también proporciona tipos para leer caracteres codificados de flujos y escribirlos en ellos. Normalmente, las secuencias están diseñadas para la entrada y salida de bytes. Los tipos de lectura y escritura controlan la conversión de caracteres codificados en bytes y a la inversa, para que la secuencia pueda completar la operación. Cada clase de lectura y escritura se asocia a una secuencia, que se puede recuperar mediante la propiedad `BaseStream` de la clase.  
  
 Estas son algunas clases de lectura y escritura de uso general:  
  
-   <xref:System.IO.BinaryReader> y <xref:System.IO.BinaryWriter>: para leer y escribir tipos de datos primitivos como valores binarios.  
  
-   <xref:System.IO.StreamReader> y <xref:System.IO.StreamWriter>: para leer y escribir caracteres mediante un valor de codificación que convierta caracteres en bytes y a la inversa.  
  
-   <xref:System.IO.StringReader> y <xref:System.IO.StringWriter>: para leer y escribir caracteres en cadenas y a la inversa.  
  
-   <xref:System.IO.TextReader> y <xref:System.IO.TextWriter>: sirven como clases base abstractas para otros lectores y escritores que leen y escriben caracteres y cadenas, pero no datos binarios.  
  
 Vea [How to: Read Text from a File](../../../docs/standard/io/how-to-read-text-from-a-file.md) (Cómo: Leer texto de un archivo), [How to: Write Text to a File](../../../docs/standard/io/how-to-write-text-to-a-file.md) (Cómo: Escribir texto en un archivo), [How to: Read Characters from a String](../../../docs/standard/io/how-to-read-characters-from-a-string.md) (Cómo: Leer caracteres de una cadena) y [How to: Write Characters to a String](../../../docs/standard/io/how-to-write-characters-to-a-string.md) (Cómo: Escribir caracteres en una cadena).  
  
## <a name="asynchronous-io-operations"></a>Operaciones de E/S asincrónicas  
 Leer o escribir una gran cantidad de datos puede requerir muchos recursos. Estas tareas se deben realizar de forma asincrónica si la aplicación necesita seguir respondiendo al usuario. Con las operaciones de E/S sincrónicas, el subproceso de la interfaz de usuario está bloqueado hasta que se completa la operación que usa gran cantidad de recursos.  Use operaciones de E/S asincrónicas al desarrollar aplicaciones para la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] para evitar crear la impresión de que la aplicación ha dejado de responder.  
  
 Los miembros asincrónicos incluyen `Async` en sus nombres, como, por ejemplo, los métodos <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.FlushAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> y <xref:System.IO.Stream.WriteAsync%2A>. Estos métodos se usan con las palabras clave `async` y `await`.  
  
 Para más información, consulte [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica).  
  
## <a name="compression"></a>Compresión  
 La compresión se refiere al proceso de reducir el tamaño de un archivo para su almacenamiento. La descompresión es el proceso de extraer el contenido de un archivo comprimido para que esté en un formato utilizable. El espacio de nombres <xref:System.IO.Compression?displayProperty=fullName> contiene tipos para comprimir y descomprimir archivos y flujos.  
  
 Las clases siguientes se utilizan con frecuencia al comprimir y descomprimir archivos y secuencias:  
  
-   <xref:System.IO.Compression.ZipArchive>: para crear y recuperar entradas en el archivo zip.  
  
-   <xref:System.IO.Compression.ZipArchiveEntry>: para representar un archivo comprimido.  
  
-   <xref:System.IO.Compression.ZipFile>: para crear, extraer y abrir un paquete comprimido.  
  
-   <xref:System.IO.Compression.ZipFileExtensions>: para crear y extraer entradas en un paquete comprimido.  
  
-   <xref:System.IO.Compression.DeflateStream>: para comprimir y descomprimir flujos con el algoritmo Deflate.  
  
-   <xref:System.IO.Compression.GZipStream>: para comprimir y descomprimir flujos con formato de datos gzip.  
  
 Vea [How to: Compress and Extract Files](../../../docs/standard/io/how-to-compress-and-extract-files.md) (Cómo: Comprimir y extraer archivos).  
  
## <a name="isolated-storage"></a>Almacenamiento aislado  
 El almacenamiento aislado es un mecanismo de almacenamiento de datos que proporciona aislamiento y seguridad mediante la definición de modos estándar de asociar código a los datos guardados. El almacenamiento proporciona un sistema de archivos virtual que está aislado para cada usuario, ensamblado y (opcionalmente) dominio. El almacenamiento aislado es especialmente útil cuando la aplicación no tiene permiso para obtener acceso a los archivos del usuario. Se pueden guardar los valores o los archivos de la aplicación de una forma controlada por la directiva de seguridad del equipo.  
  
 El almacenamiento aislado no está disponible para aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], sino que deben usarse las clases de datos de aplicaciones del espacio de nombres [Windows.Storage](http://msdn.microsoft.com/library/windows/apps/windows.storage.aspx). Para más información, consulte [Almacenamiento de datos de aplicación](http://go.microsoft.com/fwlink/?LinkId=229175) en el Centro de desarrollo de Windows.  
  
 Las clases siguientes se utilizan con frecuencia al implementar el almacenamiento aislado:  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorage>: proporciona la clase base para las implementaciones de almacenamiento aislado.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFile>: proporciona un área de almacenamiento aislado que contiene archivos y directorios.  
  
-   <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>: expone un archivo dentro del almacenamiento aislado.  
  
 Vea [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md).  
  
## <a name="io-operations-in-windows-store-apps"></a>Operaciones de E/S en aplicaciones de la Tienda Windows  
 [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] contiene muchos de los tipos necesarios para leer y escribir en secuencias; sin embargo, este conjunto no incluye todos los tipos de E/S de .NET Framework.  
  
 Estas son algunas diferencias importantes que se deben tener en cuenta al utilizar operaciones de E/S en las aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)]:  
  
-   Los tipos relacionados específicamente con operaciones de archivo, como <xref:System.IO.File>, <xref:System.IO.FileInfo>, <xref:System.IO.Directory> y <xref:System.IO.DirectoryInfo>, no se incluyen en las aplicaciones de la [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)]. En su lugar, use los tipos del espacio de nombres [Windows.Storage](http://msdn.microsoft.com/library/windows/apps/windows.storage.aspx) de [!INCLUDE[wrt](../../../includes/wrt-md.md)], como [StorageFile](http://msdn.microsoft.com/library/windows/apps/windows.storage.storagefile.aspx) y [StorageFolder](http://msdn.microsoft.com/library/windows/apps/windows.storage.storagefolder.aspx).  
  
-   El almacenamiento aislado no está disponible; use en su lugar [datos de aplicaciones](http://go.microsoft.com/fwlink/?LinkId=229175).  
  
-   Use métodos asincrónicos tales como <xref:System.IO.Stream.ReadAsync%2A> y <xref:System.IO.Stream.WriteAsync%2A> para evitar el bloqueo del subproceso de UI.  
  
-   Los tipos de compresión basada en rutas de acceso <xref:System.IO.Compression.ZipFile> y <xref:System.IO.Compression.ZipFileExtensions> no se encuentran disponibles. Use en su lugar los tipos del espacio de nombres [Windows.Storage.Compression](http://msdn.microsoft.com/library/windows/apps/windows.storage.compression.aspx).  
  
 Si es necesario, puede convertir entre las secuencias de .NET Framework y las secuencias de Windows Runtime. Para más información, vea [Cómo: Convertir flujos de .NET Framework en flujos de Windows en tiempo de ejecución](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md) o [System.IO.WindowsRuntimeStreamExtensions](https://msdn.microsoft.com/library/system.io.windowsruntimestreamextensions.aspx). <!--zz TODO: <xref:System.IO.WindowsRuntimeStreamExtensions>--> 
  
 Para más información sobre las operaciones de E/S en una aplicación de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], vea [Inicio rápido: leer y escribir archivos (XAML)](http://go.microsoft.com/fwlink/p/?LinkId=243072) en el Centro de desarrollo de Windows.  
  
## <a name="io-and-security"></a>E/S y seguridad  
 Cuando se utilizan las clases del espacio de nombres <xref:System.IO?displayProperty=fullName>, se deben seguir los requisitos de seguridad del sistema operativo como las listas de control de acceso (ACL) para controlar el acceso a los archivos y directorios. Este requisito es adicional a los requisitos de <xref:System.Security.Permissions.FileIOPermission>. Se pueden administrar las listas de control de acceso mediante programación. Para más información, consulte [How to: Add or Remove Access Control List Entries](../../../docs/standard/io/how-to-add-or-remove-access-control-list-entries.md) (Cómo: Agregar o quitar entradas de la lista de control de acceso).  
  
 Las políticas de seguridad predeterminadas impiden que las aplicaciones de intranet o Internet obtengan acceso a los archivos del equipo del usuario. Por lo tanto, no use las clases de E/S que requieren una ruta a un archivo físico al escribir el código que se descarga a través de Internet o una intranet. Use en su lugar [almacenamiento aislado](../../../docs/standard/io/isolated-storage.md) para las aplicaciones tradicionales de .NET Framework, o [datos de aplicaciones](http://go.microsoft.com/fwlink/?LinkId=229175) para las aplicaciones de la [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  
  
 Solo se realiza una comprobación de seguridad cuando se construye la secuencia. Por consiguiente, no abra una secuencia y se la pase al código o a los dominios de aplicación de menos confianza.  
  
## <a name="related-topics"></a>Temas relacionados  
  
-   [Tareas de E/S comunes](../../../docs/standard/io/common-i-o-tasks.md)  
  
 Proporciona una lista de tareas de E/S asociadas a los archivos, directorios y secuencias, y vínculos al contenido y los ejemplos pertinentes para cada tarea.  
  
-   [Asynchronous File I/O](../../../docs/standard/io/asynchronous-file-i-o.md) (E/S de archivos asincrónica)  
  
 Describe las ventajas de rendimiento y el funcionamiento básico de la E/S asincrónica.  
  
-   [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)  
  
 Describe un mecanismo de almacenamiento de datos que proporciona aislamiento y seguridad mediante la definición de las formas estándar de asociar código a los datos guardados.  
  
-   [Pipes](../../../docs/standard/io/pipe-operations.md) (Operaciones de canalización de .NET Framework)  
  
 Describe las operaciones anónimas y de canalización con nombre de .NET Framework.  
  
-   [Memory-Mapped Files](../../../docs/standard/io/memory-mapped-files.md) (Archivos asignados a memoria)  
  
 Describe los archivos asignados a memoria, que incluyen el contenido de archivos en disco en memoria virtual. Puede usar archivos asignados a memoria para editar archivos muy grandes y crear memoria compartida para la comunicación entre procesos.

