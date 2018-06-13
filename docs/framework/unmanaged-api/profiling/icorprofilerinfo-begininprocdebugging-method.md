---
title: ICorProfilerInfo::BeginInprocDebugging (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82e798e1a31f771c63e71f2a85f8cbb684b237bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462395"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="2dd0c-102">ICorProfilerInfo::BeginInprocDebugging (Método)</span><span class="sxs-lookup"><span data-stu-id="2dd0c-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="2dd0c-103">Inicializa la compatibilidad con la depuración en proceso.</span><span class="sxs-lookup"><span data-stu-id="2dd0c-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="2dd0c-104">Este método está obsoleto en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2dd0c-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dd0c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2dd0c-105">Syntax</span></span>  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2dd0c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2dd0c-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="2dd0c-107">[in] Establezca este valor en `true` para inicializar la compatibilidad con la depuración para el actual subproceso; establézcalo en `false` para inicializar la compatibilidad con la depuración en todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="2dd0c-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="2dd0c-108">[out] Puntero a un valor devuelto que identifica la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="2dd0c-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dd0c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2dd0c-109">Remarks</span></span>  
 <span data-ttu-id="2dd0c-110">Los servicios de depuración de CLR admiten la depuración en proceso limitada en las versiones 1.0 y 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2dd0c-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="2dd0c-111">Un generador de perfiles usar las partes de inspección de la API de depuración habilita la depuración en curso.</span><span class="sxs-lookup"><span data-stu-id="2dd0c-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="2dd0c-112">Sin embargo, debido a los comentarios de clientes, depuración en proceso se ha quitado de la versión 2.0 de .NET Framework y reemplazan con un conjunto de funciones que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="2dd0c-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dd0c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2dd0c-113">Requirements</span></span>  
 <span data-ttu-id="2dd0c-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2dd0c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dd0c-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2dd0c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2dd0c-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dd0c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dd0c-117">**Versión de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="2dd0c-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd0c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2dd0c-118">See Also</span></span>  
 [<span data-ttu-id="2dd0c-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2dd0c-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
