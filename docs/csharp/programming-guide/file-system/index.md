---
title: 'Sistema de archivos y el Registro: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: f160df456f1a3437e11de2d3660d158ae4d4bb67
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900562"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="85203-102">Sistema de archivos y el Registro (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="85203-102">File system and the registry (C# Programming Guide)</span></span>

<span data-ttu-id="85203-103">En los artículos siguientes se muestra cómo usar C# y .NET para realizar diversas operaciones básicas en los archivos, las carpetas y el Registro.</span><span class="sxs-lookup"><span data-stu-id="85203-103">The following articles show how to use C# and .NET to perform various basic operations on files, folders, and the registry.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="85203-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="85203-104">In this section</span></span>

|<span data-ttu-id="85203-105">**Título**</span><span class="sxs-lookup"><span data-stu-id="85203-105">**Title**</span></span>|<span data-ttu-id="85203-106">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="85203-106">**Description**</span></span>|
|---------------|---------------------|
|[<span data-ttu-id="85203-107">Procedimiento para recorrer en iteración un árbol de directorio</span><span class="sxs-lookup"><span data-stu-id="85203-107">How to iterate through a directory tree</span></span>](how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="85203-108">Muestra cómo realizar una iteración manual a través de un árbol de directorio.</span><span class="sxs-lookup"><span data-stu-id="85203-108">Shows how to manually iterate through a directory tree.</span></span>|
|[<span data-ttu-id="85203-109">Procedimiento para obtener información sobre archivos, carpetas y unidades</span><span class="sxs-lookup"><span data-stu-id="85203-109">How to get information about files, folders, and drives</span></span>](how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="85203-110">Muestra cómo recuperar información como las horas de creación y el tamaño, así como sobre archivos, carpetas y unidades.</span><span class="sxs-lookup"><span data-stu-id="85203-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|
|[<span data-ttu-id="85203-111">Procedimiento para crear archivos o carpetas</span><span class="sxs-lookup"><span data-stu-id="85203-111">How to create a file or folder</span></span>](how-to-create-a-file-or-folder.md)|<span data-ttu-id="85203-112">Muestra cómo crear un archivo o una carpeta nuevos.</span><span class="sxs-lookup"><span data-stu-id="85203-112">Shows how to create a new file or folder.</span></span>|
|[<span data-ttu-id="85203-113">Procedimiento para copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="85203-113">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="85203-114">Muestra cómo copiar, eliminar y mover archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="85203-114">Shows how to copy, delete and move files and folders.</span></span>|
|[<span data-ttu-id="85203-115">Procedimiento para proporcionar un cuadro de diálogo de progreso para operaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="85203-115">How to provide a progress dialog box for file operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="85203-116">Muestra cómo mostrar un cuadro de diálogo de progreso estándar de Windows para determinadas operaciones de archivo.</span><span class="sxs-lookup"><span data-stu-id="85203-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|
|[<span data-ttu-id="85203-117">Procedimiento para escribir en un archivo texto</span><span class="sxs-lookup"><span data-stu-id="85203-117">How to write to a text file</span></span>](how-to-write-to-a-text-file.md)|<span data-ttu-id="85203-118">Muestra cómo escribir en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="85203-118">Shows how to write to a text file.</span></span>|
|[<span data-ttu-id="85203-119">Procedimiento para leer de un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="85203-119">How to read from a text file</span></span>](how-to-read-from-a-text-file.md)|<span data-ttu-id="85203-120">Muestra cómo leer de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="85203-120">Shows how to read from a text file.</span></span>|
|[<span data-ttu-id="85203-121">Procedimiento para leer un archivo de texto línea a línea</span><span class="sxs-lookup"><span data-stu-id="85203-121">How to read a text file one line at a time</span></span>](how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="85203-122">Muestra cómo recuperar el texto de un archivo línea a línea.</span><span class="sxs-lookup"><span data-stu-id="85203-122">Shows how to retrieve text from a file one line at a time.</span></span>|
|[<span data-ttu-id="85203-123">Procedimiento para crear una clave en el Registro</span><span class="sxs-lookup"><span data-stu-id="85203-123">How to create a key in the registry</span></span>](how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="85203-124">Muestra cómo escribir una clave en el registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="85203-124">Shows how to write a key to the system registry.</span></span>|

## <a name="related-sections"></a><span data-ttu-id="85203-125">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="85203-125">Related sections</span></span>

- [<span data-ttu-id="85203-126">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="85203-126">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="85203-127">Procedimiento para copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="85203-127">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)
- [<span data-ttu-id="85203-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="85203-128">C# Programming Guide</span></span>](../index.md)
- <xref:System.IO?displayProperty=nameWithType>
