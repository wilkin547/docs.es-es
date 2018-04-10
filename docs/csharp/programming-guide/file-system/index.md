---
title: Registro y sistema de archivos (Guía de programación de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d1b4e3fa9b6c6da89abd242be855e9fb7c16dd6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="7eeb7-102">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7eeb7-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="7eeb7-103">Los temas siguientes tratan cómo usar C# y .NET Framework para realizar diversas operaciones básicas en los archivos, las carpetas y el Registro.</span><span class="sxs-lookup"><span data-stu-id="7eeb7-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7eeb7-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7eeb7-104">In This Section</span></span>  
  
|<span data-ttu-id="7eeb7-105">**Título**</span><span class="sxs-lookup"><span data-stu-id="7eeb7-105">**Title**</span></span>|<span data-ttu-id="7eeb7-106">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7eeb7-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="7eeb7-107">Cómo: Recorrer en iteración un árbol de directorio</span><span class="sxs-lookup"><span data-stu-id="7eeb7-107">How to: Iterate Through a Directory Tree</span></span>](../../../csharp/programming-guide/file-system/how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="7eeb7-108">Muestra cómo realizar una iteración manual a través de un árbol de directorio.</span><span class="sxs-lookup"><span data-stu-id="7eeb7-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="7eeb7-109">Cómo: Obtener información sobre archivos, carpetas y unidades</span><span class="sxs-lookup"><span data-stu-id="7eeb7-109">How to: Get Information About Files, Folders, and Drives</span></span>](../../../csharp/programming-guide/file-system/how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="7eeb7-110">Muestra cómo recuperar información como las horas de creación y el tamaño, así como sobre archivos, carpetas y unidades.</span><span class="sxs-lookup"><span data-stu-id="7eeb7-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="7eeb7-111">Cómo: Crear archivos o carpetas</span><span class="sxs-lookup"><span data-stu-id="7eeb7-111">How to: Create a File or Folder</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-file-or-folder.md)|<span data-ttu-id="7eeb7-112">Muestra cómo crear un archivo o una carpeta nuevos.</span><span class="sxs-lookup"><span data-stu-id="7eeb7-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="7eeb7-113">Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7eeb7-113">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="7eeb7-114">Muestra cómo copiar, eliminar y mover archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="7eeb7-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="7eeb7-115">Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="7eeb7-115">How to: Provide a Progress Dialog Box for File Operations</span></span>](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="7eeb7-116">Muestra cómo mostrar un cuadro de diálogo de progreso estándar de Windows para determinadas operaciones de archivo.</span><span class="sxs-lookup"><span data-stu-id="7eeb7-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="7eeb7-117">Cómo: Escribir en un archivo texto</span><span class="sxs-lookup"><span data-stu-id="7eeb7-117">How to: Write to a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md)|<span data-ttu-id="7eeb7-118">Muestra cómo escribir en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7eeb7-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="7eeb7-119">Cómo: Leer de un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="7eeb7-119">How to: Read From a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-read-from-a-text-file.md)|<span data-ttu-id="7eeb7-120">Muestra cómo leer de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7eeb7-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="7eeb7-121">Cómo: Leer un archivo de texto línea a línea</span><span class="sxs-lookup"><span data-stu-id="7eeb7-121">How to: Read a Text File One Line at a Time</span></span>](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="7eeb7-122">Muestra cómo recuperar el texto de un archivo línea a línea.</span><span class="sxs-lookup"><span data-stu-id="7eeb7-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="7eeb7-123">Cómo: Crear una clave en el Registro</span><span class="sxs-lookup"><span data-stu-id="7eeb7-123">How to: Create a Key In the Registry</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="7eeb7-124">Muestra cómo escribir una clave en el registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="7eeb7-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="7eeb7-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7eeb7-125">Related Sections</span></span>  
 [<span data-ttu-id="7eeb7-126">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="7eeb7-126">File and Stream I/O</span></span>](https://msdn.microsoft.com/library/k3352a4t)  
  
 [<span data-ttu-id="7eeb7-127">Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7eeb7-127">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)  
  
 [<span data-ttu-id="7eeb7-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7eeb7-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
  
 [<span data-ttu-id="7eeb7-129">Archivos, carpetas y unidades</span><span class="sxs-lookup"><span data-stu-id="7eeb7-129">Files, Folders and Drives</span></span>](../../../csharp/programming-guide/file-system/index.md)  
  
 <xref:System.IO?displayProperty=nameWithType>
