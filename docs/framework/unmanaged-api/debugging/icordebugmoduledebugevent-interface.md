---
description: 'Más información acerca de: interfaz ICorDebugModuleDebugEvent'
title: Interfaz ICorDebugModuleDebugEvent
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: 0c2d43d7b04caeea0407ede23f0df6e278d60c92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801038"
---
# <a name="icordebugmoduledebugevent-interface"></a><span data-ttu-id="1e24c-103">Interfaz ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="1e24c-103">ICorDebugModuleDebugEvent Interface</span></span>

<span data-ttu-id="1e24c-104">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de nivel de módulo.</span><span class="sxs-lookup"><span data-stu-id="1e24c-104">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e24c-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1e24c-105">Methods</span></span>  
  
|<span data-ttu-id="1e24c-106">Método</span><span class="sxs-lookup"><span data-stu-id="1e24c-106">Method</span></span>|<span data-ttu-id="1e24c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e24c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e24c-108">GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="1e24c-108">GetModule Method</span></span>](icordebugmoduledebugevent-getmodule-method.md)|<span data-ttu-id="1e24c-109">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="1e24c-109">Gets the merged module that was just loaded or unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e24c-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1e24c-110">Remarks</span></span>  

 <span data-ttu-id="1e24c-111">Los tipos de evento [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) y [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) implementan esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="1e24c-111">The [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) and [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) event types implement this interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e24c-112">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1e24c-112">The interface is available with .NET Native only.</span></span> <span data-ttu-id="1e24c-113">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="1e24c-113">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e24c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e24c-114">Requirements</span></span>  

 <span data-ttu-id="1e24c-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e24c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e24c-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e24c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e24c-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e24c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e24c-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e24c-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e24c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e24c-119">See also</span></span>

- [<span data-ttu-id="1e24c-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1e24c-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1e24c-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="1e24c-121">Debugging</span></span>](index.md)
