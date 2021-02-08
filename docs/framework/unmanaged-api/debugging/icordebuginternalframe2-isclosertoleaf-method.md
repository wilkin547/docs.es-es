---
description: 'Más información sobre: ICorDebugInternalFrame2:: Isclosertoleaf ((método)'
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
ms.openlocfilehash: d773f8670f600a5bcd2a8dad7f23fe243195957c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801285"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="10a19-103">ICorDebugInternalFrame2::IsCloserToLeaf (Método)</span><span class="sxs-lookup"><span data-stu-id="10a19-103">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>

<span data-ttu-id="10a19-104">Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="10a19-104">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a19-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10a19-105">Syntax</span></span>  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10a19-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10a19-106">Parameters</span></span>  

 `pFrameToCompare`  
 <span data-ttu-id="10a19-107">de Puntero al objeto de comparación `ICorDebugFrame` .</span><span class="sxs-lookup"><span data-stu-id="10a19-107">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="10a19-108">[out] `true` Si el `this` marco interno está más cerca de la hoja que el marco especificado por `pFrameToCompare` ; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="10a19-108">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10a19-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="10a19-109">Return Value</span></span>  

 <span data-ttu-id="10a19-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="10a19-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="10a19-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10a19-111">HRESULT</span></span>|<span data-ttu-id="10a19-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="10a19-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10a19-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="10a19-113">S_OK</span></span>|<span data-ttu-id="10a19-114">La comparación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="10a19-114">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="10a19-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10a19-115">E_FAIL</span></span>|<span data-ttu-id="10a19-116">No se pudo realizar la comparación.</span><span class="sxs-lookup"><span data-stu-id="10a19-116">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="10a19-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="10a19-117">E_INVALIDARG</span></span>|<span data-ttu-id="10a19-118">`pFrameToCompare` o `pIsCloser` es null.</span><span class="sxs-lookup"><span data-stu-id="10a19-118">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10a19-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="10a19-119">Remarks</span></span>  

 <span data-ttu-id="10a19-120">`IsCloserToLeaf` se puede usar para implementar una directiva para intercalar Marcos internos con otros marcos en la pila.</span><span class="sxs-lookup"><span data-stu-id="10a19-120">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10a19-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10a19-121">Requirements</span></span>  

 <span data-ttu-id="10a19-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10a19-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10a19-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10a19-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10a19-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10a19-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10a19-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a19-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a19-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="10a19-126">See also</span></span>

- [<span data-ttu-id="10a19-127">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="10a19-127">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="10a19-128">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="10a19-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="10a19-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="10a19-129">Debugging</span></span>](index.md)
