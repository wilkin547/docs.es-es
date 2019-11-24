---
title: ISymUnmanagedScope::GetEndOffset (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
ms.openlocfilehash: 25a8188e3ab62c095355b72b3e63e767a6768114
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446356"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="4f2fd-102">ISymUnmanagedScope::GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="4f2fd-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="4f2fd-103">Gets the end offset for this scope.</span><span class="sxs-lookup"><span data-stu-id="4f2fd-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f2fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f2fd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f2fd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4f2fd-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="4f2fd-106">[out] A pointer to a `ULONG32` that receives the end offset.</span><span class="sxs-lookup"><span data-stu-id="4f2fd-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f2fd-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4f2fd-107">Return Value</span></span>  
 <span data-ttu-id="4f2fd-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="4f2fd-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f2fd-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f2fd-109">Requirements</span></span>  
 <span data-ttu-id="4f2fd-110">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4f2fd-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f2fd-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f2fd-111">See also</span></span>

- [<span data-ttu-id="4f2fd-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f2fd-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
- [<span data-ttu-id="4f2fd-113">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="4f2fd-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
