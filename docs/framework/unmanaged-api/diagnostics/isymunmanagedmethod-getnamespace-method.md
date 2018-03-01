---
title: "ISymUnmanagedMethod::GetNamespace (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedMethod.GetNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2244229b50a9944cefb5804720198bf391fd0e6b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="d53e3-102">ISymUnmanagedMethod::GetNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="d53e3-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="d53e3-103">Obtiene el espacio de nombres dentro del cual se define este método.</span><span class="sxs-lookup"><span data-stu-id="d53e3-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d53e3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d53e3-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d53e3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d53e3-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d53e3-106">[out] Un puntero que se establece en el valor devuelto [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="d53e3-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d53e3-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d53e3-107">Return Value</span></span>  
 <span data-ttu-id="d53e3-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="d53e3-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d53e3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d53e3-109">Requirements</span></span>  
 <span data-ttu-id="d53e3-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d53e3-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53e3-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="d53e3-111">See Also</span></span>  
 [<span data-ttu-id="d53e3-112">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d53e3-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
