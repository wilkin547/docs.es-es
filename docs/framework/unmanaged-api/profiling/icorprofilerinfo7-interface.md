---
title: Interfaz ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d8586031c5bcb0303a64b67ee601fe41b81ee3f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134870"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="b71e4-102">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="b71e4-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="b71e4-103">[compatible con la versión [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] y posteriores]</span><span class="sxs-lookup"><span data-stu-id="b71e4-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="b71e4-104">Una subclase de [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) que proporciona un método para aplicar recién definido los metadatos para un módulo y que proporciona acceso a una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="b71e4-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b71e4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b71e4-105">Methods</span></span>  
  
|<span data-ttu-id="b71e4-106">Método</span><span class="sxs-lookup"><span data-stu-id="b71e4-106">Method</span></span>|<span data-ttu-id="b71e4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b71e4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b71e4-108">Método ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="b71e4-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="b71e4-109">Se aplica a los metadatos recién definido por el `IMetadataEmit::Define*` métodos a un módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="b71e4-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="b71e4-110">Método GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="b71e4-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="b71e4-111">Devuelve la longitud de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="b71e4-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="b71e4-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="b71e4-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="b71e4-113">Lee los bytes de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="b71e4-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b71e4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b71e4-114">Requirements</span></span>  
 <span data-ttu-id="b71e4-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b71e4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b71e4-116">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b71e4-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="b71e4-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b71e4-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b71e4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b71e4-118">See also</span></span>

- [<span data-ttu-id="b71e4-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b71e4-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
