---
title: ISymUnmanagedWriter2::DefineLocalVariable2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
ms.openlocfilehash: 73f536b4ab98aa596c2395810cb8b616ffd309e9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438292"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="8fa73-102">ISymUnmanagedWriter2::DefineLocalVariable2 (Método)</span><span class="sxs-lookup"><span data-stu-id="8fa73-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="8fa73-103">Define una única variable en el ámbito léxico actual.</span><span class="sxs-lookup"><span data-stu-id="8fa73-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="8fa73-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span><span class="sxs-lookup"><span data-stu-id="8fa73-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="8fa73-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span><span class="sxs-lookup"><span data-stu-id="8fa73-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fa73-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8fa73-106">Syntax</span></span>  
  
```cpp  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fa73-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8fa73-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8fa73-108">[in] The local variable name.</span><span class="sxs-lookup"><span data-stu-id="8fa73-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="8fa73-109">[in] The local variable attributes.</span><span class="sxs-lookup"><span data-stu-id="8fa73-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="8fa73-110">[in] The metadata token of the signature.</span><span class="sxs-lookup"><span data-stu-id="8fa73-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="8fa73-111">[in] The address type.</span><span class="sxs-lookup"><span data-stu-id="8fa73-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="8fa73-112">[in] The first address for the parameter specification.</span><span class="sxs-lookup"><span data-stu-id="8fa73-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="8fa73-113">[in] The second address for the parameter specification.</span><span class="sxs-lookup"><span data-stu-id="8fa73-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="8fa73-114">[in] The third address for the parameter specification.</span><span class="sxs-lookup"><span data-stu-id="8fa73-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="8fa73-115">[in] The start offset for the variable.</span><span class="sxs-lookup"><span data-stu-id="8fa73-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="8fa73-116">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="8fa73-116">This parameter is optional.</span></span> <span data-ttu-id="8fa73-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span><span class="sxs-lookup"><span data-stu-id="8fa73-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="8fa73-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span><span class="sxs-lookup"><span data-stu-id="8fa73-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="8fa73-119">[in] The end offset for the variable.</span><span class="sxs-lookup"><span data-stu-id="8fa73-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="8fa73-120">Este parámetro es opcional.</span><span class="sxs-lookup"><span data-stu-id="8fa73-120">This parameter is optional.</span></span> <span data-ttu-id="8fa73-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span><span class="sxs-lookup"><span data-stu-id="8fa73-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="8fa73-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span><span class="sxs-lookup"><span data-stu-id="8fa73-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fa73-123">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8fa73-123">Return Value</span></span>  
 <span data-ttu-id="8fa73-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="8fa73-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fa73-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8fa73-125">Requirements</span></span>  
 <span data-ttu-id="8fa73-126">**Header:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="8fa73-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fa73-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fa73-127">See also</span></span>

- [<span data-ttu-id="8fa73-128">ISymUnmanagedWriter2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8fa73-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)
- [<span data-ttu-id="8fa73-129">DefineLocalVariable (método)</span><span class="sxs-lookup"><span data-stu-id="8fa73-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
