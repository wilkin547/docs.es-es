---
title: 'Sistema de archivos y el Registro: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: ef6c1da09ea0435643caba0f5e2819c064f8db01
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589908"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="9891d-102">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9891d-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="9891d-103">Los temas siguientes tratan cómo usar C# y .NET Framework para realizar diversas operaciones básicas en los archivos, las carpetas y el Registro.</span><span class="sxs-lookup"><span data-stu-id="9891d-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9891d-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="9891d-104">In This Section</span></span>  
  
|<span data-ttu-id="9891d-105">**Título**</span><span class="sxs-lookup"><span data-stu-id="9891d-105">**Title**</span></span>|<span data-ttu-id="9891d-106">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9891d-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="9891d-107">Cómo: Recorrer en iteración un árbol de directorio</span><span class="sxs-lookup"><span data-stu-id="9891d-107">How to: Iterate Through a Directory Tree</span></span>](./how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="9891d-108">Muestra cómo realizar una iteración manual a través de un árbol de directorio.</span><span class="sxs-lookup"><span data-stu-id="9891d-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="9891d-109">Cómo: Obtener información sobre archivos, carpetas y unidades</span><span class="sxs-lookup"><span data-stu-id="9891d-109">How to: Get Information About Files, Folders, and Drives</span></span>](./how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="9891d-110">Muestra cómo recuperar información como las horas de creación y el tamaño, así como sobre archivos, carpetas y unidades.</span><span class="sxs-lookup"><span data-stu-id="9891d-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="9891d-111">Cómo: Creación de un archivo o una carpeta</span><span class="sxs-lookup"><span data-stu-id="9891d-111">How to: Create a File or Folder</span></span>](./how-to-create-a-file-or-folder.md)|<span data-ttu-id="9891d-112">Muestra cómo crear un archivo o una carpeta nuevos.</span><span class="sxs-lookup"><span data-stu-id="9891d-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="9891d-113">Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9891d-113">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="9891d-114">Muestra cómo copiar, eliminar y mover archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="9891d-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="9891d-115">Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="9891d-115">How to: Provide a Progress Dialog Box for File Operations</span></span>](./how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="9891d-116">Muestra cómo mostrar un cuadro de diálogo de progreso estándar de Windows para determinadas operaciones de archivo.</span><span class="sxs-lookup"><span data-stu-id="9891d-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="9891d-117">Cómo: Escribir en un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="9891d-117">How to: Write to a Text File</span></span>](./how-to-write-to-a-text-file.md)|<span data-ttu-id="9891d-118">Muestra cómo escribir en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="9891d-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="9891d-119">Cómo: Leer de un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="9891d-119">How to: Read From a Text File</span></span>](./how-to-read-from-a-text-file.md)|<span data-ttu-id="9891d-120">Muestra cómo leer de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="9891d-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="9891d-121">Cómo: Leer un archivo de texto línea a línea</span><span class="sxs-lookup"><span data-stu-id="9891d-121">How to: Read a Text File One Line at a Time</span></span>](./how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="9891d-122">Muestra cómo recuperar el texto de un archivo línea a línea.</span><span class="sxs-lookup"><span data-stu-id="9891d-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="9891d-123">Cómo: Crear una clave en el Registro</span><span class="sxs-lookup"><span data-stu-id="9891d-123">How to: Create a Key In the Registry</span></span>](./how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="9891d-124">Muestra cómo escribir una clave en el registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="9891d-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="9891d-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="9891d-125">Related Sections</span></span>  
 [<span data-ttu-id="9891d-126">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="9891d-126">File and Stream I/O</span></span>](../../../standard/io/index.md)  
  
 [<span data-ttu-id="9891d-127">Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9891d-127">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)  
  
 [<span data-ttu-id="9891d-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9891d-128">C# Programming Guide</span></span>](../index.md)  
  
 [<span data-ttu-id="9891d-129">Archivos, carpetas y unidades</span><span class="sxs-lookup"><span data-stu-id="9891d-129">Files, Folders and Drives</span></span>](./index.md)  
  
 <xref:System.IO?displayProperty=nameWithType>
