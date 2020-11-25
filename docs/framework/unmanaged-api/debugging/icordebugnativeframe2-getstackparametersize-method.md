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
ms.openlocfilehash: 21af3980de9b5a768b6af9a8aca74b693c7ac528
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695497"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="99f2b-102">ICorDebugNativeFrame2::GetStackParameterSize (Método)</span><span class="sxs-lookup"><span data-stu-id="99f2b-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>

<span data-ttu-id="99f2b-103">Devuelve el tamaño acumulado de los parámetros de la pila en los sistemas operativos x86.</span><span class="sxs-lookup"><span data-stu-id="99f2b-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99f2b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99f2b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="99f2b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="99f2b-105">Parameters</span></span>  

 `pSize`  
 <span data-ttu-id="99f2b-106">enuncia Puntero al tamaño acumulado de los parámetros de la pila.</span><span class="sxs-lookup"><span data-stu-id="99f2b-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99f2b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="99f2b-107">Return Value</span></span>  

 <span data-ttu-id="99f2b-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="99f2b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="99f2b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99f2b-109">HRESULT</span></span>|<span data-ttu-id="99f2b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="99f2b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99f2b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="99f2b-111">S_OK</span></span>|<span data-ttu-id="99f2b-112">El tamaño de la pila se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="99f2b-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="99f2b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="99f2b-113">S_FALSE</span></span>|<span data-ttu-id="99f2b-114">`GetStackParameterSize` se llamó a en una plataforma distinta de x86.</span><span class="sxs-lookup"><span data-stu-id="99f2b-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="99f2b-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="99f2b-115">E_FAIL</span></span>|<span data-ttu-id="99f2b-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="99f2b-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="99f2b-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="99f2b-117">E_INVALIDARG</span></span>|<span data-ttu-id="99f2b-118">`pSize` Es `null` .</span><span class="sxs-lookup"><span data-stu-id="99f2b-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="99f2b-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="99f2b-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99f2b-120">Notas</span><span class="sxs-lookup"><span data-stu-id="99f2b-120">Remarks</span></span>  

 <span data-ttu-id="99f2b-121">Los métodos [ICorDebugStackWalk](icordebugstackwalk-interface.md) no ajustan el puntero de pila para los parámetros que se insertan en la pila.</span><span class="sxs-lookup"><span data-stu-id="99f2b-121">The [ICorDebugStackWalk](icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="99f2b-122">En su lugar, puede usar el valor devuelto por `GetStackParameterSize` para ajustar el puntero de la pila y, de este modo, inicializar un desenredado nativo, que se ajusta para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="99f2b-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99f2b-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="99f2b-123">Requirements</span></span>  

 <span data-ttu-id="99f2b-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99f2b-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99f2b-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99f2b-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99f2b-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99f2b-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99f2b-127">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99f2b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f2b-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="99f2b-128">See also</span></span>

- [<span data-ttu-id="99f2b-129">ICorDebugNativeFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="99f2b-129">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="99f2b-130">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="99f2b-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="99f2b-131">Depuración</span><span class="sxs-lookup"><span data-stu-id="99f2b-131">Debugging</span></span>](index.md)
