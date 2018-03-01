---
title: "ICorDebugNativeFrame2::GetStackParameterSize (Método)"
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
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fa7e67c252f2ece16c072e22d0333e085fbc4f65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="4093d-102">ICorDebugNativeFrame2::GetStackParameterSize (Método)</span><span class="sxs-lookup"><span data-stu-id="4093d-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="4093d-103">Devuelve el tamaño acumulado de los parámetros en la pila en x86 sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="4093d-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4093d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4093d-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4093d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4093d-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="4093d-106">[out] Un puntero al tamaño acumulado de los parámetros en la pila.</span><span class="sxs-lookup"><span data-stu-id="4093d-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4093d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4093d-107">Return Value</span></span>  
 <span data-ttu-id="4093d-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="4093d-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4093d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4093d-109">HRESULT</span></span>|<span data-ttu-id="4093d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4093d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4093d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4093d-111">S_OK</span></span>|<span data-ttu-id="4093d-112">El tamaño de pila se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4093d-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="4093d-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4093d-113">S_FALSE</span></span>|<span data-ttu-id="4093d-114">`GetStackParameterSize`se llamó en una plataforma no x86.</span><span class="sxs-lookup"><span data-stu-id="4093d-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="4093d-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4093d-115">E_FAIL</span></span>|<span data-ttu-id="4093d-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="4093d-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="4093d-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4093d-117">E_INVALIDARG</span></span>|<span data-ttu-id="4093d-118">`pSize`Es `null`.</span><span class="sxs-lookup"><span data-stu-id="4093d-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4093d-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="4093d-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4093d-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4093d-120">Remarks</span></span>  
 <span data-ttu-id="4093d-121">El [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) métodos no ajustan el puntero de pila para los parámetros que se insertan en la pila.</span><span class="sxs-lookup"><span data-stu-id="4093d-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="4093d-122">En su lugar, puede usar el valor devuelto por `GetStackParameterSize` para ajustar el puntero de pila para inicializar un desenredador nativo, que ajusta los parámetros.</span><span class="sxs-lookup"><span data-stu-id="4093d-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4093d-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4093d-123">Requirements</span></span>  
 <span data-ttu-id="4093d-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4093d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4093d-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4093d-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4093d-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4093d-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4093d-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4093d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4093d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4093d-128">See Also</span></span>  
 [<span data-ttu-id="4093d-129">ICorDebugNativeFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4093d-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="4093d-130">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4093d-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="4093d-131">Depuración</span><span class="sxs-lookup"><span data-stu-id="4093d-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
