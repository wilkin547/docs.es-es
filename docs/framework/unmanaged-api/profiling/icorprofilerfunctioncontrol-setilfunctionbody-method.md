---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e87d466e463cad2d9cd57c341812a0b57e025256
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479433"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="15ae2-102">ICorProfilerFunctionControl::SetILFunctionBody (Método)</span><span class="sxs-lookup"><span data-stu-id="15ae2-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="15ae2-103">Reemplaza el cuerpo del Lenguaje intermedio común (CIL) del método.</span><span class="sxs-lookup"><span data-stu-id="15ae2-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ae2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15ae2-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15ae2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15ae2-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="15ae2-106">[in] El tamaño total del nuevo CIL, incluido el encabezado y cualquier estructura que venga después del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="15ae2-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="15ae2-107">[in] Puntero al nuevo encabezado de CIL.</span><span class="sxs-lookup"><span data-stu-id="15ae2-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15ae2-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="15ae2-108">Return Value</span></span>  
 <span data-ttu-id="15ae2-109">Este método devuelve los siguientes HRESULT concretos.</span><span class="sxs-lookup"><span data-stu-id="15ae2-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="15ae2-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15ae2-110">HRESULT</span></span>|<span data-ttu-id="15ae2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="15ae2-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15ae2-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="15ae2-112">S_OK</span></span>|<span data-ttu-id="15ae2-113">El reemplazo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="15ae2-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15ae2-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15ae2-114">Remarks</span></span>  
 <span data-ttu-id="15ae2-115">A diferencia de la [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) método, el `SetILFunctionBody` método administra la memoria necesaria para el nuevo cuerpo CIL.</span><span class="sxs-lookup"><span data-stu-id="15ae2-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="15ae2-116">Esto significa que el cuerpo de CIL proporcionado por el generador de perfiles no tiene que asignar mediante el [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interfaz o dentro de un intervalo determinado.</span><span class="sxs-lookup"><span data-stu-id="15ae2-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="15ae2-117">sino que se puede asignar en cualquier montón.</span><span class="sxs-lookup"><span data-stu-id="15ae2-117">It can be allocated on any heap.</span></span> <span data-ttu-id="15ae2-118">El generador de perfiles puede liberar la memoria utilizada para el cuerpo CIL después `SetILFunctionBody` devuelve.</span><span class="sxs-lookup"><span data-stu-id="15ae2-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15ae2-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15ae2-119">Requirements</span></span>  
 <span data-ttu-id="15ae2-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15ae2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15ae2-121">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="15ae2-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="15ae2-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15ae2-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15ae2-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15ae2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ae2-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="15ae2-124">See also</span></span>
- [<span data-ttu-id="15ae2-125">ICorProfilerFunctionControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="15ae2-125">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
