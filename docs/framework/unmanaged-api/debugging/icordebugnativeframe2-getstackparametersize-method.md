---
description: 'Más información sobre: ICorDebugNativeFrame2:: Getstackparametersize ((método)'
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
ms.openlocfilehash: 08a17ced0be75737c1c49aa3f9bb42b13bbe8aa0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722339"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a><span data-ttu-id="4b134-103">ICorDebugNativeFrame2::GetStackParameterSize (Método)</span><span class="sxs-lookup"><span data-stu-id="4b134-103">ICorDebugNativeFrame2::GetStackParameterSize Method</span></span>

<span data-ttu-id="4b134-104">Devuelve el tamaño acumulado de los parámetros de la pila en los sistemas operativos x86.</span><span class="sxs-lookup"><span data-stu-id="4b134-104">Returns the cumulative size of the parameters on the stack on x86 operating systems.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b134-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b134-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b134-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b134-106">Parameters</span></span>  

 `pSize`  
 <span data-ttu-id="4b134-107">enuncia Puntero al tamaño acumulado de los parámetros de la pila.</span><span class="sxs-lookup"><span data-stu-id="4b134-107">[out] A pointer to the cumulative size of the parameters on the stack.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b134-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4b134-108">Return Value</span></span>  

 <span data-ttu-id="4b134-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="4b134-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4b134-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b134-110">HRESULT</span></span>|<span data-ttu-id="4b134-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b134-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b134-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b134-112">S_OK</span></span>|<span data-ttu-id="4b134-113">El tamaño de la pila se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4b134-113">The stack size was successfully returned.</span></span>|  
|<span data-ttu-id="4b134-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4b134-114">S_FALSE</span></span>|<span data-ttu-id="4b134-115">`GetStackParameterSize` se llamó a en una plataforma distinta de x86.</span><span class="sxs-lookup"><span data-stu-id="4b134-115">`GetStackParameterSize` was called on a non-x86 platform.</span></span>|  
|<span data-ttu-id="4b134-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4b134-116">E_FAIL</span></span>|<span data-ttu-id="4b134-117">`The size of the parameters could not be returned`.</span><span class="sxs-lookup"><span data-stu-id="4b134-117">`The size of the parameters could not be returned`.</span></span>|  
|<span data-ttu-id="4b134-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4b134-118">E_INVALIDARG</span></span>|<span data-ttu-id="4b134-119">`pSize` Es `null` .</span><span class="sxs-lookup"><span data-stu-id="4b134-119">`pSize` Is `null`.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="4b134-120">Excepciones</span><span class="sxs-lookup"><span data-stu-id="4b134-120">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b134-121">Notas</span><span class="sxs-lookup"><span data-stu-id="4b134-121">Remarks</span></span>  

 <span data-ttu-id="4b134-122">Los métodos [ICorDebugStackWalk](icordebugstackwalk-interface.md) no ajustan el puntero de pila para los parámetros que se insertan en la pila.</span><span class="sxs-lookup"><span data-stu-id="4b134-122">The [ICorDebugStackWalk](icordebugstackwalk-interface.md) methods do not adjust the stack pointer for parameters that are pushed on the stack.</span></span> <span data-ttu-id="4b134-123">En su lugar, puede usar el valor devuelto por `GetStackParameterSize` para ajustar el puntero de la pila y, de este modo, inicializar un desenredado nativo, que se ajusta para los parámetros.</span><span class="sxs-lookup"><span data-stu-id="4b134-123">Instead, you can use the value returned by `GetStackParameterSize` to adjust the stack pointer to seed a native unwinder, which does adjust for the parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b134-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b134-124">Requirements</span></span>  

 <span data-ttu-id="4b134-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b134-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b134-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b134-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b134-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b134-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b134-128">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b134-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b134-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b134-129">See also</span></span>

- [<span data-ttu-id="4b134-130">ICorDebugNativeFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b134-130">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="4b134-131">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="4b134-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4b134-132">Depuración</span><span class="sxs-lookup"><span data-stu-id="4b134-132">Debugging</span></span>](index.md)
