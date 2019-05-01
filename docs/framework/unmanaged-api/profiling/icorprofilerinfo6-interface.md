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
ms.openlocfilehash: febe130b4d61b6179aeab3bfcd63891c38b13fbe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041124"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="b8984-102">Interfaz ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="b8984-102">ICorProfilerInfo6 Interface</span></span>
<span data-ttu-id="b8984-103">[Compatible con .NET Framework 4.6 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="b8984-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="b8984-104">Una subclase de [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) que proporciona un enumerador para todos los métodos que se definen en un determinado módulo NGen y en línea un método determinado.</span><span class="sxs-lookup"><span data-stu-id="b8984-104">A subclass of [ICorProfilerInfo5](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8984-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b8984-105">Methods</span></span>  
  
|<span data-ttu-id="b8984-106">Método</span><span class="sxs-lookup"><span data-stu-id="b8984-106">Method</span></span>|<span data-ttu-id="b8984-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8984-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8984-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod (método)</span><span class="sxs-lookup"><span data-stu-id="b8984-108">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="b8984-109">Devuelve un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que se alinean en el cuerpo de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="b8984-109">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8984-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8984-110">Requirements</span></span>  
 <span data-ttu-id="b8984-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8984-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8984-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8984-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8984-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8984-113">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8984-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8984-114">See also</span></span>

- [<span data-ttu-id="b8984-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b8984-115">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
