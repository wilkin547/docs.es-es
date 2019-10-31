---
title: ICorDebugNativeFrame2::GetStackParameterSize (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 4dd9760c347bbc23f3e8225c1ff748c6b7b8bfe1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096537"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="143a4-102">ICorDebugNativeFrame2::GetStackParameterSize (Método)</span><span class="sxs-lookup"><span data-stu-id="143a4-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="143a4-103">Devuelve el tamaño acumulado de los parámetros de la pila en los sistemas operativos x86.</span><span class="sxs-lookup"><span data-stu-id="143a4-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="143a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="143a4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="143a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="143a4-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="143a4-106">enuncia Puntero al tamaño acumulado de los parámetros de la pila.</span><span class="sxs-lookup"><span data-stu-id="143a4-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="143a4-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="143a4-107">Return Value</span></span>  
 <span data-ttu-id="143a4-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="143a4-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="143a4-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="143a4-109">HRESULT</span></span>|<span data-ttu-id="143a4-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="143a4-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="143a4-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="143a4-111">S_OK</span></span>|<span data-ttu-id="143a4-112">El tamaño de la pila se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="143a4-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="143a4-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="143a4-113">S_FALSE</span></span>|<span data-ttu-id="143a4-114">se llamó a `GetStackParameterSize` en una plataforma distinta de x86.</span><span class="sxs-lookup"><span data-stu-id="143a4-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="143a4-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="143a4-115">E_FAIL</span></span>|<span data-ttu-id="143a4-116">`The size of the parameters could not be returned`Operador</span><span class="sxs-lookup"><span data-stu-id="143a4-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="143a4-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="143a4-117">E_INVALIDARG</span></span>|<span data-ttu-id="143a4-118">`pSize` es `null`.</span><span class="sxs-lookup"><span data-stu-id="143a4-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="143a4-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="143a4-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="143a4-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="143a4-120">Remarks</span></span>  
 <span data-ttu-id="143a4-121">Los métodos [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) no ajustan el puntero de pila para los parámetros que se insertan en la pila.</span><span class="sxs-lookup"><span data-stu-id="143a4-121">The [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="143a4-122">En su lugar, puede usar el valor devuelto por `GetStackParameterSize` para ajustar el puntero de la pila y, de este modo, inicializar un desenredado nativo, que se ajusta para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="143a4-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="143a4-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="143a4-123">Requirements</span></span>  
 <span data-ttu-id="143a4-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="143a4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="143a4-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="143a4-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="143a4-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="143a4-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="143a4-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="143a4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="143a4-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="143a4-128">See also</span></span>

- [<span data-ttu-id="143a4-129">ICorDebugNativeFrame2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="143a4-129">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="143a4-130">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="143a4-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="143a4-131">Depuración</span><span class="sxs-lookup"><span data-stu-id="143a4-131">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
