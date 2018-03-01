---
title: ISymUnmanagedScope2 (Interfaz)
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
- ISymUnmanagedScope2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2
helpviewer_keywords:
- ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f6d2ec846a34b2d3424f7bf8b54f1d4d12d4102e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="b8529-102">ISymUnmanagedScope2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8529-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="b8529-103">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="b8529-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="b8529-104">Esta interfaz extiende la [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaz con métodos que obtienen información sobre las constantes definidas dentro del ámbito.</span><span class="sxs-lookup"><span data-stu-id="b8529-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8529-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b8529-105">Methods</span></span>  
  
|<span data-ttu-id="b8529-106">Método</span><span class="sxs-lookup"><span data-stu-id="b8529-106">Method</span></span>|<span data-ttu-id="b8529-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8529-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8529-108">GetConstantCount (método)</span><span class="sxs-lookup"><span data-stu-id="b8529-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="b8529-109">Obtiene un recuento de las constantes definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="b8529-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="b8529-110">GetConstants (método)</span><span class="sxs-lookup"><span data-stu-id="b8529-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="b8529-111">Obtiene las constantes locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="b8529-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8529-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8529-112">Requirements</span></span>  
 <span data-ttu-id="b8529-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b8529-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8529-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8529-114">See Also</span></span>  
 [<span data-ttu-id="b8529-115">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="b8529-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="b8529-116">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8529-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
