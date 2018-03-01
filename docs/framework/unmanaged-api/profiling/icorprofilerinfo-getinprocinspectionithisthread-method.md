---
title: "ICorProfilerInfo::GetInprocInspectionIThisThread (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c36688af3ab8941a7004061add8598a480f3e202
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="21670-102">ICorProfilerInfo::GetInprocInspectionIThisThread (Método)</span><span class="sxs-lookup"><span data-stu-id="21670-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="21670-103">Obtiene un objeto que se pueden consultar para ICorDebugThread (interfaz).</span><span class="sxs-lookup"><span data-stu-id="21670-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="21670-104">Este método está obsoleto en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21670-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21670-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21670-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21670-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="21670-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="21670-107">[out](/cpp/atl/iunknown) objeto que se puede consultar para el `ICorDebugThread` interfaz.</span><span class="sxs-lookup"><span data-stu-id="21670-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21670-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21670-108">Remarks</span></span>  
 <span data-ttu-id="21670-109">Los servicios de depuración de common language runtime (CLR) admite la depuración en proceso de forma limitada en la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21670-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="21670-110">Un generador de perfiles usar las partes de inspección de la API de depuración habilita la depuración en curso.</span><span class="sxs-lookup"><span data-stu-id="21670-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="21670-111">Como resultado de los comentarios de clientes, la depuración en proceso tiene ha quitado de la versión 2.0 de .NET Framework y reemplaza con un conjunto de funciones que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="21670-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21670-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21670-112">Requirements</span></span>  
 <span data-ttu-id="21670-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21670-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21670-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21670-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21670-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21670-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21670-116">**Versión de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="21670-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21670-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="21670-117">See Also</span></span>  
 [<span data-ttu-id="21670-118">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="21670-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
