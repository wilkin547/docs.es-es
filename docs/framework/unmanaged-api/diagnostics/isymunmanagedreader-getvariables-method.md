---
title: "ISymUnmanagedReader::GetVariables (Método)"
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
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 86a0f8ed0a73661b80a9a196682e9539a3b97141
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="3415e-102">ISymUnmanagedReader::GetVariables (Método)</span><span class="sxs-lookup"><span data-stu-id="3415e-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="3415e-103">Devuelve una variable no local, según su elemento primario y su nombre.</span><span class="sxs-lookup"><span data-stu-id="3415e-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3415e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3415e-104">Syntax</span></span>  
  
```  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3415e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3415e-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="3415e-106">[in] El elemento primario de la variable.</span><span class="sxs-lookup"><span data-stu-id="3415e-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="3415e-107">[in] Tamaño de la matriz `pVars`.</span><span class="sxs-lookup"><span data-stu-id="3415e-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="3415e-108">[out] Un puntero a la variable que recibe el número de variables devueltas en `pVars`.</span><span class="sxs-lookup"><span data-stu-id="3415e-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="3415e-109">[out] Un puntero a la variable que recibe las variables.</span><span class="sxs-lookup"><span data-stu-id="3415e-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3415e-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3415e-110">Return Value</span></span>  
 <span data-ttu-id="3415e-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="3415e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3415e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3415e-112">Requirements</span></span>  
 <span data-ttu-id="3415e-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3415e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3415e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3415e-114">See Also</span></span>  
 [<span data-ttu-id="3415e-115">ISymUnmanagedReader (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3415e-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
