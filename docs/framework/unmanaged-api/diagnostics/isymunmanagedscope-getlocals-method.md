---
title: ISymUnmanagedScope::GetLocals (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
ms.openlocfilehash: bf932b63973f93c56883f099ddaadd9d1519f337
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446329"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="341f2-102">ISymUnmanagedScope::GetLocals (Método)</span><span class="sxs-lookup"><span data-stu-id="341f2-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="341f2-103">Gets the local variables defined within this scope.</span><span class="sxs-lookup"><span data-stu-id="341f2-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="341f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="341f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="341f2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="341f2-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="341f2-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span><span class="sxs-lookup"><span data-stu-id="341f2-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="341f2-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span><span class="sxs-lookup"><span data-stu-id="341f2-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="341f2-108">[out] The array that receives the local variables.</span><span class="sxs-lookup"><span data-stu-id="341f2-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="341f2-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="341f2-109">Return Value</span></span>  
 <span data-ttu-id="341f2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="341f2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="341f2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="341f2-111">Requirements</span></span>  
 <span data-ttu-id="341f2-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="341f2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="341f2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="341f2-113">See also</span></span>

- [<span data-ttu-id="341f2-114">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="341f2-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
