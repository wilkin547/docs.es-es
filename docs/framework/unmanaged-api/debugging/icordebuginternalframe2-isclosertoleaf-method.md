---
title: ICorDebugInternalFrame2::IsCloserToLeaf (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0e72d15ab4ca9b4468efb2a671022f30bfb3cc6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759949"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="25425-102">ICorDebugInternalFrame2::IsCloserToLeaf (Método)</span><span class="sxs-lookup"><span data-stu-id="25425-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="25425-103">Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="25425-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25425-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25425-104">Syntax</span></span>  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25425-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25425-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="25425-106">[in] Un puntero a la comparación `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="25425-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="25425-107">[out] `true` si el `this` marco interno está más cerca de la hoja que el intervalo especificado por `pFrameToCompare`; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="25425-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25425-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="25425-108">Return Value</span></span>  
 <span data-ttu-id="25425-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="25425-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="25425-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="25425-110">HRESULT</span></span>|<span data-ttu-id="25425-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="25425-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="25425-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="25425-112">S_OK</span></span>|<span data-ttu-id="25425-113">La comparación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="25425-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="25425-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="25425-114">E_FAIL</span></span>|<span data-ttu-id="25425-115">No se pudo realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="25425-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="25425-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="25425-116">E_INVALIDARG</span></span>|<span data-ttu-id="25425-117">`pFrameToCompare` o `pIsCloser` es null.</span><span class="sxs-lookup"><span data-stu-id="25425-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25425-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25425-118">Remarks</span></span>  
 <span data-ttu-id="25425-119">`IsCloserToLeaf` puede utilizarse para implementar una directiva para una intercalación de los marcos internos con otros marcos de la pila.</span><span class="sxs-lookup"><span data-stu-id="25425-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25425-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25425-120">Requirements</span></span>  
 <span data-ttu-id="25425-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25425-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25425-122">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25425-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25425-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25425-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25425-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25425-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25425-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="25425-125">See also</span></span>

- [<span data-ttu-id="25425-126">ICorDebugInternalFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="25425-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="25425-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="25425-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="25425-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="25425-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
