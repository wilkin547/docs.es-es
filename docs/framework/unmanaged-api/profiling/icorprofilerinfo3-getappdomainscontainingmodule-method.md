---
title: "ICorProfilerInfo3::GetAppDomainsContainingModule (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ff9f63fc004d7249b571d980561171464e74b9a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a><span data-ttu-id="f0fc3-102">ICorProfilerInfo3::GetAppDomainsContainingModule (Método)</span><span class="sxs-lookup"><span data-stu-id="f0fc3-102">ICorProfilerInfo3::GetAppDomainsContainingModule Method</span></span>
<span data-ttu-id="f0fc3-103">Obtiene los identificadores de los dominios de aplicación en los que se cargó el módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="f0fc3-103">Gets the identifiers of the application domains in which the given module has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0fc3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0fc3-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0fc3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f0fc3-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="f0fc3-106">[in] Identificador del módulo cargado.</span><span class="sxs-lookup"><span data-stu-id="f0fc3-106">[in] The ID of the loaded module.</span></span>  
  
 `cAppDomainIds`  
 <span data-ttu-id="f0fc3-107">[in] Tamaño de la matriz `appDomainIds`.</span><span class="sxs-lookup"><span data-stu-id="f0fc3-107">[in] The size of the `appDomainIds` array.</span></span>  
  
 `pcAppDomainIds`  
 <span data-ttu-id="f0fc3-108">[out] Puntero al número total de elementos devueltos.</span><span class="sxs-lookup"><span data-stu-id="f0fc3-108">[out] A pointer to the total number of returned elements.</span></span>  
  
 `appDomainIds`  
 <span data-ttu-id="f0fc3-109">[out] Matriz de valores de identificador de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="f0fc3-109">[out] An array of application domain ID values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0fc3-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f0fc3-110">Remarks</span></span>  
 <span data-ttu-id="f0fc3-111">El método usa búferes asignados al llamador.</span><span class="sxs-lookup"><span data-stu-id="f0fc3-111">The method uses caller allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0fc3-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0fc3-112">Requirements</span></span>  
 <span data-ttu-id="f0fc3-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0fc3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0fc3-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0fc3-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f0fc3-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0fc3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0fc3-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0fc3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0fc3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0fc3-117">See Also</span></span>  
 [<span data-ttu-id="f0fc3-118">ICorProfilerFunctionEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f0fc3-118">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [<span data-ttu-id="f0fc3-119">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f0fc3-119">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="f0fc3-120">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f0fc3-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="f0fc3-121">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f0fc3-121">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
