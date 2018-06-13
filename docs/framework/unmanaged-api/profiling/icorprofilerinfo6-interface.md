---
title: Interfaz ICorProfilerInfo6
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da1aab48e2eef229bb31e9443a5549c3f9fbc621
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455307"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="f50b6-102">Interfaz ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="f50b6-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="f50b6-103">[Compatible con .NET Framework 4.6 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="f50b6-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="f50b6-104">Una subclase de [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) que proporciona un enumerador para todos los métodos que se definen en un determinado módulo de NGen y en línea un método determinado.</span><span class="sxs-lookup"><span data-stu-id="f50b6-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f50b6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f50b6-105">Methods</span></span>  
  
|<span data-ttu-id="f50b6-106">Método</span><span class="sxs-lookup"><span data-stu-id="f50b6-106">Method</span></span>|<span data-ttu-id="f50b6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f50b6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f50b6-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod (método)</span><span class="sxs-lookup"><span data-stu-id="f50b6-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="f50b6-109">Devuelve un enumerador para todos los métodos que pertenecen a un módulo de NGen determinado y que se alinean en el cuerpo de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="f50b6-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f50b6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f50b6-110">Requirements</span></span>  
 <span data-ttu-id="f50b6-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f50b6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f50b6-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f50b6-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f50b6-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f50b6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f50b6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f50b6-114">See Also</span></span>  
 [<span data-ttu-id="f50b6-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="f50b6-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
