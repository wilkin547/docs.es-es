---
title: ICorProfilerInfo::EndInprocDebugging (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cbf7e2e7de54b065f25f3a1873d760ab5051cc91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452616"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="d051a-102">ICorProfilerInfo::EndInprocDebugging (Método)</span><span class="sxs-lookup"><span data-stu-id="d051a-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="d051a-103">Se cierra una sesión de depuración en curso.</span><span class="sxs-lookup"><span data-stu-id="d051a-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="d051a-104">Este método está obsoleto en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d051a-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d051a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d051a-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d051a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d051a-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="d051a-107">[in] Un valor que identifica la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="d051a-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="d051a-108">Este valor debe ser el mismo que recibió en el [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="d051a-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d051a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d051a-109">Remarks</span></span>  
 <span data-ttu-id="d051a-110">Debe llamar a [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) y `EndInprocDebugging` en el mismo método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="d051a-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="d051a-111">Los servicios de depuración de CLR admiten la depuración en proceso limitada en las versiones 1.0 y 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d051a-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="d051a-112">Un generador de perfiles usar las partes de inspección de la API de depuración habilita la depuración en curso.</span><span class="sxs-lookup"><span data-stu-id="d051a-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="d051a-113">Sin embargo, debido a los comentarios de clientes, depuración en proceso se ha quitado de la versión 2.0 de .NET Framework y reemplazan con un conjunto de funciones que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="d051a-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d051a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d051a-114">Requirements</span></span>  
 <span data-ttu-id="d051a-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d051a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d051a-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d051a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d051a-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d051a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d051a-118">**Versión de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="d051a-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d051a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d051a-119">See Also</span></span>  
 [<span data-ttu-id="d051a-120">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d051a-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
