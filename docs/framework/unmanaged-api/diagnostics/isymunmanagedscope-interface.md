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
ms.openlocfilehash: 8da4da38d23ed65a0fdc44a0f919ee8cad2fe18e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446263"
---
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="a8cc2-102">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8cc2-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="a8cc2-103">Represents a lexical scope within a method.</span><span class="sxs-lookup"><span data-stu-id="a8cc2-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a8cc2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a8cc2-104">Methods</span></span>  
  
|<span data-ttu-id="a8cc2-105">Método</span><span class="sxs-lookup"><span data-stu-id="a8cc2-105">Method</span></span>|<span data-ttu-id="a8cc2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8cc2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a8cc2-107">GetChildren (método)</span><span class="sxs-lookup"><span data-stu-id="a8cc2-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="a8cc2-108">Gets the children of this scope.</span><span class="sxs-lookup"><span data-stu-id="a8cc2-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="a8cc2-109">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="a8cc2-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="a8cc2-110">Gets the end offset for this scope.</span><span class="sxs-lookup"><span data-stu-id="a8cc2-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="a8cc2-111">GetLocalCount (método)</span><span class="sxs-lookup"><span data-stu-id="a8cc2-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="a8cc2-112">Gets a count of the local variables defined within this scope.</span><span class="sxs-lookup"><span data-stu-id="a8cc2-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="a8cc2-113">GetLocals (método)</span><span class="sxs-lookup"><span data-stu-id="a8cc2-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="a8cc2-114">Gets the local variables defined within this scope.</span><span class="sxs-lookup"><span data-stu-id="a8cc2-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="a8cc2-115">GetMethod (método)</span><span class="sxs-lookup"><span data-stu-id="a8cc2-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="a8cc2-116">Gets the method that contains this scope.</span><span class="sxs-lookup"><span data-stu-id="a8cc2-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="a8cc2-117">GetNamespaces (método)</span><span class="sxs-lookup"><span data-stu-id="a8cc2-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="a8cc2-118">Gets the namespaces that are being used within this scope.</span><span class="sxs-lookup"><span data-stu-id="a8cc2-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="a8cc2-119">GetParent (método)</span><span class="sxs-lookup"><span data-stu-id="a8cc2-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="a8cc2-120">Gets the parent scope of this scope.</span><span class="sxs-lookup"><span data-stu-id="a8cc2-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="a8cc2-121">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="a8cc2-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="a8cc2-122">Gets the start offset for this scope.</span><span class="sxs-lookup"><span data-stu-id="a8cc2-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8cc2-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8cc2-123">Requirements</span></span>  
 <span data-ttu-id="a8cc2-124">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a8cc2-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8cc2-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8cc2-125">See also</span></span>

- [<span data-ttu-id="a8cc2-126">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="a8cc2-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="a8cc2-127">ISymUnmanagedScope2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8cc2-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
