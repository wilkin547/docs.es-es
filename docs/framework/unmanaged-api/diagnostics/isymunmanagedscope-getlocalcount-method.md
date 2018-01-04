---
title: "ISymUnmanagedScope::GetLocalCount (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetLocalCount
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9db774140ef55b2dfcb54ff701c2b842418a4923
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="303a5-102">ISymUnmanagedScope::GetLocalCount (Método)</span><span class="sxs-lookup"><span data-stu-id="303a5-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="303a5-103">Obtiene un recuento de las variables locales definidas en este ámbito.</span><span class="sxs-lookup"><span data-stu-id="303a5-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="303a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="303a5-104">Syntax</span></span>  
  
```  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="303a5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="303a5-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="303a5-106">[out] Un puntero a un `ULONG32` que recibe el número de variables locales.</span><span class="sxs-lookup"><span data-stu-id="303a5-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="303a5-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="303a5-107">Return Value</span></span>  
 <span data-ttu-id="303a5-108">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="303a5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="303a5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="303a5-109">Requirements</span></span>  
 <span data-ttu-id="303a5-110">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="303a5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="303a5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="303a5-111">See Also</span></span>  
 [<span data-ttu-id="303a5-112">ISymUnmanagedScope (interfaz)</span><span class="sxs-lookup"><span data-stu-id="303a5-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
