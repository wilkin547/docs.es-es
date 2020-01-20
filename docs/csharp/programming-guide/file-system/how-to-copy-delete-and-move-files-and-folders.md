---
title: 'Procedimiento Copiar, eliminar y mover archivos y carpeta: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 662f0ab3b9e69aa8bfb0085f42f577b850029e4d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712278"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="911dd-102">Procedimiento Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="911dd-102">How to copy, delete, and move files and folders (C# Programming Guide)</span></span>
<span data-ttu-id="911dd-103">En los siguientes ejemplos se muestra cómo copiar, mover y eliminar archivos y carpetas de una manera sincrónica con las clases <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> y <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> desde el espacio de nombres <xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="911dd-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="911dd-104">En estos ejemplos no se proporciona una barra de progreso ni ninguna otra interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="911dd-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="911dd-105">Si quiere proporcionar un cuadro de diálogo de progreso estándar, consulte [Procedimiento Proporcionar un cuadro de diálogo de progreso para operaciones de archivos](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="911dd-105">If you want to provide a standard progress dialog box, see [How to provide a progress dialog box for file operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="911dd-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> para proporcionar eventos que le permitan calcular el progreso al realizar operaciones en varios archivos.</span><span class="sxs-lookup"><span data-stu-id="911dd-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="911dd-107">Otro enfoque consiste en usar la invocación de plataforma para llamar a los métodos pertinentes relacionados con archivos en el shell de Windows.</span><span class="sxs-lookup"><span data-stu-id="911dd-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="911dd-108">Para obtener información sobre cómo realizar estas operaciones de archivo de forma asincrónica, vea [E/S de archivos asincrónica](../../../standard/io/asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="911dd-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](../../../standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="911dd-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="911dd-109">Example</span></span>  
 <span data-ttu-id="911dd-110">En el ejemplo siguiente se muestra cómo copiar archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="911dd-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#7)]  
  
## <a name="example"></a><span data-ttu-id="911dd-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="911dd-111">Example</span></span>  
 <span data-ttu-id="911dd-112">En el ejemplo siguiente se muestra cómo mover archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="911dd-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#8)]  
  
## <a name="example"></a><span data-ttu-id="911dd-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="911dd-113">Example</span></span>  
 <span data-ttu-id="911dd-114">En el ejemplo siguiente se muestra cómo eliminar archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="911dd-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="911dd-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="911dd-115">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="911dd-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="911dd-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="911dd-117">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="911dd-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)
- [<span data-ttu-id="911dd-118">Procedimiento para proporcionar un cuadro de diálogo de progreso para operaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="911dd-118">How to provide a progress dialog box for file operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [<span data-ttu-id="911dd-119">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="911dd-119">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="911dd-120">Tareas de E/S comunes</span><span class="sxs-lookup"><span data-stu-id="911dd-120">Common I/O Tasks</span></span>](../../../standard/io/common-i-o-tasks.md)
