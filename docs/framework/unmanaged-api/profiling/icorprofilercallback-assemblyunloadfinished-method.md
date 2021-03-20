---
description: 'Más información sobre: ICorProfilerCallback:: Assemblyunloadfinished ((método)'
title: ICorProfilerCallback::AssemblyUnloadFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
ms.openlocfilehash: c3c87644602ede3b849d13624b0cc0a2df71e2fd
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760676"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a><span data-ttu-id="3069e-103">ICorProfilerCallback::AssemblyUnloadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="3069e-103">ICorProfilerCallback::AssemblyUnloadFinished Method</span></span>

<span data-ttu-id="3069e-104">Notifica al generador de perfiles que se ha descargado un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3069e-104">Notifies the profiler that an assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3069e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3069e-105">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3069e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3069e-106">Parameters</span></span>

<span data-ttu-id="3069e-107">`assemblyId` de Identifica el ensamblado que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="3069e-107">`assemblyId` [in] Identifies the assembly that is being unloaded.</span></span>

<span data-ttu-id="3069e-108">`hrStatus` de HRESULT que indica si el ensamblado se ha descargado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3069e-108">`hrStatus` [in] An HRESULT that indicates whether the assembly was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="3069e-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3069e-109">Remarks</span></span>  

 <span data-ttu-id="3069e-110">El valor de `assemblyId` no es válido para una solicitud de información después de que el método [ICorProfilerCallback:: assemblyunloadstarted (](icorprofilercallback-assemblyunloadstarted-method.md) devuelva.</span><span class="sxs-lookup"><span data-stu-id="3069e-110">The value of `assemblyId` is not valid for an information request after the [ICorProfilerCallback::AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="3069e-111">Algunas partes de la descarga del ensamblado podrían continuar después de la `AssemblyUnloadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3069e-111">Some parts of unloading the assembly might continue after the `AssemblyUnloadFinished` callback.</span></span> <span data-ttu-id="3069e-112">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="3069e-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="3069e-113">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la descarga del ensamblado se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3069e-113">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3069e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3069e-114">Requirements</span></span>  

 <span data-ttu-id="3069e-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3069e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3069e-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3069e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3069e-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3069e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3069e-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3069e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3069e-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3069e-119">See also</span></span>

- [<span data-ttu-id="3069e-120">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3069e-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
