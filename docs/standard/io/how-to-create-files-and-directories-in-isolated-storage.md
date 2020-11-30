---
title: Procedimiento para crear archivos y directorios en almacenamiento aislado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directories [.NET], isolated storage
- files [.NET], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
ms.openlocfilehash: 1f6e8e1a048fcf7f8fd278eaac4988fa0e35791d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684998"
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a>Procedimiento para crear archivos y directorios en almacenamiento aislado

Después de haber obtenido un almacén aislado, puede crear directorios y archivos para almacenar los datos. Dentro de un almacén, los nombres de archivos y directorios se especifican con respecto a la raíz del sistema de archivos virtual.  
  
 Para crear un directorio, use el método de instancia <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType>. Si especifica un subdirectorio de un directorio que no existe, se crearán ambos directorios. Si especifica un directorio que ya existe, el método realiza la devolución sin crear un directorio y no se genera ninguna excepción. Sin embargo, si especifica un nombre de directorio que contiene caracteres no válidos, se produce la excepción <xref:System.IO.IsolatedStorage.IsolatedStorageException>.  
  
 Para crear un archivo, use el método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType>.  
  
 En el sistema operativo Windows, los nombres de archivos y directorios del almacenamiento aislado distinguen mayúsculas y minúsculas. Es decir, si crea un archivo denominado `ThisFile.txt` y luego crea otro archivo llamado `THISFILE.TXT`, solo se crea un archivo. El nombre de archivo mantiene las mayúsculas y minúsculas originales para la presentación.  

 La creación de un archivo de almacenamiento aislado producirá una excepción del tipo <xref:System.IO.IsolatedStorage.IsolatedStorageException> si la ruta de acceso contiene un directorio que no existe.
  
## <a name="example"></a>Ejemplo  

 En el ejemplo de código siguiente se muestra cómo crear archivos y directorios en un almacén aislado.  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>
- [Almacenamiento aislado](isolated-storage.md)
