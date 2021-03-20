---
description: 'Más información sobre: ICorProfilerCallback:: AssemblyLoadFinished ((método)'
title: ICorProfilerCallback::AssemblyLoadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
ms.openlocfilehash: accddef08f3cb76ef2cb1b70993aee24cf83ae50
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760678"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="37622-103">ICorProfilerCallback::AssemblyLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="37622-103">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>

<span data-ttu-id="37622-104">Notifica al generador de perfiles que un ensamblado ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="37622-104">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37622-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37622-105">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37622-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="37622-106">Parameters</span></span>

<span data-ttu-id="37622-107">`assemblyId` de Identifica el ensamblado que se cargó.</span><span class="sxs-lookup"><span data-stu-id="37622-107">`assemblyId` [in] Identifies the assembly that was loaded.</span></span>

<span data-ttu-id="37622-108">`hrStatus` de HRESULT que indica si el ensamblado finalizó la carga correctamente.</span><span class="sxs-lookup"><span data-stu-id="37622-108">`hrStatus` [in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="37622-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="37622-109">Remarks</span></span>  

 <span data-ttu-id="37622-110">El valor de `assemblyId` no es válido para una solicitud de información hasta que `AssemblyLoadFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="37622-110">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="37622-111">Algunas partes de la carga del ensamblado podrían continuar después de la `AssemblyLoadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="37622-111">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="37622-112">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="37622-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="37622-113">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la carga del ensamblado se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="37622-113">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37622-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37622-114">Requirements</span></span>  

 <span data-ttu-id="37622-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37622-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37622-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="37622-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="37622-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37622-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37622-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37622-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37622-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37622-119">See also</span></span>

- [<span data-ttu-id="37622-120">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37622-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
