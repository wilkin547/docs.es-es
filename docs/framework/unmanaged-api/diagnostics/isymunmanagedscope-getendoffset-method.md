---
title: "ISymUnmanagedScope::GetEndOffset (Método)"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64990dc2785a3804e683e281c823f459ec48e8a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="e492e-102">ISymUnmanagedScope::GetEndOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="e492e-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="e492e-103">Obtiene el desplazamiento final de este ámbito.</span><span class="sxs-lookup"><span data-stu-id="e492e-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e492e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e492e-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e492e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e492e-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e492e-106">[out] Un puntero a un `ULONG32` que recibe el desplazamiento final.</span><span class="sxs-lookup"><span data-stu-id="e492e-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e492e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e492e-107">Return Value</span></span>  
 <span data-ttu-id="e492e-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="e492e-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e492e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e492e-109">Requirements</span></span>  
 <span data-ttu-id="e492e-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e492e-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e492e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e492e-111">See Also</span></span>  
 [<span data-ttu-id="e492e-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e492e-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="e492e-113">GetStartOffset (método)</span><span class="sxs-lookup"><span data-stu-id="e492e-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
