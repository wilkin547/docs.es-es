---
description: 'Más información acerca de: interfaz ICorProfilerInfo8'
title: Interface ICorProfilerInfo8
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4538c9d314283c67ab0bfe6af3f3768062cffda4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646548"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="08cc9-103">Interface ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="08cc9-103">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="08cc9-104">Una subclase de [ICorProfilerInfo7](icorprofilerinfo7-interface.md) que proporciona métodos para consultar información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="08cc9-104">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="08cc9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="08cc9-105">Methods</span></span>  

| <span data-ttu-id="08cc9-106">Método</span><span class="sxs-lookup"><span data-stu-id="08cc9-106">Method</span></span>|<span data-ttu-id="08cc9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="08cc9-107">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="08cc9-108">Método IsFunctionDynamic</span><span class="sxs-lookup"><span data-stu-id="08cc9-108">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="08cc9-109">Determina si una función no tiene metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="08cc9-109">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="08cc9-110">Método GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="08cc9-110">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="08cc9-111">Asigna un puntero de instrucción de código administrado a un FunctionID.</span><span class="sxs-lookup"><span data-stu-id="08cc9-111">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="08cc9-112">Este método funciona para los métodos dinámicos y no dinámicos.</span><span class="sxs-lookup"><span data-stu-id="08cc9-112">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="08cc9-113">Método GetDynamicFunctionInfo</span><span class="sxs-lookup"><span data-stu-id="08cc9-113">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="08cc9-114">Recupera información acerca de los métodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="08cc9-114">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="08cc9-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08cc9-115">Requirements</span></span>  

<span data-ttu-id="08cc9-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08cc9-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="08cc9-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="08cc9-117">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="08cc9-118">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="08cc9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="08cc9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="08cc9-119">See also</span></span>

- [<span data-ttu-id="08cc9-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="08cc9-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
