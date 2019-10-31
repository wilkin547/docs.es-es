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
ms.openlocfilehash: b1d31012662964132f8b65f030a062ae39ded56e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130366"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="868fd-102">Interfaz ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="868fd-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="868fd-103">[Se admite en el .NET Framework 4,6 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="868fd-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="868fd-104">Una subclase de [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) que proporciona un enumerador para todos los métodos que se definen en un módulo Ngen determinado e insertan un método determinado.</span><span class="sxs-lookup"><span data-stu-id="868fd-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="868fd-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="868fd-105">Methods</span></span>  
  
|<span data-ttu-id="868fd-106">Método</span><span class="sxs-lookup"><span data-stu-id="868fd-106">Method</span></span>|<span data-ttu-id="868fd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="868fd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="868fd-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod (método)</span><span class="sxs-lookup"><span data-stu-id="868fd-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="868fd-109">Devuelve un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que están insertados en el cuerpo de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="868fd-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="868fd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="868fd-110">Requirements</span></span>  
 <span data-ttu-id="868fd-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="868fd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="868fd-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="868fd-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="868fd-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="868fd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="868fd-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="868fd-114">See also</span></span>

- [<span data-ttu-id="868fd-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="868fd-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
