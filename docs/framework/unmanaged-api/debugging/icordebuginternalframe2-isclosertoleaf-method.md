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
ms.openlocfilehash: 30a9d26283d4f544bdd865e40cfc1c1c625ae462
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120905"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="18a7d-102">ICorDebugInternalFrame2::IsCloserToLeaf (Método)</span><span class="sxs-lookup"><span data-stu-id="18a7d-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="18a7d-103">Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="18a7d-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18a7d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18a7d-104">Syntax</span></span>  
  
```  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="18a7d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="18a7d-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="18a7d-106">[in] Un puntero a la comparación `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="18a7d-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="18a7d-107">[out] `true` si el `this` marco interno está más cerca de la hoja que el intervalo especificado por `pFrameToCompare`; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="18a7d-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18a7d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="18a7d-108">Return Value</span></span>  
 <span data-ttu-id="18a7d-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="18a7d-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="18a7d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="18a7d-110">HRESULT</span></span>|<span data-ttu-id="18a7d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="18a7d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="18a7d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="18a7d-112">S_OK</span></span>|<span data-ttu-id="18a7d-113">La comparación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="18a7d-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="18a7d-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="18a7d-114">E_FAIL</span></span>|<span data-ttu-id="18a7d-115">No se pudo realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="18a7d-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="18a7d-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="18a7d-116">E_INVALIDARG</span></span>|`pFrameToCompare` <span data-ttu-id="18a7d-117">o `pIsCloser` es null.</span><span class="sxs-lookup"><span data-stu-id="18a7d-117">or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18a7d-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="18a7d-118">Remarks</span></span>  
 `IsCloserToLeaf` <span data-ttu-id="18a7d-119">puede utilizarse para implementar una directiva para una intercalación de los marcos internos con otros marcos de la pila.</span><span class="sxs-lookup"><span data-stu-id="18a7d-119">can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18a7d-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18a7d-120">Requirements</span></span>  
 <span data-ttu-id="18a7d-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18a7d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18a7d-122">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18a7d-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18a7d-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18a7d-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="18a7d-124">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="18a7d-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18a7d-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="18a7d-125">See also</span></span>

- [<span data-ttu-id="18a7d-126">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="18a7d-126">ICorDebugInternalFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [<span data-ttu-id="18a7d-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="18a7d-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="18a7d-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="18a7d-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
