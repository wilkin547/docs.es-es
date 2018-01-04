---
title: ISymUnmanagedScope (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope
helpviewer_keywords: ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e4d4c83b754945c126913a9d96db47966959fed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="c60d6-102">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c60d6-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="c60d6-103">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="c60d6-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c60d6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c60d6-104">Methods</span></span>  
  
|<span data-ttu-id="c60d6-105">Método</span><span class="sxs-lookup"><span data-stu-id="c60d6-105">Method</span></span>|<span data-ttu-id="c60d6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c60d6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c60d6-107">GetChildren (método)</span><span class="sxs-lookup"><span data-stu-id="c60d6-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="c60d6-108">Obtiene a los elementos secundarios de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c60d6-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="c60d6-109">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="c60d6-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="c60d6-110">Obtiene el desplazamiento final de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c60d6-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="c60d6-111">GetLocalCount (método)</span><span class="sxs-lookup"><span data-stu-id="c60d6-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="c60d6-112">Obtiene un recuento de las variables locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c60d6-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="c60d6-113">GetLocals (método)</span><span class="sxs-lookup"><span data-stu-id="c60d6-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="c60d6-114">Obtiene las variables locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c60d6-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="c60d6-115">GetMethod (método)</span><span class="sxs-lookup"><span data-stu-id="c60d6-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="c60d6-116">Obtiene el método que contiene este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c60d6-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="c60d6-117">GetNamespaces (método)</span><span class="sxs-lookup"><span data-stu-id="c60d6-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="c60d6-118">Obtiene los espacios de nombres que se utilizan dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c60d6-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="c60d6-119">GetParent (método)</span><span class="sxs-lookup"><span data-stu-id="c60d6-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="c60d6-120">Obtiene el ámbito primario de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c60d6-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="c60d6-121">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="c60d6-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="c60d6-122">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="c60d6-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c60d6-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c60d6-123">Requirements</span></span>  
 <span data-ttu-id="c60d6-124">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c60d6-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c60d6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c60d6-125">See Also</span></span>  
 [<span data-ttu-id="c60d6-126">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="c60d6-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="c60d6-127">ISymUnmanagedScope2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c60d6-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
