---
title: ICorProfilerFunctionControl::SetILFunctionBody (método)
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
ms.openlocfilehash: bebc0cf6ac7912ea3a6641e0c729b759e865dac3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864666"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="9cdec-102">ICorProfilerFunctionControl::SetILFunctionBody (método)</span><span class="sxs-lookup"><span data-stu-id="9cdec-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="9cdec-103">Reemplaza el cuerpo del Lenguaje intermedio común (CIL) del método.</span><span class="sxs-lookup"><span data-stu-id="9cdec-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cdec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9cdec-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cdec-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9cdec-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="9cdec-106">[in] El tamaño total del nuevo CIL, incluido el encabezado y cualquier estructura que venga después del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="9cdec-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="9cdec-107">[in] Puntero al nuevo encabezado de CIL.</span><span class="sxs-lookup"><span data-stu-id="9cdec-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cdec-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9cdec-108">Return Value</span></span>  
 <span data-ttu-id="9cdec-109">Este método devuelve los siguientes HRESULT concretos.</span><span class="sxs-lookup"><span data-stu-id="9cdec-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="9cdec-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9cdec-110">HRESULT</span></span>|<span data-ttu-id="9cdec-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9cdec-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9cdec-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9cdec-112">S_OK</span></span>|<span data-ttu-id="9cdec-113">El reemplazo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="9cdec-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cdec-114">Notas</span><span class="sxs-lookup"><span data-stu-id="9cdec-114">Remarks</span></span>  
 <span data-ttu-id="9cdec-115">A diferencia del método [ICorProfilerInfo:: SetILFunctionBody (](icorprofilerinfo-setilfunctionbody-method.md) , el método `SetILFunctionBody` administra la memoria necesaria para el nuevo cuerpo de CIL.</span><span class="sxs-lookup"><span data-stu-id="9cdec-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="9cdec-116">Esto significa que no es necesario asignar el cuerpo de CIL proporcionado por el generador de perfiles utilizando la interfaz [IMethodMalloc](imethodmalloc-interface.md) o asignada dentro de un intervalo determinado.</span><span class="sxs-lookup"><span data-stu-id="9cdec-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="9cdec-117">sino que se puede asignar en cualquier montón.</span><span class="sxs-lookup"><span data-stu-id="9cdec-117">It can be allocated on any heap.</span></span> <span data-ttu-id="9cdec-118">El generador de perfiles puede liberar la memoria usada para su cuerpo de CIL después de que `SetILFunctionBody` devuelve.</span><span class="sxs-lookup"><span data-stu-id="9cdec-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cdec-119">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="9cdec-119">Requirements</span></span>  
 <span data-ttu-id="9cdec-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cdec-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cdec-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9cdec-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9cdec-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cdec-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cdec-123">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cdec-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cdec-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cdec-124">See also</span></span>

- [<span data-ttu-id="9cdec-125">ICorProfilerFunctionControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9cdec-125">ICorProfilerFunctionControl Interface</span></span>](icorprofilerfunctioncontrol-interface.md)
