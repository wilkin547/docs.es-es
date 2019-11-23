---
title: ISymUnmanagedMethod (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod
helpviewer_keywords:
- ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: f204d74c-cc79-4092-83bb-60654be95649
topic_type:
- apiref
ms.openlocfilehash: 1d3ccb2265f056d5776199d997dc067c8d5513e5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448786"
---
# <a name="isymunmanagedmethod-interface"></a><span data-ttu-id="55ccf-102">ISymUnmanagedMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55ccf-102">ISymUnmanagedMethod Interface</span></span>
<span data-ttu-id="55ccf-103">Represents a method within the symbol store.</span><span class="sxs-lookup"><span data-stu-id="55ccf-103">Represents a method within the symbol store.</span></span> <span data-ttu-id="55ccf-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span><span class="sxs-lookup"><span data-stu-id="55ccf-104">This interface provides access to only the symbol-related attributes of a method, instead of the type-related attributes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55ccf-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="55ccf-105">Methods</span></span>  
  
|<span data-ttu-id="55ccf-106">Método</span><span class="sxs-lookup"><span data-stu-id="55ccf-106">Method</span></span>|<span data-ttu-id="55ccf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="55ccf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="55ccf-108">GetNamespace (método)</span><span class="sxs-lookup"><span data-stu-id="55ccf-108">GetNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getnamespace-method.md)|<span data-ttu-id="55ccf-109">Gets the namespace within which this method is defined.</span><span class="sxs-lookup"><span data-stu-id="55ccf-109">Gets the namespace within which this method is defined.</span></span>|  
|[<span data-ttu-id="55ccf-110">GetOffset (método)</span><span class="sxs-lookup"><span data-stu-id="55ccf-110">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getoffset-method.md)|<span data-ttu-id="55ccf-111">Returns the offset within this method that corresponds to a given position within a document.</span><span class="sxs-lookup"><span data-stu-id="55ccf-111">Returns the offset within this method that corresponds to a given position within a document.</span></span>|  
|[<span data-ttu-id="55ccf-112">GetParameters (método)</span><span class="sxs-lookup"><span data-stu-id="55ccf-112">GetParameters Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getparameters-method.md)|<span data-ttu-id="55ccf-113">Gets the parameters for this method.</span><span class="sxs-lookup"><span data-stu-id="55ccf-113">Gets the parameters for this method.</span></span>|  
|[<span data-ttu-id="55ccf-114">GetRanges (método)</span><span class="sxs-lookup"><span data-stu-id="55ccf-114">GetRanges Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getranges-method.md)|<span data-ttu-id="55ccf-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span><span class="sxs-lookup"><span data-stu-id="55ccf-115">Given a position in a document, returns an array of start and end offset pairs that correspond to the ranges of Microsoft intermediate language (MSIL) that the position covers within this method.</span></span>|  
|[<span data-ttu-id="55ccf-116">GetRootScope (método)</span><span class="sxs-lookup"><span data-stu-id="55ccf-116">GetRootScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getrootscope-method.md)|<span data-ttu-id="55ccf-117">Gets the root lexical scope within this method.</span><span class="sxs-lookup"><span data-stu-id="55ccf-117">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="55ccf-118">Este ámbito abarca el método completo.</span><span class="sxs-lookup"><span data-stu-id="55ccf-118">This scope encloses the entire method.</span></span>|  
|[<span data-ttu-id="55ccf-119">GetScopeFromOffset (método)</span><span class="sxs-lookup"><span data-stu-id="55ccf-119">GetScopeFromOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getscopefromoffset-method.md)|<span data-ttu-id="55ccf-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span><span class="sxs-lookup"><span data-stu-id="55ccf-120">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span>|  
|[<span data-ttu-id="55ccf-121">GetSequencePointCount (método)</span><span class="sxs-lookup"><span data-stu-id="55ccf-121">GetSequencePointCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepointcount-method.md)|<span data-ttu-id="55ccf-122">Gets the count of sequence points within this method.</span><span class="sxs-lookup"><span data-stu-id="55ccf-122">Gets the count of sequence points within this method.</span></span>|  
|[<span data-ttu-id="55ccf-123">GetSequencePoints (método)</span><span class="sxs-lookup"><span data-stu-id="55ccf-123">GetSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsequencepoints-method.md)|<span data-ttu-id="55ccf-124">Gets all the sequence points within this method.</span><span class="sxs-lookup"><span data-stu-id="55ccf-124">Gets all the sequence points within this method.</span></span>|  
|[<span data-ttu-id="55ccf-125">GetSourceStartEnd (método)</span><span class="sxs-lookup"><span data-stu-id="55ccf-125">GetSourceStartEnd Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-getsourcestartend-method.md)|<span data-ttu-id="55ccf-126">Gets the start and end document positions for the source of this method.</span><span class="sxs-lookup"><span data-stu-id="55ccf-126">Gets the start and end document positions for the source of this method.</span></span>|  
|[<span data-ttu-id="55ccf-127">GetToken (método)</span><span class="sxs-lookup"><span data-stu-id="55ccf-127">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-gettoken-method.md)|<span data-ttu-id="55ccf-128">Returns the metadata token for this method.</span><span class="sxs-lookup"><span data-stu-id="55ccf-128">Returns the metadata token for this method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="55ccf-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55ccf-129">Requirements</span></span>  
 <span data-ttu-id="55ccf-130">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="55ccf-130">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ccf-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="55ccf-131">See also</span></span>

- [<span data-ttu-id="55ccf-132">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="55ccf-132">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
