---
title: 'Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: a9c5b1dc35878ac2e50a7c4ec72251885704fea6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43858348"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="a9ce3-102">Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a9ce3-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="a9ce3-103">En los siguientes ejemplos se muestra cómo copiar, mover y eliminar archivos y carpetas de una manera sincrónica con las clases <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> y <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> desde el espacio de nombres <xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="a9ce3-104">En estos ejemplos no se proporciona una barra de progreso ni ninguna otra interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="a9ce3-105">Si quiere proporcionar un cuadro de diálogo de progreso estándar, vea [Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="a9ce3-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="a9ce3-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> para proporcionar eventos que le permitan calcular el progreso al realizar operaciones en varios archivos.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="a9ce3-107">Otro enfoque consiste en usar la invocación de plataforma para llamar a los métodos pertinentes relacionados con archivos en el shell de Windows.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="a9ce3-108">Para obtener información sobre cómo realizar estas operaciones de archivo de forma asincrónica, vea [E/S de archivos asincrónica](../../../standard/io/asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="a9ce3-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](../../../standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9ce3-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9ce3-109">Example</span></span>  
 <span data-ttu-id="a9ce3-110">En el ejemplo siguiente se muestra cómo copiar archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="a9ce3-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9ce3-111">Example</span></span>  
 <span data-ttu-id="a9ce3-112">En el ejemplo siguiente se muestra cómo mover archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="a9ce3-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a9ce3-113">Example</span></span>  
 <span data-ttu-id="a9ce3-114">En el ejemplo siguiente se muestra cómo eliminar archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="a9ce3-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a9ce3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9ce3-115">See Also</span></span>

- <xref:System.IO?displayProperty=nameWithType>  
- [<span data-ttu-id="a9ce3-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a9ce3-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a9ce3-117">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a9ce3-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)  
- [<span data-ttu-id="a9ce3-118">Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="a9ce3-118">How to: Provide a Progress Dialog Box for File Operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)  
- [<span data-ttu-id="a9ce3-119">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="a9ce3-119">File and Stream I/O</span></span>](../../../standard/io/index.md)  
- [<span data-ttu-id="a9ce3-120">Tareas de E/S comunes</span><span class="sxs-lookup"><span data-stu-id="a9ce3-120">Common I/O Tasks</span></span>](../../../standard/io/common-i-o-tasks.md)
