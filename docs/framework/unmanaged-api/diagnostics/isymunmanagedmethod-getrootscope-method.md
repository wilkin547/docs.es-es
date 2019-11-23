---
title: ISymUnmanagedMethod::GetRootScope (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetRootScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type:
- apiref
ms.openlocfilehash: c956f5d68c992f1b08988e59038e8667b391f734
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448918"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="33b59-102">ISymUnmanagedMethod::GetRootScope (Método)</span><span class="sxs-lookup"><span data-stu-id="33b59-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="33b59-103">Gets the root lexical scope within this method.</span><span class="sxs-lookup"><span data-stu-id="33b59-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="33b59-104">Este ámbito abarca el método completo.</span><span class="sxs-lookup"><span data-stu-id="33b59-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33b59-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33b59-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33b59-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33b59-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="33b59-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="33b59-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33b59-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33b59-108">Return Value</span></span>  
 <span data-ttu-id="33b59-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span><span class="sxs-lookup"><span data-stu-id="33b59-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33b59-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33b59-110">Requirements</span></span>  
 <span data-ttu-id="33b59-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="33b59-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b59-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="33b59-112">See also</span></span>

- [<span data-ttu-id="33b59-113">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33b59-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
