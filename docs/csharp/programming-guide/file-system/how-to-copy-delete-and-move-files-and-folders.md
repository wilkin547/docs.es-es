---
title: "Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#) | Microsoft Docs"
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c7e9a170882c4e8dbb04dc014642a28ad4365e39
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a>Cómo: Copiar, eliminar y mover archivos y carpetas (Guía de programación de C#)
En los ejemplos siguientes se muestra cómo copiar, mover y eliminar archivos y carpetas de forma sincrónica mediante las clases <xref:System.IO.File?displayProperty=fullName>, <xref:System.IO.Directory?displayProperty=fullName>, <xref:System.IO.FileInfo?displayProperty=fullName> y <xref:System.IO.DirectoryInfo?displayProperty=fullName> del espacio de nombres <xref:System.IO?displayProperty=fullName>. En estos ejemplos no se proporciona una barra de progreso ni ninguna otra interfaz de usuario. Si quiere proporcionar un cuadro de diálogo de progreso estándar, vea [Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos](how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
 Use <xref:System.IO.FileSystemWatcher?displayProperty=fullName> para proporcionar eventos que le permitan calcular el progreso al realizar operaciones en varios archivos. Otro enfoque consiste en usar la invocación de plataforma para llamar a los métodos pertinentes relacionados con archivos en el shell de Windows. Para obtener información sobre cómo realizar estas operaciones de archivo de forma asincrónica, vea [E/S de archivos asincrónica](https://msdn.microsoft.com/library/kztecsys).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo copiar archivos y directorios.  
  
 [!code-cs[csFilesandFolders#7](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo mover archivos y directorios.  
  
 [!code-cs[csFilesandFolders#8](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_2.cs)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo eliminar archivos y directorios.  
  
 [!code-cs[csFilesandFolders#9](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-copy-delete-and-move-files-and-folders_3.cs)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO?displayProperty=fullName>   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Registro y sistema de archivos (Guía de programación de C#)](index.md)   
 [Cómo: Proporcionar un cuadro de diálogo de progreso para operaciones de archivos](how-to-provide-a-progress-dialog-box-for-file-operations.md)   
 [E/S de archivos y secuencias](https://msdn.microsoft.com/library/k3352a4t)   
 [Tareas de E/S comunes](https://msdn.microsoft.com/library/ms404278)
