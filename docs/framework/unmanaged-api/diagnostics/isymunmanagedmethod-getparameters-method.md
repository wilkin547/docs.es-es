---
title: "ISymUnmanagedMethod::GetParameters (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetParameters
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a2e3471b63f819bfe1879b87e42ff9258036356
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="cd685-102">ISymUnmanagedMethod::GetParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="cd685-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="cd685-103">Obtiene los parámetros de este método.</span><span class="sxs-lookup"><span data-stu-id="cd685-103">Gets the parameters for this method.</span></span> <span data-ttu-id="cd685-104">Los parámetros se devuelven en el orden en que se definen dentro de la firma del método.</span><span class="sxs-lookup"><span data-stu-id="cd685-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd685-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd685-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd685-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd685-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="cd685-107">[in] Tamaño de la matriz `params`.</span><span class="sxs-lookup"><span data-stu-id="cd685-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="cd685-108">[in] Un puntero a un `ULONG32` que recibe el tamaño del búfer necesario para contener los parámetros.</span><span class="sxs-lookup"><span data-stu-id="cd685-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="cd685-109">[out] Un puntero al búfer que recibe los parámetros.</span><span class="sxs-lookup"><span data-stu-id="cd685-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd685-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cd685-110">Return Value</span></span>  
 <span data-ttu-id="cd685-111">S_OK si el método tiene éxito; en caso contrario, E_FAIL u otro código de error.</span><span class="sxs-lookup"><span data-stu-id="cd685-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd685-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd685-112">Requirements</span></span>  
 <span data-ttu-id="cd685-113">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cd685-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd685-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd685-114">See Also</span></span>  
 [<span data-ttu-id="cd685-115">ISymUnmanagedMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd685-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
