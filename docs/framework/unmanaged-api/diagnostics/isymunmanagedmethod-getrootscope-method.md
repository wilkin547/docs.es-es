---
title: "ISymUnmanagedMethod::GetRootScope (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetRootScope
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetRootScope
helpviewer_keywords:
- ISymUnmanagedMethod::GetRootScope method [.NET Framework debugging]
- GetRootScope method [.NET Framework debugging]
ms.assetid: 7d58caac-2e75-4dfa-9249-32d8a624b247
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7fe3d2934345fbc89b4a2c7747abb867a20df20
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="8a072-102">ISymUnmanagedMethod::GetRootScope (Método)</span><span class="sxs-lookup"><span data-stu-id="8a072-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="8a072-103">Obtiene el ámbito léxico raíz dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="8a072-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="8a072-104">Este ámbito abarca el método completo.</span><span class="sxs-lookup"><span data-stu-id="8a072-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a072-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a072-105">Syntax</span></span>  
  
```  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a072-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a072-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8a072-107">[out] Un puntero que se establece en el valor devuelto [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="8a072-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a072-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8a072-108">Return Value</span></span>  
 <span data-ttu-id="8a072-109">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8a072-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a072-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a072-110">Requirements</span></span>  
 <span data-ttu-id="8a072-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8a072-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a072-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a072-112">See Also</span></span>  
 [<span data-ttu-id="8a072-113">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a072-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
