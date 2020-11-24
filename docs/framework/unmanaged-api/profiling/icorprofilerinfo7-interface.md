---
title: Interfaz ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 4acafafa284549fe1b078542a88c0818dcde3038
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686064"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="d5e59-102">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="d5e59-102">ICorProfilerInfo7 Interface</span></span>

<span data-ttu-id="d5e59-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="d5e59-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="d5e59-104">Una subclase de [ICorProfilerInfo6](icorprofilerinfo6-interface.md) que proporciona un método para aplicar los metadatos recién definidos a un módulo y que proporciona acceso a una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="d5e59-104">A subclass of [ICorProfilerInfo6](icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5e59-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d5e59-105">Methods</span></span>  
  
|<span data-ttu-id="d5e59-106">Método</span><span class="sxs-lookup"><span data-stu-id="d5e59-106">Method</span></span>|<span data-ttu-id="d5e59-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5e59-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5e59-108">Método ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="d5e59-108">ApplyMetaData Method</span></span>](icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="d5e59-109">Aplica los metadatos recién definidos por los `IMetadataEmit::Define*` métodos a un módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="d5e59-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="d5e59-110">Método GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="d5e59-110">GetInMemorySymbolsLength Method</span></span>](icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="d5e59-111">Devuelve la longitud de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="d5e59-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="d5e59-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="d5e59-112">ReadInMemorySymbols</span></span>](icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="d5e59-113">Lee bytes de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="d5e59-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5e59-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5e59-114">Requirements</span></span>  

 <span data-ttu-id="d5e59-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5e59-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5e59-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5e59-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5e59-117">**.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5e59-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e59-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d5e59-118">See also</span></span>

- [<span data-ttu-id="d5e59-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d5e59-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
