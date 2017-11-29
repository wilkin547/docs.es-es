---
title: "ICorProfilerInfo::EndInprocDebugging (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.EndInprocDebugging
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6e87cf210fb2717379e6bdc0b687028d680fe624
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="6d366-102">ICorProfilerInfo::EndInprocDebugging (Método)</span><span class="sxs-lookup"><span data-stu-id="6d366-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="6d366-103">Se cierra una sesión de depuración en curso.</span><span class="sxs-lookup"><span data-stu-id="6d366-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="6d366-104">Este método está obsoleto en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d366-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d366-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d366-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d366-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6d366-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="6d366-107">[in] Un valor que identifica la sesión de depuración.</span><span class="sxs-lookup"><span data-stu-id="6d366-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="6d366-108">Este valor debe ser el mismo que recibió en el [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="6d366-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d366-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d366-109">Remarks</span></span>  
 <span data-ttu-id="6d366-110">Debe llamar a [ICorProfilerInfo:: BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) y `EndInprocDebugging` en el mismo método de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="6d366-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="6d366-111">Los servicios de depuración de CLR admiten la depuración en proceso limitada en las versiones 1.0 y 1.1 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6d366-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="6d366-112">Un generador de perfiles usar las partes de inspección de la API de depuración habilita la depuración en curso.</span><span class="sxs-lookup"><span data-stu-id="6d366-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="6d366-113">Sin embargo, debido a los comentarios de clientes, depuración en proceso se ha quitado de la versión 2.0 de .NET Framework y reemplazan con un conjunto de funciones que está más en línea con la API de generación de perfiles.</span><span class="sxs-lookup"><span data-stu-id="6d366-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d366-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6d366-114">Requirements</span></span>  
 <span data-ttu-id="6d366-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d366-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d366-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d366-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d366-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d366-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d366-118">**Versión de .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="6d366-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d366-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d366-119">See Also</span></span>  
 [<span data-ttu-id="6d366-120">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6d366-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
