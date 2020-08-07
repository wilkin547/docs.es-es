---
title: 'Procedimiento Copiar, eliminar y mover archivos y carpeta: Guía de programación de C#'
description: Aprenda a copiar, eliminar y mover archivos y carpetas mediante las clases File, Directory, FileInfo y DirectoryInfo.
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 208502651080f4fd614e34d1bf5b088dfb1207a6
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303366"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="34dbc-103">Procedimiento Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="34dbc-103">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>
<span data-ttu-id="34dbc-104">En los siguientes ejemplos se muestra cómo copiar, mover y eliminar archivos y carpetas de una manera sincrónica con las clases <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> y <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> desde el espacio de nombres <xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="34dbc-104">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="34dbc-105">En estos ejemplos no se proporciona una barra de progreso ni ninguna otra interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="34dbc-105">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="34dbc-106">Si quiere proporcionar un cuadro de diálogo de progreso estándar, consulte [Procedimiento Proporcionar un cuadro de diálogo de progreso para operaciones de archivos](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="34dbc-106">If you want to provide a standard progress dialog box, see [How to provide a progress dialog box for file operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="34dbc-107">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> para proporcionar eventos que le permitan calcular el progreso al realizar operaciones en varios archivos.</span><span class="sxs-lookup"><span data-stu-id="34dbc-107">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="34dbc-108">Otro enfoque consiste en usar la invocación de plataforma para llamar a los métodos pertinentes relacionados con archivos en el shell de Windows.</span><span class="sxs-lookup"><span data-stu-id="34dbc-108">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="34dbc-109">Para obtener información sobre cómo realizar estas operaciones de archivo de forma asincrónica, vea [E/S de archivos asincrónica](../../../standard/io/asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="34dbc-109">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](../../../standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="34dbc-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34dbc-110">Example</span></span>  
 <span data-ttu-id="34dbc-111">En el ejemplo siguiente se muestra cómo copiar archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="34dbc-111">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#7)]  
  
## <a name="example"></a><span data-ttu-id="34dbc-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34dbc-112">Example</span></span>  
 <span data-ttu-id="34dbc-113">En el ejemplo siguiente se muestra cómo mover archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="34dbc-113">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#8)]  
  
## <a name="example"></a><span data-ttu-id="34dbc-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34dbc-114">Example</span></span>  
 <span data-ttu-id="34dbc-115">En el ejemplo siguiente se muestra cómo eliminar archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="34dbc-115">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="34dbc-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="34dbc-116">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="34dbc-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="34dbc-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="34dbc-118">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="34dbc-118">File System and the Registry (C# Programming Guide)</span></span>](index.md)
- [<span data-ttu-id="34dbc-119">Procedimiento para proporcionar un cuadro de diálogo de progreso para operaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="34dbc-119">How to provide a progress dialog box for file operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [<span data-ttu-id="34dbc-120">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="34dbc-120">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="34dbc-121">Tareas de E/S comunes</span><span class="sxs-lookup"><span data-stu-id="34dbc-121">Common I/O Tasks</span></span>](../../../standard/io/common-i-o-tasks.md)
