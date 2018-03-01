---
title: "ICorProfilerInfo::BeginInprocDebugging (Método)"
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
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 91306bbea7b099f7e9e408f8bf69625f1d7da68e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="b096d-102">ICorProfilerInfo::BeginInprocDebugging (Método)</span><span class="sxs-lookup"><span data-stu-id="b096d-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="b096d-103">Inicializa la compatibilidad con la depuración en proceso.</span><span class="sxs-lookup"><span data-stu-id="b096d-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="b096d-104">Este método está obsoleto en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b096d-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b096d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b096d-105">Syntax</span></span>  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b096d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b096d-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="b096d-107">[in] Establezca este valor en `true` para inicializar la compatibilidad con la depuración para el actual subproceso; establézcalo en `false` para inicializar la compatibilidad con la depuración en todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="b096d-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="b096d-108">[out] Puntero a un valor devuelto que identifica la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="b096d-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b096d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b096d-109">Remarks</span></span>  
 <span data-ttu-id="b096d-110">Los servicios de depuración de CLR admiten la depuración en proceso limitada en las versiones 1.0 y 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b096d-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="b096d-111">Un generador de perfiles usar las partes de inspección de la API de depuración habilita la depuración en curso.</span><span class="sxs-lookup"><span data-stu-id="b096d-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="b096d-112">Sin embargo, debido a los comentarios de clientes, depuración en proceso se ha quitado de la versión 2.0 de .NET Framework y reemplazan con un conjunto de funciones que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="b096d-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b096d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b096d-113">Requirements</span></span>  
 <span data-ttu-id="b096d-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b096d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b096d-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b096d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b096d-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b096d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b096d-117">**Versión de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="b096d-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b096d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b096d-118">See Also</span></span>  
 [<span data-ttu-id="b096d-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b096d-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
