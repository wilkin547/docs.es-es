---
description: 'Más información sobre: ICorProfilerFunctionControl:: SetILFunctionBody ((método)'
title: ICorProfilerFunctionControl::SetILFunctionBody (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
ms.openlocfilehash: 470eefce5b211adcfd111951be9a004b3bd7d8fc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781615"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="ff076-103">ICorProfilerFunctionControl::SetILFunctionBody (Método)</span><span class="sxs-lookup"><span data-stu-id="ff076-103">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>

<span data-ttu-id="ff076-104">Reemplaza el cuerpo del Lenguaje intermedio común (CIL) del método.</span><span class="sxs-lookup"><span data-stu-id="ff076-104">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff076-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff076-105">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff076-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff076-106">Parameters</span></span>  

 `cbNewILMethodHeader`  
 <span data-ttu-id="ff076-107">[in] El tamaño total del nuevo CIL, incluido el encabezado y cualquier estructura que venga después del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="ff076-107">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="ff076-108">[in] Puntero al nuevo encabezado de CIL.</span><span class="sxs-lookup"><span data-stu-id="ff076-108">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff076-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ff076-109">Return Value</span></span>  

 <span data-ttu-id="ff076-110">Este método devuelve los siguientes HRESULT concretos.</span><span class="sxs-lookup"><span data-stu-id="ff076-110">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="ff076-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ff076-111">HRESULT</span></span>|<span data-ttu-id="ff076-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff076-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff076-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff076-113">S_OK</span></span>|<span data-ttu-id="ff076-114">El reemplazo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="ff076-114">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff076-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ff076-115">Remarks</span></span>  

 <span data-ttu-id="ff076-116">A diferencia del método [ICorProfilerInfo:: SetILFunctionBody (](icorprofilerinfo-setilfunctionbody-method.md) , el `SetILFunctionBody` método administra la memoria necesaria para el nuevo cuerpo de CIL.</span><span class="sxs-lookup"><span data-stu-id="ff076-116">Unlike the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="ff076-117">Esto significa que no es necesario asignar el cuerpo de CIL proporcionado por el generador de perfiles utilizando la interfaz [IMethodMalloc](imethodmalloc-interface.md) o asignada dentro de un intervalo determinado.</span><span class="sxs-lookup"><span data-stu-id="ff076-117">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="ff076-118">sino que se puede asignar en cualquier montón.</span><span class="sxs-lookup"><span data-stu-id="ff076-118">It can be allocated on any heap.</span></span> <span data-ttu-id="ff076-119">El generador de perfiles puede liberar la memoria que se usa para el cuerpo de CIL después de la `SetILFunctionBody` devolución.</span><span class="sxs-lookup"><span data-stu-id="ff076-119">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff076-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff076-120">Requirements</span></span>  

 <span data-ttu-id="ff076-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff076-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff076-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff076-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff076-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff076-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff076-124">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff076-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff076-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff076-125">See also</span></span>

- [<span data-ttu-id="ff076-126">ICorProfilerFunctionControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff076-126">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)
