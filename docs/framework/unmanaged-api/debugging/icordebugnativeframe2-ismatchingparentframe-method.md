---
title: "ICorDebugNativeFrame2::IsMatchingParentFrame (Método)"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fc2d8eacb05e861290ad19a34c261943dc2959a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="b31ee-102">ICorDebugNativeFrame2::IsMatchingParentFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="b31ee-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="b31ee-103">Determina si el marco especificado es el elemento primario del fotograma actual.</span><span class="sxs-lookup"><span data-stu-id="b31ee-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b31ee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b31ee-104">Syntax</span></span>  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b31ee-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b31ee-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="b31ee-106">[in] Un puntero al objeto de marco que se va a evaluar para el estado del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="b31ee-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="b31ee-107">[out] `true` si `pPotentialParentFrame` es primario del marco actual; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b31ee-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b31ee-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b31ee-108">Return Value</span></span>  
 <span data-ttu-id="b31ee-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="b31ee-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b31ee-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b31ee-110">HRESULT</span></span>|<span data-ttu-id="b31ee-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b31ee-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b31ee-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b31ee-112">S_OK</span></span>|<span data-ttu-id="b31ee-113">El estado del primario se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b31ee-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="b31ee-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b31ee-114">E_FAIL</span></span>|<span data-ttu-id="b31ee-115">No se pudo devolver el estado del primario.</span><span class="sxs-lookup"><span data-stu-id="b31ee-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="b31ee-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b31ee-116">E_INVALIDARG</span></span>|<span data-ttu-id="b31ee-117">`pPotentialParentFrame` o `pIsParent` es null.</span><span class="sxs-lookup"><span data-stu-id="b31ee-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="b31ee-118">Excepciones</span><span class="sxs-lookup"><span data-stu-id="b31ee-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b31ee-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b31ee-119">Remarks</span></span>  
 <span data-ttu-id="b31ee-120">`IsMatchingParentFrame`Devuelve `true` si el objeto de marco se pasa al método es el elemento primario del objeto de marco en el que se llamó al método.</span><span class="sxs-lookup"><span data-stu-id="b31ee-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="b31ee-121">Si llama al método en un marco que no es un elemento secundario del marco especificado, devuelve un error.</span><span class="sxs-lookup"><span data-stu-id="b31ee-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b31ee-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b31ee-122">Requirements</span></span>  
 <span data-ttu-id="b31ee-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b31ee-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b31ee-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b31ee-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b31ee-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b31ee-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b31ee-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b31ee-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b31ee-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b31ee-127">See Also</span></span>  
 [<span data-ttu-id="b31ee-128">ICorDebugNativeFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b31ee-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="b31ee-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b31ee-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="b31ee-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="b31ee-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
