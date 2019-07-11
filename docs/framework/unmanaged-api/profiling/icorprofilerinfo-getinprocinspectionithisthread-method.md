---
title: ICorProfilerInfo::GetInprocInspectionIThisThread (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e0f56dd6ece32b1f05418ea288da409af5cad5f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782761"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="0e222-102">ICorProfilerInfo::GetInprocInspectionIThisThread (Método)</span><span class="sxs-lookup"><span data-stu-id="0e222-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="0e222-103">Obtiene un objeto que se puede consultar para ICorDebugThread (interfaz).</span><span class="sxs-lookup"><span data-stu-id="0e222-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="0e222-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="0e222-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e222-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e222-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e222-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e222-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="0e222-107">[out](/cpp/atl/iunknown) objeto que se puede consultar el `ICorDebugThread` interfaz.</span><span class="sxs-lookup"><span data-stu-id="0e222-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e222-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e222-108">Remarks</span></span>  
 <span data-ttu-id="0e222-109">Servicios de depuración de common language runtime (CLR) admite la depuración en proceso de forma limitada en la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0e222-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="0e222-110">Depuración en proceso habilitado un generador de perfiles usar las partes de inspección de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="0e222-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="0e222-111">Como resultado de comentarios del cliente, la depuración en proceso tiene se ha quitado de la versión 2.0 de .NET Framework y reemplaza con un conjunto de funciones que está más en consonancia con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="0e222-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e222-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e222-112">Requirements</span></span>  
 <span data-ttu-id="0e222-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e222-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e222-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e222-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e222-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e222-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e222-116">**Versión de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="0e222-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e222-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e222-117">See also</span></span>

- [<span data-ttu-id="0e222-118">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e222-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
