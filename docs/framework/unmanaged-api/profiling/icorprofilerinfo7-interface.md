---
title: Interfaz ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: f80f310c10bae33583cb7cd2048ede4f5efbe14c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861754"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="15e7b-102">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="15e7b-102">ICorProfilerInfo7 Interface</span></span>
<span data-ttu-id="15e7b-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="15e7b-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="15e7b-104">Una subclase de [ICorProfilerInfo6](icorprofilerinfo6-interface.md) que proporciona un método para aplicar los metadatos recién definidos a un módulo y que proporciona acceso a una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="15e7b-104">A subclass of [ICorProfilerInfo6](icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="15e7b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="15e7b-105">Methods</span></span>  
  
|<span data-ttu-id="15e7b-106">Método</span><span class="sxs-lookup"><span data-stu-id="15e7b-106">Method</span></span>|<span data-ttu-id="15e7b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="15e7b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15e7b-108">ApplyMetaData (método)</span><span class="sxs-lookup"><span data-stu-id="15e7b-108">ApplyMetaData Method</span></span>](icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="15e7b-109">Aplica los metadatos recién definidos por los métodos `IMetadataEmit::Define*` a un módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="15e7b-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="15e7b-110">GetInMemorySymbolsLength (método)</span><span class="sxs-lookup"><span data-stu-id="15e7b-110">GetInMemorySymbolsLength Method</span></span>](icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="15e7b-111">Devuelve la longitud de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="15e7b-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="15e7b-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="15e7b-112">ReadInMemorySymbols</span></span>](icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="15e7b-113">Lee bytes de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="15e7b-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15e7b-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="15e7b-114">Requirements</span></span>  
 <span data-ttu-id="15e7b-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15e7b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15e7b-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="15e7b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="15e7b-117">**.NET Framework versiones:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15e7b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15e7b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="15e7b-118">See also</span></span>

- [<span data-ttu-id="15e7b-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="15e7b-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
