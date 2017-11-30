---
title: "ICorDebugNativeFrame2::GetStackParameterSize (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame2.GetStackParameterSize Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c265cb564718b362b1354189e59dc217b2866b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="7dfbe-102">ICorDebugNativeFrame2::GetStackParameterSize (Método)</span><span class="sxs-lookup"><span data-stu-id="7dfbe-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="7dfbe-103">Devuelve el tamaño acumulado de los parámetros en la pila en x86 sistemas operativos.</span><span class="sxs-lookup"><span data-stu-id="7dfbe-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dfbe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7dfbe-104">Syntax</span></span>  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7dfbe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7dfbe-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="7dfbe-106">[out] Un puntero al tamaño acumulado de los parámetros en la pila.</span><span class="sxs-lookup"><span data-stu-id="7dfbe-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7dfbe-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7dfbe-107">Return Value</span></span>  
 <span data-ttu-id="7dfbe-108">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="7dfbe-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7dfbe-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7dfbe-109">HRESULT</span></span>|<span data-ttu-id="7dfbe-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7dfbe-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7dfbe-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7dfbe-111">S_OK</span></span>|<span data-ttu-id="7dfbe-112">El tamaño de pila se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7dfbe-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="7dfbe-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="7dfbe-113">S_FALSE</span></span>|<span data-ttu-id="7dfbe-114">`GetStackParameterSize`se llamó en una plataforma no x86.</span><span class="sxs-lookup"><span data-stu-id="7dfbe-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="7dfbe-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7dfbe-115">E_FAIL</span></span>|<span data-ttu-id="7dfbe-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="7dfbe-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="7dfbe-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7dfbe-117">E_INVALIDARG</span></span>|<span data-ttu-id="7dfbe-118">`pSize`Es `null`.</span><span class="sxs-lookup"><span data-stu-id="7dfbe-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="7dfbe-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="7dfbe-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dfbe-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7dfbe-120">Remarks</span></span>  
 <span data-ttu-id="7dfbe-121">El [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) métodos no ajustan el puntero de pila para los parámetros que se insertan en la pila.</span><span class="sxs-lookup"><span data-stu-id="7dfbe-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="7dfbe-122">En su lugar, puede usar el valor devuelto por `GetStackParameterSize` para ajustar el puntero de pila para inicializar un desenredador nativo, que ajusta los parámetros.</span><span class="sxs-lookup"><span data-stu-id="7dfbe-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dfbe-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7dfbe-123">Requirements</span></span>  
 <span data-ttu-id="7dfbe-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dfbe-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dfbe-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7dfbe-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7dfbe-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7dfbe-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7dfbe-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dfbe-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dfbe-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dfbe-128">See Also</span></span>  
 [<span data-ttu-id="7dfbe-129">ICorDebugNativeFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7dfbe-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [<span data-ttu-id="7dfbe-130">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7dfbe-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="7dfbe-131">Depuración</span><span class="sxs-lookup"><span data-stu-id="7dfbe-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
