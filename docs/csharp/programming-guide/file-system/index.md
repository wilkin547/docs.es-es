---
title: 'Sistema de archivos y el Registro: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: 2540c816a102a7f11f1f103b993194cccf0f4688
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75704526"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="31fe9-102">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="31fe9-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="31fe9-103">Los temas siguientes tratan cómo usar C# y .NET Framework para realizar diversas operaciones básicas en los archivos, las carpetas y el Registro.</span><span class="sxs-lookup"><span data-stu-id="31fe9-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31fe9-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="31fe9-104">In This Section</span></span>  
  
|<span data-ttu-id="31fe9-105">**Título**</span><span class="sxs-lookup"><span data-stu-id="31fe9-105">**Title**</span></span>|<span data-ttu-id="31fe9-106">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="31fe9-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="31fe9-107">Procedimiento para recorrer en iteración un árbol de directorio</span><span class="sxs-lookup"><span data-stu-id="31fe9-107">How to iterate through a directory tree</span></span>](./how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="31fe9-108">Muestra cómo realizar una iteración manual a través de un árbol de directorio.</span><span class="sxs-lookup"><span data-stu-id="31fe9-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="31fe9-109">Procedimiento para obtener información sobre archivos, carpetas y unidades</span><span class="sxs-lookup"><span data-stu-id="31fe9-109">How to get information about files, folders, and drives</span></span>](./how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="31fe9-110">Muestra cómo recuperar información como las horas de creación y el tamaño, así como sobre archivos, carpetas y unidades.</span><span class="sxs-lookup"><span data-stu-id="31fe9-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="31fe9-111">Procedimiento para crear archivos o carpetas</span><span class="sxs-lookup"><span data-stu-id="31fe9-111">How to create a file or folder</span></span>](./how-to-create-a-file-or-folder.md)|<span data-ttu-id="31fe9-112">Muestra cómo crear un archivo o una carpeta nuevos.</span><span class="sxs-lookup"><span data-stu-id="31fe9-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="31fe9-113">Procedimiento para copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="31fe9-113">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="31fe9-114">Muestra cómo copiar, eliminar y mover archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="31fe9-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="31fe9-115">Procedimiento para proporcionar un cuadro de diálogo de progreso para operaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="31fe9-115">How to provide a progress dialog box for file operations</span></span>](./how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="31fe9-116">Muestra cómo mostrar un cuadro de diálogo de progreso estándar de Windows para determinadas operaciones de archivo.</span><span class="sxs-lookup"><span data-stu-id="31fe9-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="31fe9-117">Procedimiento para escribir en un archivo texto</span><span class="sxs-lookup"><span data-stu-id="31fe9-117">How to write to a text file</span></span>](./how-to-write-to-a-text-file.md)|<span data-ttu-id="31fe9-118">Muestra cómo escribir en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="31fe9-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="31fe9-119">Procedimiento para leer de un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="31fe9-119">How to read from a text file</span></span>](./how-to-read-from-a-text-file.md)|<span data-ttu-id="31fe9-120">Muestra cómo leer de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="31fe9-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="31fe9-121">Procedimiento para leer un archivo de texto línea a línea</span><span class="sxs-lookup"><span data-stu-id="31fe9-121">How to read a text file one line at a time</span></span>](./how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="31fe9-122">Muestra cómo recuperar el texto de un archivo línea a línea.</span><span class="sxs-lookup"><span data-stu-id="31fe9-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="31fe9-123">Procedimiento para crear una clave en el Registro</span><span class="sxs-lookup"><span data-stu-id="31fe9-123">How to create a key in the registry</span></span>](./how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="31fe9-124">Muestra cómo escribir una clave en el registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="31fe9-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="31fe9-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="31fe9-125">Related Sections</span></span>  
 [<span data-ttu-id="31fe9-126">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="31fe9-126">File and Stream I/O</span></span>](../../../standard/io/index.md)  
  
 [<span data-ttu-id="31fe9-127">Procedimiento para copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="31fe9-127">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](./how-to-copy-delete-and-move-files-and-folders.md)
  
 [<span data-ttu-id="31fe9-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="31fe9-128">C# Programming Guide</span></span>](../index.md)  
  
 [<span data-ttu-id="31fe9-129">Archivos, carpetas y unidades</span><span class="sxs-lookup"><span data-stu-id="31fe9-129">Files, Folders and Drives</span></span>](./index.md)  
  
 <xref:System.IO?displayProperty=nameWithType>
