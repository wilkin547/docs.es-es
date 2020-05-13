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
ms.openlocfilehash: b88b3907eb555050de93f35411629b2bd30c7375
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212950"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="b7c2a-102">ICorDebugNativeFrame2::GetStackParameterSize (Método)</span><span class="sxs-lookup"><span data-stu-id="b7c2a-102">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>
<span data-ttu-id="b7c2a-103">Devuelve el tamaño acumulado de los parámetros de la pila en los sistemas operativos x86.</span><span class="sxs-lookup"><span data-stu-id="b7c2a-103">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7c2a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7c2a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7c2a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7c2a-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="b7c2a-106">enuncia Puntero al tamaño acumulado de los parámetros de la pila.</span><span class="sxs-lookup"><span data-stu-id="b7c2a-106">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7c2a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b7c2a-107">Return Value</span></span>  
 <span data-ttu-id="b7c2a-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="b7c2a-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b7c2a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b7c2a-109">HRESULT</span></span>|<span data-ttu-id="b7c2a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7c2a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b7c2a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b7c2a-111">S_OK</span></span>|<span data-ttu-id="b7c2a-112">El tamaño de la pila se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b7c2a-112">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="b7c2a-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b7c2a-113">S_FALSE</span></span>|<span data-ttu-id="b7c2a-114">`GetStackParameterSize`se llamó a en una plataforma distinta de x86.</span><span class="sxs-lookup"><span data-stu-id="b7c2a-114">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="b7c2a-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b7c2a-115">E_FAIL</span></span>|<span data-ttu-id="b7c2a-116">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="b7c2a-116">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="b7c2a-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b7c2a-117">E_INVALIDARG</span></span>|<span data-ttu-id="b7c2a-118">`pSize`Es `null` .</span><span class="sxs-lookup"><span data-stu-id="b7c2a-118">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="b7c2a-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="b7c2a-119">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7c2a-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b7c2a-120">Remarks</span></span>  
 <span data-ttu-id="b7c2a-121">Los métodos [ICorDebugStackWalk](icordebugstackwalk-interface.md) no ajustan el puntero de pila para los parámetros que se insertan en la pila.</span><span class="sxs-lookup"><span data-stu-id="b7c2a-121">The [ICorDebugStackWalk](icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="b7c2a-122">En su lugar, puede usar el valor devuelto por `GetStackParameterSize` para ajustar el puntero de la pila y, de este modo, inicializar un desenredado nativo, que se ajusta para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="b7c2a-122">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7c2a-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7c2a-123">Requirements</span></span>  
 <span data-ttu-id="b7c2a-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7c2a-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7c2a-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7c2a-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7c2a-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7c2a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7c2a-127">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7c2a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c2a-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b7c2a-128">See also</span></span>

- [<span data-ttu-id="b7c2a-129">ICorDebugNativeFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7c2a-129">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="b7c2a-130">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="b7c2a-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b7c2a-131">Depuración</span><span class="sxs-lookup"><span data-stu-id="b7c2a-131">Debugging</span></span>](index.md)
