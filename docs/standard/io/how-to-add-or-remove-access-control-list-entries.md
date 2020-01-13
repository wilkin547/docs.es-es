---
title: Procedimiento Agregar o quitar entradas de la lista de control de acceso (solo .NET Framework)
ms.date: 01/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ACEs [.NET Framework]
- ACLs [.NET Framework]
- access control entries [.NET Framework]
- I/O [.NET Framework], access control list entries
- access control lists [.NET Framework]
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
ms.openlocfilehash: 5f41c518b8732adff95593cab29d7085adcc9ab3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708133"
---
# <a name="how-to-add-or-remove-access-control-list-entries-net-framework-only"></a>Procedimiento Agregar o quitar entradas de la lista de control de acceso (solo .NET Framework)
Para agregar o quitar entradas de la lista de control de acceso (ACL) en un archivo o directorio o quitarlas de él, obtenga el objeto <xref:System.Security.AccessControl.FileSecurity> o <xref:System.Security.AccessControl.DirectorySecurity> a partir del archivo o directorio. Modifique el objeto y, a continuación, vuelva a aplicarlo al archivo o directorio.  
  
## <a name="add-or-remove-an-acl-entry-from-a-file"></a>Agregar una entrada de la ACL a un archivo o quitarla de él  
  
1. Llame al método <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType> para obtener un objeto <xref:System.Security.AccessControl.FileSecurity> que contenga las entradas de la ACL actuales de un archivo.  
  
2. Agregue las entradas de la ACL al objeto <xref:System.Security.AccessControl.FileSecurity> devuelto desde el paso 1 o quite dichas entradas de dicho objeto.  
  
3. Para aplicar los cambios, pase el objeto <xref:System.Security.AccessControl.FileSecurity> al método <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType>.  
  
## <a name="add-or-remove-an-acl-entry-from-a-directory"></a>Agregar una entrada de la ACL a un directorio o quitarla de él  
  
1. Llame al método <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType> para obtener un objeto <xref:System.Security.AccessControl.DirectorySecurity> que contenga las entradas de la ACL actuales de un directorio.  
  
2. Agregue las entradas de la ACL al objeto <xref:System.Security.AccessControl.DirectorySecurity> devuelto desde el paso 1 o quite dichas entradas de dicho objeto.  
  
3. Para aplicar los cambios, pase el objeto <xref:System.Security.AccessControl.DirectorySecurity> al método <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  
 Para ejecutar este ejemplo, debe usar una cuenta de usuario o grupo válida. En el ejemplo se usa un objeto <xref:System.IO.File>. Use el mismo procedimiento para las clases <xref:System.IO.FileInfo>, <xref:System.IO.Directory> y <xref:System.IO.DirectoryInfo>.

 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
