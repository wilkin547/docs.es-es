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
ms.openlocfilehash: 83d3eda0f3c4619ec7a5df91d13ab9f3a58e5f01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721353"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="99ed9-102">ICorDebugInternalFrame2::IsCloserToLeaf (Método)</span><span class="sxs-lookup"><span data-stu-id="99ed9-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>

<span data-ttu-id="99ed9-103">Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="99ed9-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99ed9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99ed9-104">Syntax</span></span>  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99ed9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99ed9-105">Parameters</span></span>  

 `pFrameToCompare`  
 <span data-ttu-id="99ed9-106">de Puntero al objeto de comparación `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="99ed9-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="99ed9-107">[out] `true` Si el `this` marco interno está más cerca de la hoja que el marco especificado por `pFrameToCompare` ; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="99ed9-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99ed9-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="99ed9-108">Return Value</span></span>  

 <span data-ttu-id="99ed9-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="99ed9-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="99ed9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99ed9-110">HRESULT</span></span>|<span data-ttu-id="99ed9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="99ed9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99ed9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="99ed9-112">S_OK</span></span>|<span data-ttu-id="99ed9-113">La comparación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="99ed9-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="99ed9-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="99ed9-114">E_FAIL</span></span>|<span data-ttu-id="99ed9-115">No se pudo realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="99ed9-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="99ed9-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="99ed9-116">E_INVALIDARG</span></span>|<span data-ttu-id="99ed9-117">`pFrameToCompare` o `pIsCloser` es null.</span><span class="sxs-lookup"><span data-stu-id="99ed9-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99ed9-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="99ed9-118">Remarks</span></span>  

 <span data-ttu-id="99ed9-119">`IsCloserToLeaf` se puede usar para implementar una directiva para intercalar Marcos internos con otros marcos en la pila.</span><span class="sxs-lookup"><span data-stu-id="99ed9-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99ed9-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99ed9-120">Requirements</span></span>  

 <span data-ttu-id="99ed9-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99ed9-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99ed9-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99ed9-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99ed9-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99ed9-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99ed9-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99ed9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ed9-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99ed9-125">See also</span></span>

- [<span data-ttu-id="99ed9-126">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99ed9-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="99ed9-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="99ed9-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="99ed9-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="99ed9-128">Debugging</span></span>](index.md)
