---
title: "ICorProfilerFunctionControl::SetILFunctionBody (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetILFunctionBody
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9469435186a5aef130ca4ebef27a4613afeb921c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="3e8f9-102">ICorProfilerFunctionControl::SetILFunctionBody (Método)</span><span class="sxs-lookup"><span data-stu-id="3e8f9-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="3e8f9-103">Reemplaza el cuerpo del Lenguaje intermedio común (CIL) del método.</span><span class="sxs-lookup"><span data-stu-id="3e8f9-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e8f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e8f9-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e8f9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e8f9-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="3e8f9-106">[in] El tamaño total del nuevo CIL, incluido el encabezado y cualquier estructura que venga después del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="3e8f9-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="3e8f9-107">[in] Puntero al nuevo encabezado de CIL.</span><span class="sxs-lookup"><span data-stu-id="3e8f9-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e8f9-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3e8f9-108">Return Value</span></span>  
 <span data-ttu-id="3e8f9-109">Este método devuelve los siguientes HRESULT concretos.</span><span class="sxs-lookup"><span data-stu-id="3e8f9-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="3e8f9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e8f9-110">HRESULT</span></span>|<span data-ttu-id="3e8f9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e8f9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e8f9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e8f9-112">S_OK</span></span>|<span data-ttu-id="3e8f9-113">El reemplazo se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3e8f9-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e8f9-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e8f9-114">Remarks</span></span>  
 <span data-ttu-id="3e8f9-115">A diferencia de la [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) método, el `SetILFunctionBody` método administra la memoria necesaria para el nuevo cuerpo CIL.</span><span class="sxs-lookup"><span data-stu-id="3e8f9-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="3e8f9-116">Esto significa que el cuerpo CIL proporcionado por el generador de perfiles no tiene que asignar mediante la [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interfaz o dentro de un intervalo determinado.</span><span class="sxs-lookup"><span data-stu-id="3e8f9-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="3e8f9-117">sino que se puede asignar en cualquier montón.</span><span class="sxs-lookup"><span data-stu-id="3e8f9-117">It can be allocated on any heap.</span></span> <span data-ttu-id="3e8f9-118">El generador de perfiles puede liberar la memoria utilizada para el cuerpo CIL después `SetILFunctionBody` devuelve.</span><span class="sxs-lookup"><span data-stu-id="3e8f9-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e8f9-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e8f9-119">Requirements</span></span>  
 <span data-ttu-id="3e8f9-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e8f9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e8f9-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3e8f9-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3e8f9-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e8f9-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e8f9-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e8f9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e8f9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e8f9-124">See Also</span></span>  
 [<span data-ttu-id="3e8f9-125">ICorProfilerFunctionControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e8f9-125">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
