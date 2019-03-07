---
title: ISymUnmanagedMethod::GetNamespace (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 544fffd1b230469227d6ddbe3afcba54b6a7d5c1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484594"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="8cf84-102">ISymUnmanagedMethod::GetNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="8cf84-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="8cf84-103">Obtiene el espacio de nombres dentro del cual se define este método.</span><span class="sxs-lookup"><span data-stu-id="8cf84-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cf84-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8cf84-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cf84-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8cf84-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8cf84-106">[out] Un puntero que se establece en el valor devuelto [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="8cf84-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8cf84-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8cf84-107">Return Value</span></span>  
 <span data-ttu-id="8cf84-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="8cf84-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cf84-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8cf84-109">Requirements</span></span>  
 <span data-ttu-id="8cf84-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8cf84-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf84-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cf84-111">See also</span></span>
- [<span data-ttu-id="8cf84-112">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cf84-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
