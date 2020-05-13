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
ms.openlocfilehash: 4a01ccd4e5cb9aadc6a693b2c6ceaff31c114bbc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209895"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="4d2ce-102">ICorDebugInternalFrame2::IsCloserToLeaf (Método)</span><span class="sxs-lookup"><span data-stu-id="4d2ce-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>
<span data-ttu-id="4d2ce-103">Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="4d2ce-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d2ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d2ce-104">Syntax</span></span>  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d2ce-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d2ce-105">Parameters</span></span>  
 `pFrameToCompare`  
 <span data-ttu-id="4d2ce-106">de Puntero al objeto de comparación `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="4d2ce-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="4d2ce-107">[out] `true` Si el `this` marco interno está más cerca de la hoja que el marco especificado por `pFrameToCompare` ; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="4d2ce-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d2ce-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4d2ce-108">Return Value</span></span>  
 <span data-ttu-id="4d2ce-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="4d2ce-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4d2ce-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4d2ce-110">HRESULT</span></span>|<span data-ttu-id="4d2ce-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d2ce-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4d2ce-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d2ce-112">S_OK</span></span>|<span data-ttu-id="4d2ce-113">La comparación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d2ce-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="4d2ce-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4d2ce-114">E_FAIL</span></span>|<span data-ttu-id="4d2ce-115">No se pudo realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="4d2ce-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="4d2ce-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4d2ce-116">E_INVALIDARG</span></span>|<span data-ttu-id="4d2ce-117">`pFrameToCompare` o `pIsCloser` es null.</span><span class="sxs-lookup"><span data-stu-id="4d2ce-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d2ce-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4d2ce-118">Remarks</span></span>  
 <span data-ttu-id="4d2ce-119">`IsCloserToLeaf`se puede usar para implementar una directiva para intercalar Marcos internos con otros marcos en la pila.</span><span class="sxs-lookup"><span data-stu-id="4d2ce-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d2ce-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d2ce-120">Requirements</span></span>  
 <span data-ttu-id="4d2ce-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d2ce-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d2ce-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d2ce-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d2ce-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d2ce-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d2ce-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d2ce-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d2ce-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d2ce-125">See also</span></span>

- [<span data-ttu-id="4d2ce-126">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d2ce-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="4d2ce-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4d2ce-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4d2ce-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="4d2ce-128">Debugging</span></span>](index.md)
