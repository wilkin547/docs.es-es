---
title: ICorProfilerInfo::GetInprocInspectionInterface (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 456dd8aedf11b1b27ee4926988fc615ebb7a76d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991827"
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="2db3b-102">ICorProfilerInfo::GetInprocInspectionInterface (Método)</span><span class="sxs-lookup"><span data-stu-id="2db3b-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="2db3b-103">Obtiene un objeto que puede consultarse para una interfaz "ICorDebugProcess".</span><span class="sxs-lookup"><span data-stu-id="2db3b-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="2db3b-104">Este método está obsoleto en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="2db3b-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2db3b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2db3b-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2db3b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2db3b-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="2db3b-107">[out](/cpp/atl/iunknown) objeto que se puede consultar un `ICorDebugProcess` interfaz.</span><span class="sxs-lookup"><span data-stu-id="2db3b-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2db3b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2db3b-108">Remarks</span></span>  
 <span data-ttu-id="2db3b-109">API de depuración de common language runtime (CLR) admite la depuración en proceso de forma limitada en la versión 1.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2db3b-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="2db3b-110">Depuración en proceso habilitado un generador de perfiles usar las partes de inspección de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="2db3b-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="2db3b-111">Como resultado de comentarios del cliente, la depuración en proceso tiene se ha quitado de la versión 2.0 de .NET Framework y reemplaza con un conjunto de funciones que está más en consonancia con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="2db3b-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2db3b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2db3b-112">Requirements</span></span>  
 <span data-ttu-id="2db3b-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2db3b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2db3b-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2db3b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2db3b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2db3b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2db3b-116">**Versión de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="2db3b-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db3b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2db3b-117">See also</span></span>

- [<span data-ttu-id="2db3b-118">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2db3b-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
