---
title: "Cómo: Crear archivos y directorios en almacenamiento aislado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b8a48473bf9ac91b89657d00d27031255491353
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a>Cómo: Crear archivos y directorios en almacenamiento aislado
Después de haber obtenido un almacén aislado, puede crear directorios y archivos para almacenar los datos. Dentro de un almacén, se especifican los nombres de archivos y directorios con respecto a la raíz del sistema de archivos virtual.  
  
 Para crear un directorio, use el <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> método de instancia. Si especifica un subdirectorio de un directorio que no existe, se crean dos directorios. Si especifica un directorio que ya existe, el método devuelve sin crear un directorio y se inicia ninguna excepción. Sin embargo, si especifica un nombre de directorio que contiene caracteres no válidos, un <xref:System.IO.IsolatedStorage.IsolatedStorageException> se produce la excepción.  
  
 Para crear un archivo, use la <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> método.  
  
 En el sistema operativo de Windows, el archivo de almacenamiento aislado y el directorio nombres distinguen mayúsculas de minúsculas. Es decir, si crea un archivo denominado `ThisFile.txt`y, a continuación, cree otro archivo denominado `THISFILE.TXT`, se crea un solo archivo. El nombre de archivo mantiene sus mayúsculas y minúsculas original para la presentación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo crear archivos y directorios en un almacén aislado.  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)
