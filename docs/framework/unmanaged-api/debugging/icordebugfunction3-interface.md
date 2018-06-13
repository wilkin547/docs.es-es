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
ms.openlocfilehash: c1945e678dd62f81c698807714d0e71053d6b378
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414790"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="dc6c6-102">ICorDebugFunction3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc6c6-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="dc6c6-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="dc6c6-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="dc6c6-104">Extiende lógicamente la ICorDebugFunction (interfaz) para proporcionar acceso al código desde una solicitud ReJIT.</span><span class="sxs-lookup"><span data-stu-id="dc6c6-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dc6c6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="dc6c6-105">Methods</span></span>  
  
|<span data-ttu-id="dc6c6-106">Método</span><span class="sxs-lookup"><span data-stu-id="dc6c6-106">Method</span></span>|<span data-ttu-id="dc6c6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc6c6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dc6c6-108">GetActiveReJitRequestILCode (método)</span><span class="sxs-lookup"><span data-stu-id="dc6c6-108">GetActiveReJitRequestILCode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="dc6c6-109">Obtiene un puntero de interfaz a una [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) que contiene el IL de una solicitud ReJIT activa.</span><span class="sxs-lookup"><span data-stu-id="dc6c6-109">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc6c6-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc6c6-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc6c6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc6c6-111">Requirements</span></span>  
 <span data-ttu-id="dc6c6-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc6c6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc6c6-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc6c6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc6c6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc6c6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc6c6-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc6c6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6c6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc6c6-116">See Also</span></span>  
 [<span data-ttu-id="dc6c6-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="dc6c6-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="dc6c6-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="dc6c6-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)  
 [<span data-ttu-id="dc6c6-119">ReJIT: Una guía de procedimientos</span><span class="sxs-lookup"><span data-stu-id="dc6c6-119">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
