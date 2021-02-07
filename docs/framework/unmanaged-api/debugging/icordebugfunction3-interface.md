---
description: 'Más información acerca de: interfaz Icordebugfunction3 ('
title: ICorDebugFunction3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: f6f3ce78fbb0ca7efb6ba6a95da20f8c698b923c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692074"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="00008-103">ICorDebugFunction3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="00008-103">ICorDebugFunction3 Interface</span></span>

<span data-ttu-id="00008-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="00008-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="00008-105">Extiende la interfaz ICorDebugFunction de manera lógica para proporcionar acceso al código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="00008-105">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="00008-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="00008-106">Methods</span></span>  
  
|<span data-ttu-id="00008-107">Método</span><span class="sxs-lookup"><span data-stu-id="00008-107">Method</span></span>|<span data-ttu-id="00008-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="00008-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="00008-109">GetActiveReJitRequestILCode (método)</span><span class="sxs-lookup"><span data-stu-id="00008-109">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="00008-110">Obtiene un puntero de interfaz a un [ICorDebugILCode](icordebugilcode-interface.md) que contiene el Il de una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="00008-110">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00008-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="00008-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00008-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00008-112">Requirements</span></span>  

 <span data-ttu-id="00008-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00008-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00008-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00008-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00008-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00008-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00008-116">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00008-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00008-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="00008-117">See also</span></span>

- [<span data-ttu-id="00008-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="00008-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="00008-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="00008-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="00008-120">ReJIT: Guía de How-To</span><span class="sxs-lookup"><span data-stu-id="00008-120">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
