---
title: "C&#243;mo: Enumerar los almacenes de almacenamiento aislado | Microsoft Docs"
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
  - "enumerar almacenes"
  - "almacenamiento de datos mediante el almacenamiento aislado, enumerar almacenes"
  - "almacenar datos mediante el almacenamiento aislado, enumerar almacenes"
  - "almacenes, enumerar"
  - "almacenamiento aislado, enumerar almacenes"
  - "almacenes de datos, enumerar"
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Enumerar los almacenes de almacenamiento aislado
Puede enumerar todos los almacenes aislados del usuario actual utilizando el método estático de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=fullName> .  Este método toma un valor de <xref:System.IO.IsolatedStorage.IsolatedStorageScope> y devuelve un enumerador de <xref:System.IO.IsolatedStorage.IsolatedStorageFile> .  Para enumerar almacenes, debe tener el permiso <xref:System.Security.Permissions.IsolatedStorageFilePermission> que especifica el valor <xref:System.Security.Permissions.IsolatedStorageContainment>.  Si se llama al método de <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> con el valor de <xref:System.IO.IsolatedStorage.IsolatedStorageScope>, devuelve una matriz de los objetos <xref:System.IO.IsolatedStorage.IsolatedStorageFile> definidos para el usuario actual.  
  
## Ejemplo  
 El siguiente ejemplo de código obtiene un almacén que está aislado por el usuario y el ensamblado, crea unos cuantos archivos, y recupera dichos archivos mediante el método <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A>.  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## Vea también  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>   
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)