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
ms.openlocfilehash: 1bcf52a3745b22df58e67e892bf3a2b77c542d43
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479012"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="bd387-102">ICorProfilerInfo::GetInprocInspectionIThisThread (Método)</span><span class="sxs-lookup"><span data-stu-id="bd387-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="bd387-103">Obtiene un objeto que se puede consultar para ICorDebugThread (interfaz).</span><span class="sxs-lookup"><span data-stu-id="bd387-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="bd387-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="bd387-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd387-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd387-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd387-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd387-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="bd387-107">[out](/cpp/atl/iunknown) objeto que se puede consultar el `ICorDebugThread` interfaz.</span><span class="sxs-lookup"><span data-stu-id="bd387-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd387-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd387-108">Remarks</span></span>  
 <span data-ttu-id="bd387-109">Servicios de depuración de common language runtime (CLR) admite la depuración en proceso de forma limitada en la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bd387-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="bd387-110">Depuración en proceso habilitado un generador de perfiles usar las partes de inspección de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="bd387-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="bd387-111">Como resultado de comentarios del cliente, la depuración en proceso tiene se ha quitado de la versión 2.0 de .NET Framework y reemplaza con un conjunto de funciones que está más en consonancia con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="bd387-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd387-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd387-112">Requirements</span></span>  
 <span data-ttu-id="bd387-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd387-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd387-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd387-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd387-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd387-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd387-116">**Versión de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="bd387-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd387-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd387-117">See also</span></span>
- [<span data-ttu-id="bd387-118">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd387-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
