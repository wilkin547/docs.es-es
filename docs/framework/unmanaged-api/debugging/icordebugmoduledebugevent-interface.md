---
title: Interfaz ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: 62d419a193cff000e1dd748d0cbb6b61775a81aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695821"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="db498-102">Interfaz ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="db498-102">ICorDebugModuleDebugEvent Interface</span></span>

<span data-ttu-id="db498-103">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="db498-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db498-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="db498-104">Methods</span></span>  
  
|<span data-ttu-id="db498-105">Método</span><span class="sxs-lookup"><span data-stu-id="db498-105">Method</span></span>|<span data-ttu-id="db498-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="db498-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db498-107">GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="db498-107">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="db498-108">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="db498-108">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db498-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db498-109">Remarks</span></span>  

 <span data-ttu-id="db498-110">Los tipos de evento [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) y [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="db498-110">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db498-111">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="db498-111">The interface is available with .NET Native only.</span></span> <span data-ttu-id="db498-112">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="db498-112">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db498-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db498-113">Requirements</span></span>  

 <span data-ttu-id="db498-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db498-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db498-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db498-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db498-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db498-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db498-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db498-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db498-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db498-118">See also</span></span>

- [<span data-ttu-id="db498-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="db498-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="db498-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="db498-120">Debugging</span></span>](index.md)
