---
title: "Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 56383873674998fc0d6417a2abf4fa72e498f08f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="93e30-102">Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="93e30-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="93e30-103">En los siguientes ejemplos se muestra cómo copiar, mover y eliminar archivos y carpetas de una manera sincrónica con las clases <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> y <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> desde el espacio de nombres <xref:System.IO?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="93e30-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="93e30-104">En estos ejemplos no se proporciona una barra de progreso ni ninguna otra interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="93e30-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="93e30-105">Si quiere proporcionar un cuadro de diálogo de progreso estándar, vea [Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="93e30-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="93e30-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> para proporcionar eventos que le permitan calcular el progreso al realizar operaciones en varios archivos.</span><span class="sxs-lookup"><span data-stu-id="93e30-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="93e30-107">Otro enfoque consiste en usar la invocación de plataforma para llamar a los métodos pertinentes relacionados con archivos en el shell de Windows.</span><span class="sxs-lookup"><span data-stu-id="93e30-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="93e30-108">Para obtener información sobre cómo realizar estas operaciones de archivo de forma asincrónica, vea [E/S de archivos asincrónica](https://msdn.microsoft.com/library/kztecsys).</span><span class="sxs-lookup"><span data-stu-id="93e30-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](https://msdn.microsoft.com/library/kztecsys).</span></span>  
  
## <a name="example"></a><span data-ttu-id="93e30-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93e30-109">Example</span></span>  
 <span data-ttu-id="93e30-110">En el ejemplo siguiente se muestra cómo copiar archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="93e30-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="93e30-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93e30-111">Example</span></span>  
 <span data-ttu-id="93e30-112">En el ejemplo siguiente se muestra cómo mover archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="93e30-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="93e30-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93e30-113">Example</span></span>  
 <span data-ttu-id="93e30-114">En el ejemplo siguiente se muestra cómo eliminar archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="93e30-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="93e30-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="93e30-115">See Also</span></span>  
 <xref:System.IO?displayProperty=nameWithType>  
 [<span data-ttu-id="93e30-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="93e30-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="93e30-117">Registro y sistema de archivos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="93e30-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)  
 [<span data-ttu-id="93e30-118">Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos</span><span class="sxs-lookup"><span data-stu-id="93e30-118">How to: Provide a Progress Dialog Box for File Operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)  
 [<span data-ttu-id="93e30-119">E/S de archivos y secuencias</span><span class="sxs-lookup"><span data-stu-id="93e30-119">File and Stream I/O</span></span>](https://msdn.microsoft.com/library/k3352a4t)  
 [<span data-ttu-id="93e30-120">Tareas de E/S comunes</span><span class="sxs-lookup"><span data-stu-id="93e30-120">Common I/O Tasks</span></span>](https://msdn.microsoft.com/library/ms404278)
