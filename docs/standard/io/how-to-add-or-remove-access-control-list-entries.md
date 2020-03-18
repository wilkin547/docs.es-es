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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "75708133"
---
# <a name="how-to-add-or-remove-access-control-list-entries-net-framework-only"></a><span data-ttu-id="dd6ff-102">Procedimiento Agregar o quitar entradas de la lista de control de acceso (solo .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="dd6ff-102">How to: Add or remove Access Control List entries (.NET Framework only)</span></span>
<span data-ttu-id="dd6ff-103">Para agregar o quitar entradas de la lista de control de acceso (ACL) en un archivo o directorio o quitarlas de él, obtenga el objeto <xref:System.Security.AccessControl.FileSecurity> o <xref:System.Security.AccessControl.DirectorySecurity> a partir del archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="dd6ff-103">To add or remove Access Control List (ACL) entries to or from a file or directory, get the <xref:System.Security.AccessControl.FileSecurity> or <xref:System.Security.AccessControl.DirectorySecurity> object from the file or directory.</span></span> <span data-ttu-id="dd6ff-104">Modifique el objeto y, a continuación, vuelva a aplicarlo al archivo o directorio.</span><span class="sxs-lookup"><span data-stu-id="dd6ff-104">Modify the object, and then apply it back to the file or directory.</span></span>  
  
## <a name="add-or-remove-an-acl-entry-from-a-file"></a><span data-ttu-id="dd6ff-105">Agregar una entrada de la ACL a un archivo o quitarla de él</span><span class="sxs-lookup"><span data-stu-id="dd6ff-105">Add or remove an ACL entry from a file</span></span>  
  
1. <span data-ttu-id="dd6ff-106">Llame al método <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType> para obtener un objeto <xref:System.Security.AccessControl.FileSecurity> que contenga las entradas de la ACL actuales de un archivo.</span><span class="sxs-lookup"><span data-stu-id="dd6ff-106">Call the <xref:System.IO.File.GetAccessControl%2A?displayProperty=nameWithType> method to get a <xref:System.Security.AccessControl.FileSecurity> object that contains the current ACL entries of a file.</span></span>  
  
2. <span data-ttu-id="dd6ff-107">Agregue las entradas de la ACL al objeto <xref:System.Security.AccessControl.FileSecurity> devuelto desde el paso 1 o quite dichas entradas de dicho objeto.</span><span class="sxs-lookup"><span data-stu-id="dd6ff-107">Add or remove ACL entries from the <xref:System.Security.AccessControl.FileSecurity> object returned from step 1.</span></span>  
  
3. <span data-ttu-id="dd6ff-108">Para aplicar los cambios, pase el objeto <xref:System.Security.AccessControl.FileSecurity> al método <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dd6ff-108">To apply the changes, pass the <xref:System.Security.AccessControl.FileSecurity> object to the <xref:System.IO.File.SetAccessControl%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="add-or-remove-an-acl-entry-from-a-directory"></a><span data-ttu-id="dd6ff-109">Agregar una entrada de la ACL a un directorio o quitarla de él</span><span class="sxs-lookup"><span data-stu-id="dd6ff-109">Add or remove an ACL entry from a directory</span></span>  
  
1. <span data-ttu-id="dd6ff-110">Llame al método <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType> para obtener un objeto <xref:System.Security.AccessControl.DirectorySecurity> que contenga las entradas de la ACL actuales de un directorio.</span><span class="sxs-lookup"><span data-stu-id="dd6ff-110">Call the <xref:System.IO.Directory.GetAccessControl%2A?displayProperty=nameWithType> method to get a <xref:System.Security.AccessControl.DirectorySecurity> object that contains the current ACL entries of a directory.</span></span>  
  
2. <span data-ttu-id="dd6ff-111">Agregue las entradas de la ACL al objeto <xref:System.Security.AccessControl.DirectorySecurity> devuelto desde el paso 1 o quite dichas entradas de dicho objeto.</span><span class="sxs-lookup"><span data-stu-id="dd6ff-111">Add or remove ACL entries from the <xref:System.Security.AccessControl.DirectorySecurity> object returned from step 1.</span></span>  
  
3. <span data-ttu-id="dd6ff-112">Para aplicar los cambios, pase el objeto <xref:System.Security.AccessControl.DirectorySecurity> al método <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="dd6ff-112">To apply the changes, pass the <xref:System.Security.AccessControl.DirectorySecurity> object to the <xref:System.IO.Directory.SetAccessControl%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd6ff-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd6ff-113">Example</span></span>  
 <span data-ttu-id="dd6ff-114">Para ejecutar este ejemplo, debe usar una cuenta de usuario o grupo válida.</span><span class="sxs-lookup"><span data-stu-id="dd6ff-114">You must use a valid user or group account to run this example.</span></span> <span data-ttu-id="dd6ff-115">En el ejemplo se usa un objeto <xref:System.IO.File>.</span><span class="sxs-lookup"><span data-stu-id="dd6ff-115">The example uses a <xref:System.IO.File> object.</span></span> <span data-ttu-id="dd6ff-116">Use el mismo procedimiento para las clases <xref:System.IO.FileInfo>, <xref:System.IO.Directory> y <xref:System.IO.DirectoryInfo>.</span><span class="sxs-lookup"><span data-stu-id="dd6ff-116">Use the same procedure for the <xref:System.IO.FileInfo>, <xref:System.IO.Directory>, and <xref:System.IO.DirectoryInfo> classes.</span></span>

 [!code-csharp[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/csharp/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/CS/sample.cs#1)]
 [!code-vb[IO.File.GetAccessControl-SetAccessControl#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/IO.File.GetAccessControl-SetAccessControl/VB/sample.vb#1)]  
