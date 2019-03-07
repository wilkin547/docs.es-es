---
title: ICorDebugNativeFrame2::IsMatchingParentFrame (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 56d2c28529d3f3ee87fe3fdedd91634133ebf864
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492210"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="3536f-102">ICorDebugNativeFrame2::IsMatchingParentFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="3536f-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="3536f-103">Determina si el marco especificado es el elemento primario del fotograma actual.</span><span class="sxs-lookup"><span data-stu-id="3536f-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3536f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3536f-104">Syntax</span></span>  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3536f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3536f-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="3536f-106">[in] Un puntero al objeto de marco que se va a evaluar para el estado del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="3536f-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="3536f-107">[out] `true` si `pPotentialParentFrame` es elemento primario del fotograma actual; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3536f-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3536f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3536f-108">Return Value</span></span>  
 <span data-ttu-id="3536f-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="3536f-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3536f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3536f-110">HRESULT</span></span>|<span data-ttu-id="3536f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3536f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3536f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3536f-112">S_OK</span></span>|<span data-ttu-id="3536f-113">El estado del primario se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3536f-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="3536f-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3536f-114">E_FAIL</span></span>|<span data-ttu-id="3536f-115">No se pudo devolver el estado del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="3536f-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="3536f-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3536f-116">E_INVALIDARG</span></span>|<span data-ttu-id="3536f-117">`pPotentialParentFrame` o `pIsParent` es null.</span><span class="sxs-lookup"><span data-stu-id="3536f-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="3536f-118">Excepciones</span><span class="sxs-lookup"><span data-stu-id="3536f-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3536f-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3536f-119">Remarks</span></span>  
 <span data-ttu-id="3536f-120">`IsMatchingParentFrame` Devuelve `true` si el objeto de marco se pasa al método es el elemento primario del objeto de marco en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="3536f-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="3536f-121">Si llama al método en un marco que no es un elemento secundario del marco especificado, devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="3536f-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3536f-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3536f-122">Requirements</span></span>  
 <span data-ttu-id="3536f-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3536f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3536f-124">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3536f-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3536f-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3536f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3536f-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3536f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3536f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="3536f-127">See also</span></span>
- [<span data-ttu-id="3536f-128">ICorDebugNativeFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3536f-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="3536f-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3536f-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3536f-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="3536f-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
