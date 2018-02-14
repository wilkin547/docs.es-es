---
title: "Cómo: Agregar o quitar entradas de la lista de control de acceso"
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
- cpp
helpviewer_keywords:
- ACEs [.NET Framework]
- ACLs [.NET Framework]
- access control entries [.NET Framework]
- I/O [.NET Framework], access control list entries
- access control lists [.NET Framework]
ms.assetid: 53758b39-bd9b-4640-bb04-cad5ed8d0abf
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 988fd354caa5fcc716107087242ead113c9a9939
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-add-or-remove-access-control-list-entries"></a><span data-ttu-id="ca9a4-102">Cómo: Agregar o quitar entradas de la lista de control de acceso</span><span class="sxs-lookup"><span data-stu-id="ca9a4-102">How to: Add or Remove Access Control List Entries</span></span>
<span data-ttu-id="ca9a4-103">Para agregar entradas de la lista de control de acceso (ACL) en un archivo o quitarlas de él, el objeto <xref:System.Security.AccessControl.FileSecurity> o <xref:System.Security.AccessControl.DirectorySecurity> debe obtenerse a partir del archivo o directorio, modificarse y, a continuación, volver a aplicarse al archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="ca9a4-103">To add or remove Access Control List (ACL) entries to or from a file, the <xref:System.Security.AccessControl.FileSecurity> or <xref:System.Security.AccessControl.DirectorySecurity> object must be obtained from the file or directory, modified, and then applied back to the file or directory.</span></span>  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-file"></a><span data-ttu-id="ca9a4-104">Para agregar una entrada de la ACL a un archivo o quitarla de él</span><span class="sxs-lookup"><span data-stu-id="ca9a4-104">To add or remove an ACL entry from a File</span></span>  
  
1.  <span data-ttu-id="ca9a4-105">Llame al método <xref:System.IO.File.GetAccessControl%2A> para obtener un objeto <xref:System.Security.AccessControl.FileSecurity> que contenga las entradas de la ACL actuales de un archivo.</span><span class="sxs-lookup"><span data-stu-id="ca9a4-105">Call the <xref:System.IO.File.GetAccessControl%2A> method to get a <xref:System.Security.AccessControl.FileSecurity> object that contains the current ACL entries of a file.</span></span>  
  
2.  <span data-ttu-id="ca9a4-106">Agregue las entradas de la ACL al objeto <xref:System.Security.AccessControl.FileSecurity> devuelto desde el paso 1 o quite dichas entradas de dicho objeto.</span><span class="sxs-lookup"><span data-stu-id="ca9a4-106">Add or remove ACL entries from the <xref:System.Security.AccessControl.FileSecurity> object returned from step 1.</span></span>  
  
3.  <span data-ttu-id="ca9a4-107">Pase el objeto <xref:System.Security.AccessControl.FileSecurity> al método <xref:System.IO.File.SetAccessControl%2A> para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="ca9a4-107">Pass the <xref:System.Security.AccessControl.FileSecurity> object to the <xref:System.IO.File.SetAccessControl%2A> method to apply the changes.</span></span>  
  
### <a name="to-add-or-remove-an-acl-entry-from-a-directory"></a><span data-ttu-id="ca9a4-108">Para agregar una entrada de la ACL a un directorio o quitarla de él</span><span class="sxs-lookup"><span data-stu-id="ca9a4-108">To add or remove an ACL entry from a Directory</span></span>  
  
1.  <span data-ttu-id="ca9a4-109">Llame al método <xref:System.IO.Directory.GetAccessControl%2A> para obtener un objeto <xref:System.Security.AccessControl.DirectorySecurity> que contenga las entradas de la ACL actuales de un directorio.</span><span class="sxs-lookup"><span data-stu-id="ca9a4-109">Call the <xref:System.IO.Directory.GetAccessControl%2A> method to get a <xref:System.Security.AccessControl.DirectorySecurity> object that contains the current ACL entries of a directory.</span></span>  
  
2.  <span data-ttu-id="ca9a4-110">Agregue las entradas de la ACL al objeto <xref:System.Security.AccessControl.DirectorySecurity> devuelto desde el paso 1 o quite dichas entradas de dicho objeto.</span><span class="sxs-lookup"><span data-stu-id="ca9a4-110">Add or remove ACL entries from the <xref:System.Security.AccessControl.DirectorySecurity> object returned from step 1.</span></span>  
  
3.  <span data-ttu-id="ca9a4-111">Pase el objeto <xref:System.Security.AccessControl.DirectorySecurity> al método <xref:System.IO.Directory.SetAccessControl%2A> para aplicar los cambios.</span><span class="sxs-lookup"><span data-stu-id="ca9a4-111">Pass the <xref:System.Security.AccessControl.DirectorySecurity> object to the <xref:System.IO.Directory.SetAccessControl%2A> method to apply the changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca9a4-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca9a4-112">Example</span></span>  
 [!code-cpp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/cpp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/cpp/sample.cpp#1)]
 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ca9a4-113">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ca9a4-113">Compiling the Code</span></span>  
 <span data-ttu-id="ca9a4-114">Para ejecutar este ejemplo, debe proporcionar una cuenta de usuario o grupo válida.</span><span class="sxs-lookup"><span data-stu-id="ca9a4-114">You must supply a valid user or group account to run this example.</span></span> <span data-ttu-id="ca9a4-115">Este ejemplo utiliza un objeto <xref:System.IO.File>; sin embargo, se utiliza el mismo procedimiento para las clases <xref:System.IO.FileInfo>, <xref:System.IO.Directory> y <xref:System.IO.DirectoryInfo>.</span><span class="sxs-lookup"><span data-stu-id="ca9a4-115">This example uses a <xref:System.IO.File> object; however, the same procedure is used for the <xref:System.IO.FileInfo>, <xref:System.IO.Directory>, and <xref:System.IO.DirectoryInfo> classes.</span></span>
