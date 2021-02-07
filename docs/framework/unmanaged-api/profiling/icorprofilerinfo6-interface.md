---
description: 'Más información acerca de: interfaz ICorProfilerInfo6'
title: Interfaz ICorProfilerInfo6
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
ms.openlocfilehash: c093930b102ca99a8524e6d5d6129690f80a5353
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737160"
---
# <a name="icorprofilerinfo6-interface"></a><span data-ttu-id="e5441-103">Interfaz ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="e5441-103">ICorProfilerInfo6 Interface</span></span>

<span data-ttu-id="e5441-104">[Se admite en el .NET Framework 4,6 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="e5441-104">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="e5441-105">Una subclase de [ICorProfilerInfo5](icorprofilerinfo5-interface.md) que proporciona un enumerador para todos los métodos que se definen en un módulo Ngen determinado e insertan un método determinado.</span><span class="sxs-lookup"><span data-stu-id="e5441-105">A subclass of [ICorProfilerInfo5](icorprofilerinfo5-interface.md) that provides an enumerator for all methods that are defined in a given NGen module and inline a given method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e5441-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="e5441-106">Methods</span></span>  
  
|<span data-ttu-id="e5441-107">Método</span><span class="sxs-lookup"><span data-stu-id="e5441-107">Method</span></span>|<span data-ttu-id="e5441-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5441-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5441-109">Método ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="e5441-109">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>](icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|<span data-ttu-id="e5441-110">Devuelve un enumerador para todos los métodos que pertenecen a un módulo NGen determinado y que están insertados en el cuerpo de un método determinado.</span><span class="sxs-lookup"><span data-stu-id="e5441-110">Returns an enumerator for all methods that belong to a given NGen module and that are inlined in the body of a given method.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5441-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e5441-111">Requirements</span></span>  

 <span data-ttu-id="e5441-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5441-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5441-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e5441-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e5441-114">**.NET Framework versiones:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5441-114">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5441-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5441-115">See also</span></span>

- [<span data-ttu-id="e5441-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e5441-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
