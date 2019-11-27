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
# <a name="isymunmanagedscope-interface"></a><span data-ttu-id="64d4b-102">ISymUnmanagedScope (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="64d4b-102">ISymUnmanagedScope Interface</span></span>
<span data-ttu-id="64d4b-103">Representa un ámbito léxico dentro de un método.</span><span class="sxs-lookup"><span data-stu-id="64d4b-103">Represents a lexical scope within a method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="64d4b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="64d4b-104">Methods</span></span>  
  
|<span data-ttu-id="64d4b-105">Método</span><span class="sxs-lookup"><span data-stu-id="64d4b-105">Method</span></span>|<span data-ttu-id="64d4b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="64d4b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="64d4b-107">GetChildren (método)</span><span class="sxs-lookup"><span data-stu-id="64d4b-107">GetChildren Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getchildren-method.md)|<span data-ttu-id="64d4b-108">Obtiene los elementos secundarios de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="64d4b-108">Gets the children of this scope.</span></span>|  
|[<span data-ttu-id="64d4b-109">GetEndOffset (método)</span><span class="sxs-lookup"><span data-stu-id="64d4b-109">GetEndOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getendoffset-method.md)|<span data-ttu-id="64d4b-110">Obtiene el desplazamiento final para este ámbito.</span><span class="sxs-lookup"><span data-stu-id="64d4b-110">Gets the end offset for this scope.</span></span>|  
|[<span data-ttu-id="64d4b-111">GetLocalCount (método)</span><span class="sxs-lookup"><span data-stu-id="64d4b-111">GetLocalCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocalcount-method.md)|<span data-ttu-id="64d4b-112">Obtiene un recuento de las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="64d4b-112">Gets a count of the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="64d4b-113">GetLocals (método)</span><span class="sxs-lookup"><span data-stu-id="64d4b-113">GetLocals Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getlocals-method.md)|<span data-ttu-id="64d4b-114">Obtiene las variables locales definidas dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="64d4b-114">Gets the local variables defined within this scope.</span></span>|  
|[<span data-ttu-id="64d4b-115">GetMethod (método)</span><span class="sxs-lookup"><span data-stu-id="64d4b-115">GetMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getmethod-method.md)|<span data-ttu-id="64d4b-116">Obtiene el método que contiene este ámbito.</span><span class="sxs-lookup"><span data-stu-id="64d4b-116">Gets the method that contains this scope.</span></span>|  
|[<span data-ttu-id="64d4b-117">GetNamespaces (método)</span><span class="sxs-lookup"><span data-stu-id="64d4b-117">GetNamespaces Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getnamespaces-method.md)|<span data-ttu-id="64d4b-118">Obtiene los espacios de nombres que se usan dentro de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="64d4b-118">Gets the namespaces that are being used within this scope.</span></span>|  
|[<span data-ttu-id="64d4b-119">GetParent (método)</span><span class="sxs-lookup"><span data-stu-id="64d4b-119">GetParent Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getparent-method.md)|<span data-ttu-id="64d4b-120">Obtiene el ámbito primario de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="64d4b-120">Gets the parent scope of this scope.</span></span>|  
|[<span data-ttu-id="64d4b-121">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="64d4b-121">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)|<span data-ttu-id="64d4b-122">Obtiene el desplazamiento inicial de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="64d4b-122">Gets the start offset for this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="64d4b-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64d4b-123">Requirements</span></span>  
 <span data-ttu-id="64d4b-124">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="64d4b-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64d4b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="64d4b-125">See also</span></span>

- [<span data-ttu-id="64d4b-126">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="64d4b-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="64d4b-127">ISymUnmanagedScope2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="64d4b-127">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
