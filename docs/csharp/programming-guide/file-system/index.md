---
title: 'Sistema de archivos y el Registro: Guía de programación de C#'
description: Vea artículos en los que se muestra cómo usar C# y .NET para realizar operaciones básicas en los archivos, las carpetas y el Registro.
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: 9e25058f5fb8ae49196c070dd426123e61a55e46
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301637"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="7c5c5-103">Sistema de archivos y el Registro (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7c5c5-103">File system and the registry (C# Programming Guide)</span></span>

<span data-ttu-id="7c5c5-104">En los artículos siguientes se muestra cómo usar C# y .NET para realizar diversas operaciones básicas en los archivos, las carpetas y el Registro.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-104">The following articles show how to use C# and .NET to perform various basic operations on files, folders, and the registry.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7c5c5-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7c5c5-105">In this section</span></span>

|<span data-ttu-id="7c5c5-106">**Título**</span><span class="sxs-lookup"><span data-stu-id="7c5c5-106">**Title**</span></span>|<span data-ttu-id="7c5c5-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7c5c5-107">**Description**</span></span>|
|---------------|---------------------|
|[<span data-ttu-id="7c5c5-108">Procedimiento para recorrer en iteración un árbol de directorio</span><span class="sxs-lookup"><span data-stu-id="7c5c5-108">How to iterate through a directory tree</span></span>](how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="7c5c5-109">Muestra cómo realizar una iteración manual a través de un árbol de directorio.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-109">Shows how to manually iterate through a directory tree.</span></span>|
|[<span data-ttu-id="7c5c5-110">Procedimiento para obtener información sobre archivos, carpetas y unidades</span><span class="sxs-lookup"><span data-stu-id="7c5c5-110">How to get information about files, folders, and drives</span></span>](how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="7c5c5-111">Muestra cómo recuperar información como las horas de creación y el tamaño, así como sobre archivos, carpetas y unidades.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-111">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|
|[<span data-ttu-id="7c5c5-112">Procedimiento para crear archivos o carpetas</span><span class="sxs-lookup"><span data-stu-id="7c5c5-112">How to create a file or folder</span></span>](how-to-create-a-file-or-folder.md)|<span data-ttu-id="7c5c5-113">Muestra cómo crear un archivo o una carpeta nuevos.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-113">Shows how to create a new file or folder.</span></span>|
|[<span data-ttu-id="7c5c5-114">Procedimiento para copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7c5c5-114">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="7c5c5-115">Muestra cómo copiar, eliminar y mover archivos y carpetas.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-115">Shows how to copy, delete and move files and folders.</span></span>|
|[<span data-ttu-id="7c5c5-116">Procedimiento para proporcionar un cuadro de diálogo de progreso para operaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="7c5c5-116">How to provide a progress dialog box for file operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="7c5c5-117">Muestra cómo mostrar un cuadro de diálogo de progreso estándar de Windows para determinadas operaciones de archivo.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-117">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|
|[<span data-ttu-id="7c5c5-118">Procedimiento para escribir en un archivo texto</span><span class="sxs-lookup"><span data-stu-id="7c5c5-118">How to write to a text file</span></span>](how-to-write-to-a-text-file.md)|<span data-ttu-id="7c5c5-119">Muestra cómo escribir en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-119">Shows how to write to a text file.</span></span>|
|[<span data-ttu-id="7c5c5-120">Procedimiento para leer de un archivo de texto</span><span class="sxs-lookup"><span data-stu-id="7c5c5-120">How to read from a text file</span></span>](how-to-read-from-a-text-file.md)|<span data-ttu-id="7c5c5-121">Muestra cómo leer de un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-121">Shows how to read from a text file.</span></span>|
|[<span data-ttu-id="7c5c5-122">Procedimiento para leer un archivo de texto línea a línea</span><span class="sxs-lookup"><span data-stu-id="7c5c5-122">How to read a text file one line at a time</span></span>](how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="7c5c5-123">Muestra cómo recuperar el texto de un archivo línea a línea.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-123">Shows how to retrieve text from a file one line at a time.</span></span>|
|[<span data-ttu-id="7c5c5-124">Procedimiento para crear una clave en el Registro</span><span class="sxs-lookup"><span data-stu-id="7c5c5-124">How to create a key in the registry</span></span>](how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="7c5c5-125">Muestra cómo escribir una clave en el registro del sistema.</span><span class="sxs-lookup"><span data-stu-id="7c5c5-125">Shows how to write a key to the system registry.</span></span>|

## <a name="related-sections"></a><span data-ttu-id="7c5c5-126">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="7c5c5-126">Related sections</span></span>

- [<span data-ttu-id="7c5c5-127">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="7c5c5-127">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="7c5c5-128">Procedimiento para copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7c5c5-128">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>](how-to-copy-delete-and-move-files-and-folders.md)
- [<span data-ttu-id="7c5c5-129">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7c5c5-129">C# Programming Guide</span></span>](../index.md)
- <xref:System.IO?displayProperty=nameWithType>
