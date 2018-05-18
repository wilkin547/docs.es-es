---
title: 'Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 5debb2cbfa5ada45447e280169b9fe66d1a15a53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a>Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)
En los siguientes ejemplos se muestra cómo copiar, mover y eliminar archivos y carpetas de una manera sincrónica con las clases <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> y <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> desde el espacio de nombres <xref:System.IO?displayProperty=nameWithType>. En estos ejemplos no se proporciona una barra de progreso ni ninguna otra interfaz de usuario. Si quiere proporcionar un cuadro de diálogo de progreso estándar, vea [Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos](how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
 Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> para proporcionar eventos que le permitan calcular el progreso al realizar operaciones en varios archivos. Otro enfoque consiste en usar la invocación de plataforma para llamar a los métodos pertinentes relacionados con archivos en el shell de Windows. Para obtener información sobre cómo realizar estas operaciones de archivo de forma asincrónica, vea [E/S de archivos asincrónica](https://msdn.microsoft.com/library/kztecsys).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo copiar archivos y directorios.  
  
 [!code-csharp[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo mover archivos y directorios.  
  
 [!code-csharp[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo eliminar archivos y directorios.  
  
 [!code-csharp[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO?displayProperty=nameWithType>  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Registro y sistema de archivos (Guía de programación de C#)](index.md)  
 [Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos](how-to-provide-a-progress-dialog-box-for-file-operations.md)  
 [E/S de archivos y secuencias](https://msdn.microsoft.com/library/k3352a4t)  
 [Tareas de E/S comunes](https://msdn.microsoft.com/library/ms404278)
