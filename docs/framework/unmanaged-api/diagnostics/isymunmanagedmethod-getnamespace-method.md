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
ms.openlocfilehash: a2bba44af50607772f2a52203a47e21d8699f78b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716161"
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="17445-102">ISymUnmanagedMethod::GetNamespace (Método)</span><span class="sxs-lookup"><span data-stu-id="17445-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="17445-103">Obtiene el espacio de nombres dentro del cual se define este método.</span><span class="sxs-lookup"><span data-stu-id="17445-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17445-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17445-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17445-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17445-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="17445-106">[out] Un puntero que se establece en el valor devuelto [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="17445-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17445-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="17445-107">Return Value</span></span>  
 <span data-ttu-id="17445-108">S_OK si el método se realiza correctamente; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="17445-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17445-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17445-109">Requirements</span></span>  
 <span data-ttu-id="17445-110">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="17445-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17445-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="17445-111">See also</span></span>
- [<span data-ttu-id="17445-112">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="17445-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
