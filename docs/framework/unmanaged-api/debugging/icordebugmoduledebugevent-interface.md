---
title: Interfaz ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 706f392652c5cb868e09d4ee9fcb69c6d3d92d2a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965096"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="cda6c-102">Interfaz ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="cda6c-102">ICorDebugModuleDebugEvent Interface</span></span>
<span data-ttu-id="cda6c-103">Extiende la interfaz [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) para admitir eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="cda6c-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cda6c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="cda6c-104">Methods</span></span>  
  
|<span data-ttu-id="cda6c-105">Método</span><span class="sxs-lookup"><span data-stu-id="cda6c-105">Method</span></span>|<span data-ttu-id="cda6c-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cda6c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cda6c-107">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="cda6c-107">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="cda6c-108">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="cda6c-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cda6c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cda6c-109">Remarks</span></span>  
 <span data-ttu-id="cda6c-110">Los tipos de eventos [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) y [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="cda6c-110">The [MODULE_LOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cda6c-111">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cda6c-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="cda6c-112">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="cda6c-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cda6c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cda6c-113">Requirements</span></span>  
 <span data-ttu-id="cda6c-114">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cda6c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cda6c-115">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="cda6c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cda6c-116">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cda6c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cda6c-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cda6c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda6c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cda6c-118">See also</span></span>

- [<span data-ttu-id="cda6c-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="cda6c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="cda6c-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="cda6c-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
