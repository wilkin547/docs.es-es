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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7c77be0dde950693d3943e41c392dcdcd9bc995e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096080"
---
# <a name="isymunmanagedmethodgetrootscope-method"></a><span data-ttu-id="feafe-102">ISymUnmanagedMethod::GetRootScope (Método)</span><span class="sxs-lookup"><span data-stu-id="feafe-102">ISymUnmanagedMethod::GetRootScope Method</span></span>
<span data-ttu-id="feafe-103">Obtiene el ámbito léxico raíz dentro de este método.</span><span class="sxs-lookup"><span data-stu-id="feafe-103">Gets the root lexical scope within this method.</span></span> <span data-ttu-id="feafe-104">Este ámbito abarca el método completo.</span><span class="sxs-lookup"><span data-stu-id="feafe-104">This scope encloses the entire method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="feafe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="feafe-105">Syntax</span></span>  
  
```  
HRESULT GetRootScope(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="feafe-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="feafe-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="feafe-107">[out] Un puntero que se establece en el valor devuelto [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="feafe-107">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="feafe-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="feafe-108">Return Value</span></span>  
 <span data-ttu-id="feafe-109">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="feafe-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="feafe-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="feafe-110">Requirements</span></span>  
 <span data-ttu-id="feafe-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="feafe-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feafe-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="feafe-112">See also</span></span>

- [<span data-ttu-id="feafe-113">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="feafe-113">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
