---
title: "Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a4cfec46e0af0056a0de20a1ed83a370cd010055
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="051bc-102">Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="051bc-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="051bc-103">En los siguientes ejemplos se muestra cómo copiar, mover y eliminar archivos y carpetas de una manera sincrónica con las clases <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName> y <xref:System.IO.DirectoryInfo?displayProperty=fullName> desde el espacio de nombres <xref:System.IO?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="051bc-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName>, and <xref:System.IO.DirectoryInfo?displayProperty=fullName> classes from the <xref:System.IO?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="051bc-104">En estos ejemplos no se proporciona una barra de progreso ni ninguna otra interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="051bc-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="051bc-105">Si quiere proporcionar un cuadro de diálogo de progreso estándar, vea [Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="051bc-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="051bc-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=fullName> para proporcionar eventos que le permitan calcular el progreso al realizar operaciones en varios archivos.</span><span class="sxs-lookup"><span data-stu-id="051bc-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=fullName> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="051bc-107">Otro enfoque consiste en usar la invocación de plataforma para llamar a los métodos pertinentes relacionados con archivos en el shell de Windows.</span><span class="sxs-lookup"><span data-stu-id="051bc-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="051bc-108">Para obtener información sobre cómo realizar estas operaciones de archivo de forma asincrónica, vea [E/S de archivos asincrónica](https://msdn.microsoft.com/library/kztecsys).</span><span class="sxs-lookup"><span data-stu-id="051bc-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](https://msdn.microsoft.com/library/kztecsys).</span></span>  
  
## <a name="example"></a><span data-ttu-id="051bc-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="051bc-109">Example</span></span>  
 <span data-ttu-id="051bc-110">En el ejemplo siguiente se muestra cómo copiar archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="051bc-110">The following example shows how to copy files and directories.</span></span>  
  
 <span data-ttu-id="051bc-111">[!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="051bc-111">[!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="051bc-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="051bc-112">Example</span></span>  
 <span data-ttu-id="051bc-113">En el ejemplo siguiente se muestra cómo mover archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="051bc-113">The following example shows how to move files and directories.</span></span>  
  
 <span data-ttu-id="051bc-114">[!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="051bc-114">[!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="051bc-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="051bc-115">Example</span></span>  
 <span data-ttu-id="051bc-116">En el ejemplo siguiente se muestra cómo eliminar archivos y directorios.</span><span class="sxs-lookup"><span data-stu-id="051bc-116">The following example shows how to delete files and directories.</span></span>  
  
 <span data-ttu-id="051bc-117">[!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="051bc-117">[!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="051bc-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="051bc-118">See Also</span></span>  
 <span data-ttu-id="051bc-119"><xref:System.IO?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="051bc-119"><xref:System.IO?displayProperty=fullName></span></span>   
 <span data-ttu-id="051bc-120">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="051bc-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="051bc-121">[Registro y sistema de archivos (Guía de programación de C#)](index.md) </span><span class="sxs-lookup"><span data-stu-id="051bc-121">[File System and the Registry (C# Programming Guide)](index.md) </span></span>  
 <span data-ttu-id="051bc-122">[Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos](how-to-provide-a-progress-dialog-box-for-file-operations.md) </span><span class="sxs-lookup"><span data-stu-id="051bc-122">[How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md) </span></span>  
 <span data-ttu-id="051bc-123">[E/S de archivos y secuencias](https://msdn.microsoft.com/library/k3352a4t) </span><span class="sxs-lookup"><span data-stu-id="051bc-123">[File and Stream I/O](https://msdn.microsoft.com/library/k3352a4t) </span></span>  
 [<span data-ttu-id="051bc-124">Tareas de E/S comunes</span><span class="sxs-lookup"><span data-stu-id="051bc-124">Common I/O Tasks</span></span>](https://msdn.microsoft.com/library/ms404278)

