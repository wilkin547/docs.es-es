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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff49d64b0b58d301d24e39bc626abf6520c031b9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514225"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="37a40-102">ICorDebugFunction3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37a40-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="37a40-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="37a40-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="37a40-104">Extiende lógicamente la ICorDebugFunction (interfaz) para proporcionar acceso a código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="37a40-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37a40-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="37a40-105">Methods</span></span>  
  
|<span data-ttu-id="37a40-106">Método</span><span class="sxs-lookup"><span data-stu-id="37a40-106">Method</span></span>|<span data-ttu-id="37a40-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="37a40-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37a40-108">GetActiveReJitRequestILCode (método)</span><span class="sxs-lookup"><span data-stu-id="37a40-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="37a40-109">Obtiene un puntero de interfaz a un [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) que contiene el IL de una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="37a40-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37a40-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37a40-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37a40-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37a40-111">Requirements</span></span>  
 <span data-ttu-id="37a40-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37a40-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37a40-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="37a40-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37a40-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37a40-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37a40-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37a40-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37a40-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="37a40-116">See Also</span></span>  
 [<span data-ttu-id="37a40-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="37a40-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="37a40-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="37a40-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 [<span data-ttu-id="37a40-119">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="37a40-119">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
