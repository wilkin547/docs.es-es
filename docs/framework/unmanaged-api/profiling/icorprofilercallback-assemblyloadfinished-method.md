---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7f000b6e944be7bd2e38f97e40176952cb19605
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450637"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="3d2f6-102">ICorProfilerCallback::AssemblyLoadFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="3d2f6-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="3d2f6-103">Notifica al generador de perfiles que un ensamblado ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="3d2f6-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d2f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d2f6-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d2f6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d2f6-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="3d2f6-106">[in] Identifica el ensamblado que se cargó.</span><span class="sxs-lookup"><span data-stu-id="3d2f6-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="3d2f6-107">[in] Un valor HRESULT que indica si el ensamblado terminó de cargarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="3d2f6-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d2f6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d2f6-108">Remarks</span></span>  
 <span data-ttu-id="3d2f6-109">El valor de `assemblyId` no es válido para una solicitud de información hasta que el `AssemblyLoadFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="3d2f6-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="3d2f6-110">Algunas partes de la carga del ensamblado podrían continuar después de la `AssemblyLoadFinished` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3d2f6-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="3d2f6-111">Un valor HRESULT de error en `hrStatus` indica un error.</span><span class="sxs-lookup"><span data-stu-id="3d2f6-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="3d2f6-112">Sin embargo, un valor HRESULT correcto en `hrStatus` sólo indica que la primera parte de cargar el ensamblado se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="3d2f6-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d2f6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d2f6-113">Requirements</span></span>  
 <span data-ttu-id="3d2f6-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d2f6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d2f6-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d2f6-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d2f6-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d2f6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d2f6-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d2f6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d2f6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d2f6-118">See Also</span></span>  
 [<span data-ttu-id="3d2f6-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d2f6-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
