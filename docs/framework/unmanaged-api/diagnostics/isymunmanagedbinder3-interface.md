---
title: ISymUnmanagedBinder3 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c93275fc32e68f49618d93bdd0b54f1970121ee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder3-interface"></a><span data-ttu-id="a64f1-102">ISymUnmanagedBinder3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a64f1-102">ISymUnmanagedBinder3 Interface</span></span>
<span data-ttu-id="a64f1-103">Extiende la interfaz de enlazador de símbolos.</span><span class="sxs-lookup"><span data-stu-id="a64f1-103">Extends the symbol binder interface.</span></span> <span data-ttu-id="a64f1-104">Obtener esta interfaz mediante una llamada a `QueryInterface` en un objeto que implementa el `ISymUnmanagedBinder` interfaz.</span><span class="sxs-lookup"><span data-stu-id="a64f1-104">Obtain this interface by calling `QueryInterface` on an object that implements the `ISymUnmanagedBinder` interface.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a64f1-105">Es un riesgo de seguridad para abrir un archivo de programa (PDB) de la base de datos desde un origen de confianza.</span><span class="sxs-lookup"><span data-stu-id="a64f1-105">It is a security risk to open a program database (PDB) file from an untrusted source.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a64f1-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="a64f1-106">Methods</span></span>  
  
|<span data-ttu-id="a64f1-107">Método</span><span class="sxs-lookup"><span data-stu-id="a64f1-107">Method</span></span>|<span data-ttu-id="a64f1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a64f1-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a64f1-109">GetReaderFromCallback (método)</span><span class="sxs-lookup"><span data-stu-id="a64f1-109">GetReaderFromCallback Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|<span data-ttu-id="a64f1-110">Permite al usuario implementar o proporcionar a través de la devolución de llamada ya sea un `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` para obtener la información de directorio de depuración de la memoria</span><span class="sxs-lookup"><span data-stu-id="a64f1-110">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the Debug directory information from memory</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a64f1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a64f1-111">Requirements</span></span>  
 <span data-ttu-id="a64f1-112">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a64f1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a64f1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a64f1-113">See Also</span></span>  
 [<span data-ttu-id="a64f1-114">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="a64f1-114">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="a64f1-115">ISymUnmanagedBinder (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a64f1-115">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="a64f1-116">ISymUnmanagedBinder2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a64f1-116">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
