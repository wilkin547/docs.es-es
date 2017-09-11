---
title: Clases utilizadas en el sistema de archivos y la E/S de archivos en .NET Framework (Visual Basic)
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
- file I/O classes
ms.assetid: 4a5ca924-eea8-4a95-a5f0-6ac10de276a3
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a87d2e6f87b92b5f66706095d3f485c080008e0f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="classes-used-in-net-framework-file-io-and-the-file-system-visual-basic"></a><span data-ttu-id="011a8-102">Clases utilizadas en el sistema de archivos y la E/S de archivos en .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="011a8-102">Classes Used in .NET Framework File I/O and the File System (Visual Basic)</span></span>
<span data-ttu-id="011a8-103">En las tablas siguientes se incluyen las clases usadas más comúnmente para las operaciones de E/S de archivos en .NET Framework, clasificadas en clases de E/S de archivos, clases usadas para crear secuencias y clases usadas para leer y escribir en secuencias.</span><span class="sxs-lookup"><span data-stu-id="011a8-103">The following tables list the classes commonly used for .NET Framework file I/O, categorized into file I/O classes, classes used for creating streams, and classes used to read and write to streams.</span></span>  
  
 <span data-ttu-id="011a8-104">Para entrar en la documentación de [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] y consultar una lista más completa, vea [Información general de la biblioteca de clases](https://msdn.microsoft.com/library/hfa3fa08).</span><span class="sxs-lookup"><span data-stu-id="011a8-104">To enter the [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] documentation and find a more comprehensive listing, see [Class Library Overview](https://msdn.microsoft.com/library/hfa3fa08).</span></span>  
  
## <a name="basic-io-classes-for-files-drives-and-directories"></a><span data-ttu-id="011a8-105">Clases básicas de E/S para archivos, unidades y directorios</span><span class="sxs-lookup"><span data-stu-id="011a8-105">Basic I/O Classes for Files, Drives, and Directories</span></span>  
 <span data-ttu-id="011a8-106">En la tabla siguiente se muestran y describen las clases principales usadas para las operaciones de E/S de archivos.</span><span class="sxs-lookup"><span data-stu-id="011a8-106">The following table lists and describes the main classes used for file I/O.</span></span>  
  
|<span data-ttu-id="011a8-107">Clase</span><span class="sxs-lookup"><span data-stu-id="011a8-107">Class</span></span>|<span data-ttu-id="011a8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="011a8-108">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.IO.Directory?displayProperty=fullName>|<span data-ttu-id="011a8-109">Proporciona métodos estáticos para crear, mover y enumerar en directorios y subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="011a8-109">Provides static methods for creating, moving, and enumerating through directories and subdirectories.</span></span>|  
|<xref:System.IO.DirectoryInfo?displayProperty=fullName>|<span data-ttu-id="011a8-110">Proporciona métodos de instancia para crear, mover y enumerar en directorios y subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="011a8-110">Provides instance methods for creating, moving, and enumerating through directories and subdirectories.</span></span>|  
|<xref:System.IO.DriveInfo?displayProperty=fullName>|<span data-ttu-id="011a8-111">Proporciona métodos de instancia para crear, mover y enumerar entre unidades.</span><span class="sxs-lookup"><span data-stu-id="011a8-111">Provides instance methods for creating, moving, and enumerating through drives.</span></span>|  
|<xref:System.IO.File?displayProperty=fullName>|<span data-ttu-id="011a8-112">Proporciona métodos estáticos para crear, copiar, eliminar, mover y abrir archivos, y ayuda en la creación de una `FileStream`.</span><span class="sxs-lookup"><span data-stu-id="011a8-112">Provides static methods for creating, copying, deleting, moving, and opening files, and aids in the creation of a `FileStream`.</span></span>|  
|<xref:System.IO.FileAccess?displayProperty=fullName>|<span data-ttu-id="011a8-113">Define constantes de acceso de lectura, de escritura y de lectura/escritura para un archivo.</span><span class="sxs-lookup"><span data-stu-id="011a8-113">Defines constants for read, write, or read/write access to a file.</span></span>|  
|<xref:System.IO.FileAttributes?displayProperty=fullName>|<span data-ttu-id="011a8-114">Proporciona atributos para archivos y directorios, como `Archive`, `Hidden` y `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="011a8-114">Provides attributes for files and directories such as `Archive`, `Hidden`, and `ReadOnly`.</span></span>|  
|<xref:System.IO.FileInfo?displayProperty=fullName>|<span data-ttu-id="011a8-115">Proporciona métodos estáticos para crear, copiar, eliminar, mover y abrir archivos, y ayuda en la creación de una `FileStream`.</span><span class="sxs-lookup"><span data-stu-id="011a8-115">Provides static methods for creating, copying, deleting, moving, and opening files, and aids in the creation of a `FileStream`.</span></span>|  
|<xref:System.IO.FileMode?displayProperty=fullName>|<span data-ttu-id="011a8-116">Controla cómo se abre un archivo.</span><span class="sxs-lookup"><span data-stu-id="011a8-116">Controls how a file is opened.</span></span> <span data-ttu-id="011a8-117">Este parámetro se especifica en muchos de los constructores para `FileStream` e `IsolatedStorageFileStream`, y para los métodos `Open` de <xref:System.IO.File> y <xref:System.IO.FileInfo>.</span><span class="sxs-lookup"><span data-stu-id="011a8-117">This parameter is specified in many of the constructors for `FileStream` and `IsolatedStorageFileStream`, and for the `Open` methods of <xref:System.IO.File> and <xref:System.IO.FileInfo>.</span></span>|  
|<xref:System.IO.FileShare?displayProperty=fullName>|<span data-ttu-id="011a8-118">Define las constantes para controlar el tipo de acceso que pueden tener otras secuencias de archivo al mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="011a8-118">Defines constants for controlling the type of access other file streams can have to the same file.</span></span>|  
|<xref:System.IO.Path?displayProperty=fullName>|<span data-ttu-id="011a8-119">Proporciona métodos y propiedades para procesar cadenas de directorio.</span><span class="sxs-lookup"><span data-stu-id="011a8-119">Provides methods and properties for processing directory strings.</span></span>|  
|<xref:System.Security.Permissions.FileIOPermission?displayProperty=fullName>|<span data-ttu-id="011a8-120">Controla el acceso a archivos y carpetas mediante la definición de los permisos <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> y <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>.</span><span class="sxs-lookup"><span data-stu-id="011a8-120">Controls the access of files and folders by defining <xref:System.Security.Permissions.FileIOPermissionAttribute.Read%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Write%2A>, <xref:System.Security.Permissions.FileIOPermissionAttribute.Append%2A> and <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> permissions.</span></span>|  
  
## <a name="classes-used-to-create-streams"></a><span data-ttu-id="011a8-121">Clases usadas para crear secuencias</span><span class="sxs-lookup"><span data-stu-id="011a8-121">Classes Used to Create Streams</span></span>  
 <span data-ttu-id="011a8-122">En la tabla siguiente se muestran y describen las clases principales usadas para crear secuencias.</span><span class="sxs-lookup"><span data-stu-id="011a8-122">The following table lists and describes the main classes used to create streams.</span></span>  
  
|<span data-ttu-id="011a8-123">Clase</span><span class="sxs-lookup"><span data-stu-id="011a8-123">Class</span></span>|<span data-ttu-id="011a8-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="011a8-124">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.IO.BufferedStream?displayProperty=fullName>|<span data-ttu-id="011a8-125">Agrega una capa de almacenamiento en búfer para las operaciones de lectura y escritura en otra secuencia.</span><span class="sxs-lookup"><span data-stu-id="011a8-125">Adds a buffering layer to read and write operations on another stream.</span></span>|  
|<xref:System.IO.FileStream?displayProperty=fullName>|<span data-ttu-id="011a8-126">Admite el acceso aleatorio a archivos a través de su método <xref:System.IO.FileStream.Seek%2A>.</span><span class="sxs-lookup"><span data-stu-id="011a8-126">Supports random access to files through its <xref:System.IO.FileStream.Seek%2A> method.</span></span> <span data-ttu-id="011a8-127"><xref:System.IO.FileStream> abre los archivos sincrónicamente de manera predeterminada, pero también admite operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="011a8-127"><xref:System.IO.FileStream> opens files synchronously by default but also supports asynchronous operation.</span></span>|  
|<xref:System.IO.MemoryStream?displayProperty=fullName>|<span data-ttu-id="011a8-128">Crea una secuencia cuya memoria auxiliar es la memoria, en lugar de un archivo.</span><span class="sxs-lookup"><span data-stu-id="011a8-128">Creates a stream whose backing store is memory, rather than a file.</span></span>|  
|<xref:System.Net.Sockets.NetworkStream?displayProperty=fullName>|<span data-ttu-id="011a8-129">Proporciona el flujo de datos subyacente para el acceso a través de la red.</span><span class="sxs-lookup"><span data-stu-id="011a8-129">Provides the underlying stream of data for network access.</span></span>|  
|<xref:System.Security.Cryptography.CryptoStream?displayProperty=fullName>|<span data-ttu-id="011a8-130">Define un flujo que vincula flujos de datos a transformaciones criptográficas.</span><span class="sxs-lookup"><span data-stu-id="011a8-130">Defines a stream that links data streams to cryptographic transformations.</span></span>|  
  
## <a name="classes-used-to-read-from-and-write-to-streams"></a><span data-ttu-id="011a8-131">Clases usadas para leer y escribir en secuencias</span><span class="sxs-lookup"><span data-stu-id="011a8-131">Classes Used to Read from and Write to Streams</span></span>  
 <span data-ttu-id="011a8-132">En la tabla siguiente se muestran las clases concretas usadas para leer y escribir en los archivos con secuencias.</span><span class="sxs-lookup"><span data-stu-id="011a8-132">The following table shows the specific classes used for reading from and writing to files with streams.</span></span>  
  
|<span data-ttu-id="011a8-133">**Clase**</span><span class="sxs-lookup"><span data-stu-id="011a8-133">**Class**</span></span>|<span data-ttu-id="011a8-134">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="011a8-134">**Description**</span></span>|  
|---------------|---------------------|  
|<xref:System.IO.BinaryReader?displayProperty=fullName>|<span data-ttu-id="011a8-135">Lee cadenas codificadas y tipos de datos primitivos de una secuencia <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="011a8-135">Reads encoded strings and primitive data types from a <xref:System.IO.FileStream>.</span></span>|  
|<xref:System.IO.BinaryWriter?displayProperty=fullName>|<span data-ttu-id="011a8-136">Escribe cadenas codificadas y tipos de datos primitivos en una secuencia <xref:System.IO.FileStream>.</span><span class="sxs-lookup"><span data-stu-id="011a8-136">Writes encoded strings and primitive data types to a <xref:System.IO.FileStream>.</span></span>|  
|<xref:System.IO.StreamReader?displayProperty=fullName>|<span data-ttu-id="011a8-137">Lee caracteres de <xref:System.IO.FileStream>, con el uso de <xref:System.IO.StreamReader.CurrentEncoding%2A> para convertir caracteres en bytes y caracteres a partir de bytes.</span><span class="sxs-lookup"><span data-stu-id="011a8-137">Reads characters from a <xref:System.IO.FileStream>, using <xref:System.IO.StreamReader.CurrentEncoding%2A> to convert characters to and from bytes.</span></span> <span data-ttu-id="011a8-138"><xref:System.IO.StreamReader> tiene un constructor que intenta confirmar la propiedad <xref:System.IO.StreamReader.CurrentEncoding%2A> correcta de un flujo determinado, en función de la presencia de un preámbulo específico de <xref:System.IO.StreamReader.CurrentEncoding%2A>, como una marca BOM.</span><span class="sxs-lookup"><span data-stu-id="011a8-138"><xref:System.IO.StreamReader> has a constructor that attempts to ascertain the correct <xref:System.IO.StreamReader.CurrentEncoding%2A> for a given stream, based on the presence of a <xref:System.IO.StreamReader.CurrentEncoding%2A>-specific preamble, such as a byte order mark.</span></span>|  
|<xref:System.IO.StreamWriter?displayProperty=fullName>|<span data-ttu-id="011a8-139">Escribe caracteres en `FileStream`, con el uso de <xref:System.IO.StreamWriter.Encoding%2A> para convertir caracteres en bytes.</span><span class="sxs-lookup"><span data-stu-id="011a8-139">Writes characters to a `FileStream`, using <xref:System.IO.StreamWriter.Encoding%2A> to convert characters to bytes.</span></span>|  
|<xref:System.IO.StringReader?displayProperty=fullName>|<span data-ttu-id="011a8-140">Lee caracteres de `String`.</span><span class="sxs-lookup"><span data-stu-id="011a8-140">Reads characters from a `String`.</span></span> <span data-ttu-id="011a8-141">El resultado puede ser una secuencia en cualquier codificación o `String`.</span><span class="sxs-lookup"><span data-stu-id="011a8-141">Output can be either a stream in any encoding or a `String`.</span></span>|  
|<xref:System.IO.StringWriter?displayProperty=fullName>|<span data-ttu-id="011a8-142">Escribe caracteres en `String`.</span><span class="sxs-lookup"><span data-stu-id="011a8-142">Writes characters to a `String`.</span></span> <span data-ttu-id="011a8-143">El resultado puede ser una secuencia en cualquier codificación o `String`.</span><span class="sxs-lookup"><span data-stu-id="011a8-143">Output can be either a stream in any encoding or a `String`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="011a8-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="011a8-144">See Also</span></span>  
 <span data-ttu-id="011a8-145">[Crear secuencias](https://msdn.microsoft.com/library/e4y2dch9) </span><span class="sxs-lookup"><span data-stu-id="011a8-145">[Composing Streams](https://msdn.microsoft.com/library/e4y2dch9) </span></span>  
 <span data-ttu-id="011a8-146">[E/S de archivos y secuencias](https://msdn.microsoft.com/library/k3352a4t) </span><span class="sxs-lookup"><span data-stu-id="011a8-146">[File and Stream I/O](https://msdn.microsoft.com/library/k3352a4t) </span></span>  
 <span data-ttu-id="011a8-147">[E/S de archivos asincrónica](https://msdn.microsoft.com/library/kztecsys) </span><span class="sxs-lookup"><span data-stu-id="011a8-147">[Asynchronous File I/O](https://msdn.microsoft.com/library/kztecsys) </span></span>  
 [<span data-ttu-id="011a8-148">Fundamentos del sistema de archivos y la E/S de archivos en .NET Framework (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="011a8-148">Basics of .NET Framework File I/O and the File System (Visual Basic)</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)

