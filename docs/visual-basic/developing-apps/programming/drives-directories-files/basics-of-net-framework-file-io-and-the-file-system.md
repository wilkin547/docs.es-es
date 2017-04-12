---
title: Fundamentos del sistema de archivos y la E/S de archivos en .NET Framework (Visual Basic) | Microsoft Docs
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- file access, file I/O in Visual Basic
- file attributes, determining
- streams, fundamental operations
- file permissions
- streams
- streams, definition
ms.assetid: 49d837c0-cf28-416f-8606-4d83d7b479ef
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9623d1c3076d622d69a0f7c4e711274f6e244023
ms.lasthandoff: 03/13/2017

---
# <a name="basics-of-net-framework-file-io-and-the-file-system-visual-basic"></a>Fundamentos del sistema de archivos y la E/S de archivos en .NET Framework (Visual Basic)
Las clases del espacio de nombres <xref:System.IO> se usan para trabajar con unidades, archivos y directorios.  
  
 El espacio de nombres <xref:System.IO> contiene las clases <xref:System.IO.File> y <xref:System.IO.Directory>, que proporcionan la funcionalidad [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] para manipular archivos y directorios. Dado que los métodos de estos objetos son miembros estáticos o compartidos, podrá usarlos directamente sin crear primero una instancia de la clase. A estas clases están asociadas las clases <xref:System.IO.FileInfo> y <xref:System.IO.DirectoryInfo>, que les resultarán familiares a los usuarios de la característica `My`. Para usar estas clases, debe usar los nombres completos o importar los espacios de nombres adecuados, incluidas las instrucciones `Imports` , al principio del código afectado. Para obtener más información, consulte [Instrucción Imports (Tipo y espacio de nombres de .NET)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
> [!NOTE]
>  Otros temas de esta sección usan el objeto `My.Computer.FileSystem` en lugar de las clases `System.IO` para trabajar con unidades, archivos y directorios. El objeto `My.Computer.FileSystem` está diseñado principalmente para su uso en programas de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Las clases `System.IO` están diseñadas para su uso en cualquier lenguaje que admita [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], incluido [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
## <a name="definition-of-a-stream"></a>Definición de una secuencia  
 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] usa secuencias para que sea posible leer archivos y escribir en ellos. Una secuencia se puede considerar un conjunto unidimensional de datos contiguos con un principio y un fin, en el que el cursor indica la posición actual en la secuencia.  
  
 ![El cursor muestra la posición actual de la secuencia de archivos.](../../../../visual-basic/developing-apps/programming/drives-directories-files/media/filestream.gif "FileStream")  
  
## <a name="stream-operations"></a>Operaciones con secuencias  
 Los datos contenidos en la secuencia pueden proceder de la memoria, de un archivo o de un socket TCP/IP. Las secuencias tienen una serie de operaciones fundamentales que se les pueden aplicar:  
  
-   Lectura. Puede leer de una secuencia transfiriendo los datos desde la secuencia a una estructura de datos, como una matriz de bytes.  
  
-   **Escritura**. Puede escribir en una secuencia transfiriendo datos desde un origen de datos a la secuencia.  
  
-   **Búsqueda**. Puede consultar y modificar su posición en la secuencia.  
  
 Para obtener más información, consulta [Composing Streams](https://msdn.microsoft.com/library/e4y2dch9).  
  
## <a name="types-of-streams"></a>Tipos de secuencias  
 En [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)], una secuencia se representa mediante la clase <xref:System.IO.Stream>, que constituye la clase abstracta para las demás secuencias. No se puede crear directamente una instancia de la clase <xref:System.IO.Stream>, sino que se debe usar una de las clases que implementa.  
  
 Hay muchos tipos de secuencias, pero para trabajar con la entrada/salida (E/S) de archivo, los tipos más importantes son la clase <xref:System.IO.FileStream>, que proporciona una manera de leer archivos y escribir en ellos, y la clase <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>, que proporciona una manera de crear archivos y directorios en almacenamiento aislado. Existen otras secuencias que se pueden usar al trabajar con E/S de archivo, entre las que se incluyen las siguientes:  
  
-   <xref:System.IO.BufferedStream>  
  
-   <xref:System.Security.Cryptography.CryptoStream>  
  
-   <xref:System.IO.MemoryStream>  
  
-   <xref:System.Net.Sockets.NetworkStream>.  
  
 En la tabla siguiente se enumeran las tareas que se suelen realizar con una secuencia:  
  
|Para|Vea|
|---|---|   
|Leer y escribir en un archivo de datos|[Cómo: Leer y escribir en un archivo de datos recién creado](https://msdn.microsoft.com/library/36b93480.aspx)|  
|Leer texto de un archivo|[Cómo: Leer texto de un archivo](https://msdn.microsoft.com/library/db5x7c0d.aspx)|  
|Escribir texto en un archivo|[Cómo: Escribir texto en un archivo](https://msdn.microsoft.com/library/6ka1wd3w.aspx)|  
|Leer caracteres de una cadena|[Cómo: Leer caracteres de una cadena](https://msdn.microsoft.com/library/9yyz8a6c.aspx)|  
|Escribir caracteres en una cadena|[Cómo: Escribir caracteres en una cadena](https://msdn.microsoft.com/library/z4kzt0dd.aspx)|  
|Cifrar datos|[Cifrar datos](https://msdn.microsoft.com/library/as0w18af.aspx)|  
|Descifrar datos|[Descifrar datos](https://msdn.microsoft.com/library/te15te69.aspx)|  
  
## <a name="file-access-and-attributes"></a>Acceso a archivos y atributos  
 Se puede controlar cómo se crean, se abren y se comparten los archivos con las enumeraciones <xref:System.IO.FileAccess>, <xref:System.IO.FileMode> y <xref:System.IO.FileShare>, que contienen las marcas usadas por los constructores de la clase <xref:System.IO.FileStream>. Por ejemplo, cuando se abre o se crea una clase <xref:System.IO.FileStream>, la enumeración <xref:System.IO.FileMode> permite especificar si el archivo se abre para anexarlo, si se crea un archivo nuevo en caso de que no exista el archivo especificado, si el archivo se sobrescribe, etc.  
  
 La enumeración <xref:System.IO.FileAttributes> permite la recopilación de información específica del archivo. La enumeración <xref:System.IO.FileAttributes> devuelve los atributos almacenados del archivo, por ejemplo, si está comprimido, cifrado u oculto, o bien si es de solo lectura, un archivo, un directorio, un archivo de sistema o un archivo temporal.  
  
 En la tabla siguiente se enumeran las tareas que implican acceso a archivos y atributos de archivo:  
  
|Para|Vea|  
|---|---|
|Abrir y anexar texto a un archivo de registro|[Cómo: Abrir y anexar a un archivo de registro](https://msdn.microsoft.com/library/3zc0w663.aspx)|  
|Determinar los atributos de un archivo|<xref:System.IO.FileAttributes>|  
  
## <a name="file-permissions"></a>Permisos de archivo  
 Es posible controlar el acceso a archivos y directorios mediante la clase <xref:System.Security.Permissions.FileIOPermission>. Esto puede ser especialmente importante para los desarrolladores que trabajan con formularios Web Forms, que de forma predeterminada se ejecutan en el contexto de una cuenta de usuario local especial denominada ASPNET, creada como parte de las instalaciones de [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] y [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] . Cuando este tipo de aplicación solicita acceso a un recurso, la cuenta de usuario ASPNET tiene permisos limitados, que pueden impedir que el usuario realice acciones como escribir en un archivo desde una aplicación web. Para obtener más información, vea [Permisos de seguridad](http://msdn.microsoft.com/en-us/b03757b4-e926-4196-b738-3733ced2bda0) y <xref:System.Security.Permissions.FileIOPermission>.  
  
## <a name="isolated-file-storage"></a>Almacenamiento aislado de archivos  
 El almacenamiento aislado es un intento de resolver los problemas creados al trabajar con archivos en los casos en que el usuario o el código carezcan de los permisos necesarios. El almacenamiento aislado asigna a cada usuario un compartimiento de datos, que puede contener uno o más almacenes. Los almacenes se pueden aislar entre sí por usuario y por ensamblado. Solo el usuario y el ensamblado que crearon un almacén tienen acceso a él. Un almacén actúa como un sistema de archivos virtual completo: dentro de un almacén, puede crear y manipular archivos y directorios.  
  
 En la tabla siguiente se enumeran las tareas que suelen estar asociadas con el almacenamiento aislado de archivos.  
  
|Para|Vea|
|---|---|  
|Crear un almacenamiento aislado|[Cómo: Obtener los almacenes de almacenamiento aislado](https://msdn.microsoft.com/library/k48a6h13.aspx)|  
|Enumerar almacenamientos aislados|[Cómo: Enumerar los almacenes de almacenamiento aislado](https://msdn.microsoft.com/library/c3dy613a.aspx)|  
|Eliminar un almacenamiento aislado|[Cómo: Eliminar almacenes de almacenamiento aislado](https://msdn.microsoft.com/library/5w71t104.aspx)|  
|Crear un archivo o directorio en almacenamiento aislado|[Cómo: Crear archivos y directorios en almacenamiento aislado](https://msdn.microsoft.com/library/6h2ws3ft.aspx)|  
|Buscar un archivo en almacenamiento aislado|[Cómo: Buscar archivos y directorios existentes en almacenamiento aislado](https://msdn.microsoft.com/library/zd5e2z84.aspx)|  
|Leer un archivo en almacenamiento aislado o escribir en él|[Cómo: Leer y escribir en archivos en almacenamiento aislado](https://msdn.microsoft.com/library/xf96a1wz.aspx)|  
|Eliminar un archivo o directorio en almacenamiento aislado|[Cómo: Eliminar archivos y directorios en almacenamiento aislado](https://msdn.microsoft.com/library/kx3852wf.aspx)|  
  
## <a name="file-events"></a>Eventos de archivo  
 El componente <xref:System.IO.FileSystemWatcher> permite ver los cambios en los archivos y los directorios del sistema o en cualquier equipo al que se tenga acceso de red. Por ejemplo, si se modifica un archivo, puede enviar una alerta a un usuario para indicarle que se ha realizado un cambio. Cuando se producen cambios, se generan uno o varios eventos que se almacenan en un búfer y se entregan al componente <xref:System.IO.FileSystemWatcher> para su procesamiento.  
  
## <a name="see-also"></a>Vea también  
 [Crear secuencias](https://msdn.microsoft.com/library/e4y2dch9)   
 [E/S de archivos y secuencias](https://msdn.microsoft.com/library/k3352a4t)   
 [E/S de archivos asincrónica](https://msdn.microsoft.com/library/kztecsys)   
 [Clases utilizadas en el sistema de archivos y la E/S de archivos en .NET Framework (Visual Basic)](../../../../visual-basic/developing-apps/programming/drives-directories-files/classes-used-in-net-framework-file-io-and-the-file-system.md)
