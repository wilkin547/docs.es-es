---
title: "ICorProfilerCallback::ModuleAttachedToAssembly (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ModuleAttachedToAssembly
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2c285a42bb48970756a54d5313d2839c76a9835c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="8a148-102">ICorProfilerCallback::ModuleAttachedToAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="8a148-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="8a148-103">Notifica al generador de perfiles que se va a adjuntar un módulo a su ensamblado primario.</span><span class="sxs-lookup"><span data-stu-id="8a148-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a148-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a148-104">Syntax</span></span>  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a148-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a148-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="8a148-106">[in] El identificador del módulo que se va a adjuntar.</span><span class="sxs-lookup"><span data-stu-id="8a148-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="8a148-107">[in] El identificador del ensamblado primario al que está asociado el módulo.</span><span class="sxs-lookup"><span data-stu-id="8a148-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a148-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a148-108">Remarks</span></span>  
 <span data-ttu-id="8a148-109">Un módulo se puede cargar a través de una tabla de direcciones de importación (IAT), mediante una llamada a `LoadLibrary`, o a través de una referencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="8a148-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="8a148-110">Como resultado, el cargador de common language runtime (CLR) tiene varias rutas de acceso de código para determinar el ensamblado en el que reside un módulo.</span><span class="sxs-lookup"><span data-stu-id="8a148-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="8a148-111">Por lo tanto, es posible que, una vez [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) se llama, el módulo no sepa en qué ensamblado se encuentra en y no es posible obtener el identificador del ensamblado primario.</span><span class="sxs-lookup"><span data-stu-id="8a148-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="8a148-112">El `ModuleAttachedToAssembly` método se llama cuando el módulo está asociado a su ensamblado primario y su ensamblado primario de identificador se puede obtener.</span><span class="sxs-lookup"><span data-stu-id="8a148-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a148-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a148-113">Requirements</span></span>  
 <span data-ttu-id="8a148-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a148-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a148-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a148-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a148-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a148-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a148-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a148-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a148-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a148-118">See Also</span></span>  
 [<span data-ttu-id="8a148-119">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a148-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
