---
title: "ICorDebugInternalFrame2::IsCloserToLeaf (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 60e63800ade5fb0d4a222d80ebfe43c3d84c2815
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="ac87a-102">ICorDebugInternalFrame2::IsCloserToLeaf (Método)</span><span class="sxs-lookup"><span data-stu-id="ac87a-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="ac87a-103">Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="ac87a-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac87a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac87a-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac87a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac87a-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="ac87a-106">[in] Un puntero a la comparación `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="ac87a-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="ac87a-107">[out] `true` si la `this` marco interno está más cerca de la hoja que el intervalo especificado por `pFrameToCompare`; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ac87a-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac87a-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ac87a-108">Return Value</span></span>  
 <span data-ttu-id="ac87a-109">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="ac87a-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ac87a-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac87a-110">HRESULT</span></span>|<span data-ttu-id="ac87a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac87a-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac87a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac87a-112">S_OK</span></span>|<span data-ttu-id="ac87a-113">La comparación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ac87a-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="ac87a-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac87a-114">E_FAIL</span></span>|<span data-ttu-id="ac87a-115">No se pudo realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="ac87a-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="ac87a-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ac87a-116">E_INVALIDARG</span></span>|<span data-ttu-id="ac87a-117">`pFrameToCompare` o `pIsCloser` es null.</span><span class="sxs-lookup"><span data-stu-id="ac87a-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac87a-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac87a-118">Remarks</span></span>  
 <span data-ttu-id="ac87a-119">`IsCloserToLeaf`puede utilizarse para implementar una directiva para intercalar marcos internos con otros marcos de la pila.</span><span class="sxs-lookup"><span data-stu-id="ac87a-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac87a-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac87a-120">Requirements</span></span>  
 <span data-ttu-id="ac87a-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac87a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac87a-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac87a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac87a-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac87a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac87a-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac87a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac87a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac87a-125">See Also</span></span>  
 [<span data-ttu-id="ac87a-126">ICorDebugInternalFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac87a-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 [<span data-ttu-id="ac87a-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ac87a-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ac87a-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="ac87a-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
