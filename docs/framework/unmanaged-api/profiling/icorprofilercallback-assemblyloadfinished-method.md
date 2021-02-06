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
ms.openlocfilehash: 19c0871808455e64ad8a4eb002806a87030f7882
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648043"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="36501-103">ICorProfilerCallback::AssemblyLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="36501-103">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>

<span data-ttu-id="36501-104">Notifica al generador de perfiles que un ensamblado ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="36501-104">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36501-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36501-105">Syntax</span></span>  
  
```cpp  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36501-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36501-106">Parameters</span></span>

- `assemblyId`

  <span data-ttu-id="36501-107">\[in] identifica el ensamblado que se cargó.</span><span class="sxs-lookup"><span data-stu-id="36501-107">\[in] Identifies the assembly that was loaded.</span></span>

- `hrStatus`

  <span data-ttu-id="36501-108">\[in] un valor HRESULT que indica si el ensamblado finalizó la carga correctamente.</span><span class="sxs-lookup"><span data-stu-id="36501-108">\[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="36501-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="36501-109">Remarks</span></span>  

 <span data-ttu-id="36501-110">El valor de `assemblyId` no es válido para una solicitud de información hasta que `AssemblyLoadFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="36501-110">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="36501-111">Algunas partes de la carga del ensamblado podrían continuar después de la `AssemblyLoadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="36501-111">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="36501-112">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="36501-112">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="36501-113">Sin embargo, un valor HRESULT correcto en `hrStatus` indica solo que la primera parte de la carga del ensamblado se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="36501-113">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36501-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36501-114">Requirements</span></span>  

 <span data-ttu-id="36501-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36501-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36501-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36501-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36501-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36501-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36501-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36501-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36501-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="36501-119">See also</span></span>

- [<span data-ttu-id="36501-120">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="36501-120">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
