---
title: 'Cómo: Agregar o quitar entradas de la lista de control de acceso'
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 24c428a80f18b35d0aa3119a3c5fa1a6dcb2130e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573428"
---
# <a name="how-to-add-or-remove-access-control-list-entries"></a>Cómo: Agregar o quitar entradas de la lista de control de acceso
Para agregar entradas de la lista de control de acceso (ACL) en un archivo o quitarlas de él, el objeto <xref:System.Security.AccessControl.FileSecurity> o <xref:System.Security.AccessControl.DirectorySecurity> debe obtenerse a partir del archivo o directorio, modificarse y, a continuación, volver a aplicarse al archivo o directorio.  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-file"></a>Para agregar una entrada de la ACL a un archivo o quitarla de él  
  
1.  Llame al método <xref:System.IO.File.GetAccessControl%2A> para obtener un objeto <xref:System.Security.AccessControl.FileSecurity> que contenga las entradas de la ACL actuales de un archivo.  
  
2.  Agregue las entradas de la ACL al objeto <xref:System.Security.AccessControl.FileSecurity> devuelto desde el paso 1 o quite dichas entradas de dicho objeto.  
  
3.  Pase el objeto <xref:System.Security.AccessControl.FileSecurity> al método <xref:System.IO.File.SetAccessControl%2A> para aplicar los cambios.  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-directory"></a>Para agregar una entrada de la ACL a un directorio o quitarla de él  
  
1.  Llame al método <xref:System.IO.Directory.GetAccessControl%2A> para obtener un objeto <xref:System.Security.AccessControl.DirectorySecurity> que contenga las entradas de la ACL actuales de un directorio.  
  
2.  Agregue las entradas de la ACL al objeto <xref:System.Security.AccessControl.DirectorySecurity> devuelto desde el paso 1 o quite dichas entradas de dicho objeto.  
  
3.  Pase el objeto <xref:System.Security.AccessControl.DirectorySecurity> al método <xref:System.IO.Directory.SetAccessControl%2A> para aplicar los cambios.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/cpp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/cpp/sample.cpp#1)]
 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para ejecutar este ejemplo, debe proporcionar una cuenta de usuario o grupo válida. Este ejemplo utiliza un objeto <xref:System.IO.File>; sin embargo, se utiliza el mismo procedimiento para las clases <xref:System.IO.FileInfo>, <xref:System.IO.Directory> y <xref:System.IO.DirectoryInfo>.
