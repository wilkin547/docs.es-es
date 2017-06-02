---
title: "C&#243;mo: Agregar o quitar entradas de la lista de control de acceso | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "entradas de control de acceso [.NET Framework]"
  - "listas de control de acceso [.NET Framework]"
  - "ACE [.NET Framework]"
  - "ACL [.NET Framework]"
  - "E/S [.NET Framework], obtener acceso a las entradas de la lista"
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Agregar o quitar entradas de la lista de control de acceso
Para agregar entradas de la lista de control de acceso \(ACL\) en un archivo o quitarlas de él, el objeto <xref:System.Security.AccessControl.FileSecurity> o <xref:System.Security.AccessControl.DirectorySecurity> debe obtenerse a partir del archivo o directorio, modificarse y, a continuación, volver a aplicarse al archivo o directorio.  
  
### Para agregar una entrada de la ACL a un archivo o quitarla de él  
  
1.  Llame al método <xref:System.IO.File.GetAccessControl%2A> para obtener un objeto <xref:System.Security.AccessControl.FileSecurity> que contenga las entradas de la ACL actuales de un archivo.  
  
2.  Agregue las entradas de la ACL al objeto <xref:System.Security.AccessControl.FileSecurity> devuelto desde el paso 1 o quite dichas entradas de dicho objeto.  
  
3.  Pase el objeto <xref:System.Security.AccessControl.FileSecurity> al método <xref:System.IO.File.SetAccessControl%2A> para aplicar los cambios.  
  
### Para agregar una entrada de la ACL a un directorio o quitarla de él  
  
1.  Llame al método <xref:System.IO.Directory.GetAccessControl%2A> para obtener un objeto <xref:System.Security.AccessControl.DirectorySecurity> que contenga las entradas de la ACL actuales de un directorio.  
  
2.  Agregue las entradas de la ACL al objeto <xref:System.Security.AccessControl.DirectorySecurity> devuelto desde el paso 1 o quite dichas entradas de dicho objeto.  
  
3.  Pase el objeto <xref:System.Security.AccessControl.DirectorySecurity> al método <xref:System.IO.Directory.SetAccessControl%2A> para aplicar los cambios.  
  
## Ejemplo  
 [!code-cpp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/cpp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/cpp/sample.cpp#1)]
 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
  
## Compilar el código  
 Para ejecutar este ejemplo, debe proporcionar una cuenta de usuario o grupo válida.  Este ejemplo utiliza un objeto <xref:System.IO.File>; sin embargo, se utiliza el mismo procedimiento para las clases <xref:System.IO.FileInfo>, <xref:System.IO.Directory> y <xref:System.IO.DirectoryInfo>.