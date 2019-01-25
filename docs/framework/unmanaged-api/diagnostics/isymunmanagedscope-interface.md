---
title: ISymUnmanagedScope (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope
helpviewer_keywords:
- ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 3db7a220-cfe9-4810-8ca8-a094bb8e0f5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 965e8058d44ebb5dc87ade3b6025c6291a9c3bcd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54492135"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="b901f-102">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b901f-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="b901f-103">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="b901f-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b901f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b901f-104">Methods</span></span>  
  
|<span data-ttu-id="b901f-105">Método</span><span class="sxs-lookup"><span data-stu-id="b901f-105">Method</span></span>|<span data-ttu-id="b901f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b901f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b901f-107">GetChildren (método)</span><span class="sxs-lookup"><span data-stu-id="b901f-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="b901f-108">Obtiene a los elementos secundarios de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="b901f-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="b901f-109">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="b901f-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="b901f-110">Obtiene el desplazamiento final de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="b901f-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="b901f-111">GetLocalCount (método)</span><span class="sxs-lookup"><span data-stu-id="b901f-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="b901f-112">Obtiene un recuento de las variables locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="b901f-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="b901f-113">GetLocals (método)</span><span class="sxs-lookup"><span data-stu-id="b901f-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="b901f-114">Obtiene las variables locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="b901f-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="b901f-115">GetMethod (método)</span><span class="sxs-lookup"><span data-stu-id="b901f-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="b901f-116">Obtiene el método que contiene este ámbito.</span><span class="sxs-lookup"><span data-stu-id="b901f-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="b901f-117">GetNamespaces (método)</span><span class="sxs-lookup"><span data-stu-id="b901f-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="b901f-118">Obtiene los espacios de nombres que se utilizan dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="b901f-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="b901f-119">GetParent (método)</span><span class="sxs-lookup"><span data-stu-id="b901f-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="b901f-120">Obtiene el ámbito primario de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="b901f-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="b901f-121">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="b901f-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="b901f-122">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="b901f-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b901f-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b901f-123">Requirements</span></span>  
 <span data-ttu-id="b901f-124">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b901f-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b901f-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b901f-125">See also</span></span>
- [<span data-ttu-id="b901f-126">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="b901f-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="b901f-127">ISymUnmanagedScope2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b901f-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
