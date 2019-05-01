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
ms.openlocfilehash: 24b7af4b44d51da06e9d65104f1b469ef1d83b8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992074"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="f6e87-102">ICorProfilerInfo::GetInprocInspectionIThisThread (Método)</span><span class="sxs-lookup"><span data-stu-id="f6e87-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="f6e87-103">Obtiene un objeto que se puede consultar para ICorDebugThread (interfaz).</span><span class="sxs-lookup"><span data-stu-id="f6e87-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="f6e87-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="f6e87-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6e87-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f6e87-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6e87-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f6e87-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="f6e87-107">[out](/cpp/atl/iunknown) objeto que se puede consultar el `ICorDebugThread` interfaz.</span><span class="sxs-lookup"><span data-stu-id="f6e87-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6e87-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6e87-108">Remarks</span></span>  
 <span data-ttu-id="f6e87-109">Servicios de depuración de common language runtime (CLR) admite la depuración en proceso de forma limitada en la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f6e87-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="f6e87-110">Depuración en proceso habilitado un generador de perfiles usar las partes de inspección de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="f6e87-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="f6e87-111">Como resultado de comentarios del cliente, la depuración en proceso tiene se ha quitado de la versión 2.0 de .NET Framework y reemplaza con un conjunto de funciones que está más en consonancia con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="f6e87-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6e87-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6e87-112">Requirements</span></span>  
 <span data-ttu-id="f6e87-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6e87-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6e87-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f6e87-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f6e87-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6e87-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6e87-116">**Versión de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="f6e87-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6e87-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6e87-117">See also</span></span>

- [<span data-ttu-id="f6e87-118">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f6e87-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
