---
title: 'Procedimiento Obtener información sobre archivos, carpetas y unidades: Guía de programación de C#'
description: Aprenda a obtener información sobre archivos, carpetas y unidades. Vea un ejemplo de código y examine los recursos adicionales disponibles.
ms.date: 07/20/2015
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
ms.openlocfilehash: 7cbaea4dc5381a2ebeb97ce2797ffe850488e126
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170459"
---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a><span data-ttu-id="640d7-104">Procedimiento Obtener información sobre archivos, carpetas y unidades (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="640d7-104">How to get information about files, folders, and drives  (C# Programming Guide)</span></span>

<span data-ttu-id="640d7-105">En .NET, puede acceder a información del sistema de archivos mediante las clases siguientes:</span><span class="sxs-lookup"><span data-stu-id="640d7-105">In .NET, you can access file system information by using the following classes:</span></span>  
  
- <xref:System.IO.FileInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DriveInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.Directory?displayProperty=nameWithType>  
  
- <xref:System.IO.File?displayProperty=nameWithType>  
  
 <span data-ttu-id="640d7-106">Las clases <xref:System.IO.FileInfo> y <xref:System.IO.DirectoryInfo> representan un archivo o directorio y contienen propiedades que exponen muchos de los atributos de archivo admitidos por el sistema de archivos NTFS.</span><span class="sxs-lookup"><span data-stu-id="640d7-106">The <xref:System.IO.FileInfo> and <xref:System.IO.DirectoryInfo> classes represent a file or directory and contain properties that expose many of the file attributes that are supported by the NTFS file system.</span></span> <span data-ttu-id="640d7-107">También contienen métodos para abrir, cerrar, mover y eliminar archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="640d7-107">They also contain methods for opening, closing, moving, and deleting files and folders.</span></span> <span data-ttu-id="640d7-108">Para crear instancias de estas clases, pase una cadena que represente el nombre del archivo, carpeta o unidad en el constructor:</span><span class="sxs-lookup"><span data-stu-id="640d7-108">You can create instances of these classes by passing a string that represents the name of the file, folder, or drive in to the constructor:</span></span>  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 <span data-ttu-id="640d7-109">También puede obtener los nombres de archivos, carpetas o unidades mediante llamadas a <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType> y <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="640d7-109">You can also obtain the names of files, folders, or drives by using calls to <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType>, <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType>, and <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="640d7-110">Las clases <xref:System.IO.Directory?displayProperty=nameWithType> y <xref:System.IO.File?displayProperty=nameWithType> proporcionan métodos estáticos para recuperar información sobre directorios y archivos.</span><span class="sxs-lookup"><span data-stu-id="640d7-110">The <xref:System.IO.Directory?displayProperty=nameWithType> and <xref:System.IO.File?displayProperty=nameWithType> classes provide static methods for retrieving information about directories and files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="640d7-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="640d7-111">Example</span></span>  

 <span data-ttu-id="640d7-112">En el ejemplo siguiente se muestran diversas maneras de obtener acceso a información sobre archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="640d7-112">The following example shows various ways to access information about files and folders.</span></span>  
  
 [!code-csharp[csFilesandFolders#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#6)]  
  
## <a name="robust-programming"></a><span data-ttu-id="640d7-113">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="640d7-113">Robust Programming</span></span>  

 <span data-ttu-id="640d7-114">Al procesar cadenas de ruta de acceso especificadas por el usuario, también debe controlar las excepciones para las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="640d7-114">When you process user-specified path strings, you should also handle exceptions for the following conditions:</span></span>  
  
- <span data-ttu-id="640d7-115">El nombre del archivo es incorrecto.</span><span class="sxs-lookup"><span data-stu-id="640d7-115">The file name is malformed.</span></span> <span data-ttu-id="640d7-116">Por ejemplo, contiene caracteres no válidos o solo espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="640d7-116">For example, it contains invalid characters or only white space.</span></span>  
  
- <span data-ttu-id="640d7-117">El nombre del archivo es nulo.</span><span class="sxs-lookup"><span data-stu-id="640d7-117">The file name is null.</span></span>  
  
- <span data-ttu-id="640d7-118">La longitud del nombre de archivo es superior a la longitud máxima definida por el sistema.</span><span class="sxs-lookup"><span data-stu-id="640d7-118">The file name is longer than the system-defined maximum length.</span></span>  
  
- <span data-ttu-id="640d7-119">El nombre de archivo contiene un signo de dos puntos (:).</span><span class="sxs-lookup"><span data-stu-id="640d7-119">The file name contains a colon (:).</span></span>  
  
 <span data-ttu-id="640d7-120">Si la aplicación no tiene permisos suficientes para leer el archivo especificado, el método `Exists` devuelve `false` con independencia de si existe una ruta de acceso; el método no produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="640d7-120">If the application does not have sufficient permissions to read the specified file, the `Exists` method returns `false` regardless of whether a path exists; the method does not throw an exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="640d7-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="640d7-121">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="640d7-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="640d7-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="640d7-123">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="640d7-123">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
