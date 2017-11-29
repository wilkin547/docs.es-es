---
title: Interfaz ICorProfilerInfo7
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a85bf82a01f431e42a5714eeb54e17a34314534
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="bcf23-102">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="bcf23-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="bcf23-103">[compatible con la versión [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] y posteriores]</span><span class="sxs-lookup"><span data-stu-id="bcf23-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="bcf23-104">Una subclase de [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) que proporciona un método para aplicar recién definido los metadatos para un módulo y que proporciona acceso a una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="bcf23-104">A subclass of [ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bcf23-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="bcf23-105">Methods</span></span>  
  
|<span data-ttu-id="bcf23-106">Método</span><span class="sxs-lookup"><span data-stu-id="bcf23-106">Method</span></span>|<span data-ttu-id="bcf23-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bcf23-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bcf23-108">ApplyMetaData (método)</span><span class="sxs-lookup"><span data-stu-id="bcf23-108">ApplyMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="bcf23-109">Se aplica a los metadatos recién definidos por el `IMetadataEmit::Define*` métodos a un módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="bcf23-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="bcf23-110">GetInMemorySymbolsLength (método)</span><span class="sxs-lookup"><span data-stu-id="bcf23-110">GetInMemorySymbolsLength Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="bcf23-111">Devuelve la longitud de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="bcf23-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="bcf23-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="bcf23-112">ReadInMemorySymbols</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="bcf23-113">Lee los bytes de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="bcf23-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bcf23-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bcf23-114">Requirements</span></span>  
 <span data-ttu-id="bcf23-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcf23-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcf23-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bcf23-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bcf23-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bcf23-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcf23-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcf23-118">See Also</span></span>  
 [<span data-ttu-id="bcf23-119">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bcf23-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
