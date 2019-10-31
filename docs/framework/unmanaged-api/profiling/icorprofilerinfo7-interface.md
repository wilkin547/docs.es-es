---
title: Interfaz ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 4c7e94ffa60bcfaead009e1a8baa9b54b2e8ab7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125052"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="fa9cb-102">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="fa9cb-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="fa9cb-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="fa9cb-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="fa9cb-104">Una subclase de [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) que proporciona un método para aplicar los metadatos recién definidos a un módulo y que proporciona acceso a una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="fa9cb-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa9cb-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fa9cb-105">Methods</span></span>  
  
|<span data-ttu-id="fa9cb-106">Método</span><span class="sxs-lookup"><span data-stu-id="fa9cb-106">Method</span></span>|<span data-ttu-id="fa9cb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa9cb-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa9cb-108">ApplyMetaData (método)</span><span class="sxs-lookup"><span data-stu-id="fa9cb-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="fa9cb-109">Aplica los metadatos recién definidos por los métodos `IMetadataEmit::Define*` a un módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="fa9cb-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="fa9cb-110">GetInMemorySymbolsLength (método)</span><span class="sxs-lookup"><span data-stu-id="fa9cb-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="fa9cb-111">Devuelve la longitud de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="fa9cb-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="fa9cb-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="fa9cb-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="fa9cb-113">Lee bytes de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="fa9cb-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fa9cb-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa9cb-114">Requirements</span></span>  
 <span data-ttu-id="fa9cb-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa9cb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa9cb-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fa9cb-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fa9cb-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa9cb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa9cb-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa9cb-118">See also</span></span>

- [<span data-ttu-id="fa9cb-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="fa9cb-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
