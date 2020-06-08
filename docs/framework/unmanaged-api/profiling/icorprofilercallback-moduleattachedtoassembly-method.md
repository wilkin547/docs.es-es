---
title: ICorProfilerCallback::ModuleAttachedToAssembly (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
ms.openlocfilehash: 4f494919d11e0f979cf1964c08106fbb9b9ed20b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503398"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="03b9b-102">ICorProfilerCallback::ModuleAttachedToAssembly (Método)</span><span class="sxs-lookup"><span data-stu-id="03b9b-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="03b9b-103">Notifica al generador de perfiles que se está asociando un módulo a su ensamblado primario.</span><span class="sxs-lookup"><span data-stu-id="03b9b-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03b9b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03b9b-104">Syntax</span></span>  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03b9b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03b9b-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="03b9b-106">de IDENTIFICADOR del módulo que se va a adjuntar.</span><span class="sxs-lookup"><span data-stu-id="03b9b-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="03b9b-107">de IDENTIFICADOR del ensamblado primario al que está asociado el módulo.</span><span class="sxs-lookup"><span data-stu-id="03b9b-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03b9b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03b9b-108">Remarks</span></span>  
 <span data-ttu-id="03b9b-109">Un módulo se puede cargar a través de una tabla de direcciones de importación (IAT), a través de una llamada a `LoadLibrary` o a través de una referencia de metadatos.</span><span class="sxs-lookup"><span data-stu-id="03b9b-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="03b9b-110">Como resultado, el cargador de Common Language Runtime (CLR) tiene varias rutas de acceso de código para determinar el ensamblado en el que reside un módulo.</span><span class="sxs-lookup"><span data-stu-id="03b9b-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="03b9b-111">Por lo tanto, es posible que después de llamar a [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) , el módulo no sepa en qué ensamblado se encuentra y que no sea posible obtener el identificador del ensamblado primario.</span><span class="sxs-lookup"><span data-stu-id="03b9b-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="03b9b-112">`ModuleAttachedToAssembly`Se llama al método cuando el módulo se adjunta a su ensamblado primario y se puede obtener el identificador del ensamblado primario.</span><span class="sxs-lookup"><span data-stu-id="03b9b-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03b9b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03b9b-113">Requirements</span></span>  
 <span data-ttu-id="03b9b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03b9b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03b9b-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="03b9b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="03b9b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03b9b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03b9b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03b9b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03b9b-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="03b9b-118">See also</span></span>

- [<span data-ttu-id="03b9b-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03b9b-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
