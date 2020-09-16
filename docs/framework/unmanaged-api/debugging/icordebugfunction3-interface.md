---
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
ms.openlocfilehash: 8c9c507f00780d5ef5c5aeb28a1b10493351f37e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546977"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="59935-102">ICorDebugFunction3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="59935-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="59935-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="59935-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="59935-104">Extiende la interfaz ICorDebugFunction de manera lógica para proporcionar acceso al código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="59935-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="59935-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="59935-105">Methods</span></span>  
  
|<span data-ttu-id="59935-106">Método</span><span class="sxs-lookup"><span data-stu-id="59935-106">Method</span></span>|<span data-ttu-id="59935-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="59935-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="59935-108">GetActiveReJitRequestILCode (método)</span><span class="sxs-lookup"><span data-stu-id="59935-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="59935-109">Obtiene un puntero de interfaz a un [ICorDebugILCode](icordebugilcode-interface.md) que contiene el Il de una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="59935-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59935-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="59935-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59935-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59935-111">Requirements</span></span>  
 <span data-ttu-id="59935-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59935-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59935-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59935-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59935-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59935-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59935-115">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59935-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59935-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="59935-116">See also</span></span>

- [<span data-ttu-id="59935-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="59935-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="59935-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="59935-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="59935-119">ReJIT: Guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="59935-119">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
