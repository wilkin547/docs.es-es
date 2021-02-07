---
description: 'Más información acerca de: interfaz ICorProfilerInfo7'
title: Interfaz ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 7a33472d5562ad57d38291c64f8da7021ae2fe91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737082"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="c3ca2-103">Interfaz ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="c3ca2-103">ICorProfilerInfo7 Interface</span></span>

<span data-ttu-id="c3ca2-104">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="c3ca2-104">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="c3ca2-105">Una subclase de [ICorProfilerInfo6](icorprofilerinfo6-interface.md) que proporciona un método para aplicar los metadatos recién definidos a un módulo y que proporciona acceso a una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-105">A subclass of [ICorProfilerInfo6](icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c3ca2-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="c3ca2-106">Methods</span></span>  
  
|<span data-ttu-id="c3ca2-107">Método</span><span class="sxs-lookup"><span data-stu-id="c3ca2-107">Method</span></span>|<span data-ttu-id="c3ca2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c3ca2-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c3ca2-109">Método ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="c3ca2-109">ApplyMetaData Method</span></span>](icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="c3ca2-110">Aplica los metadatos recién definidos por los `IMetadataEmit::Define*` métodos a un módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-110">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="c3ca2-111">Método GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="c3ca2-111">GetInMemorySymbolsLength Method</span></span>](icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="c3ca2-112">Devuelve la longitud de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-112">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="c3ca2-113">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="c3ca2-113">ReadInMemorySymbols</span></span>](icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="c3ca2-114">Lee bytes de una secuencia de símbolos en memoria.</span><span class="sxs-lookup"><span data-stu-id="c3ca2-114">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c3ca2-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3ca2-115">Requirements</span></span>  

 <span data-ttu-id="c3ca2-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3ca2-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3ca2-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c3ca2-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c3ca2-118">**.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3ca2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ca2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3ca2-119">See also</span></span>

- [<span data-ttu-id="c3ca2-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c3ca2-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
