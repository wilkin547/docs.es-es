---
title: Método ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 4d9eea8fb5c42002763a0ae52a186bf2c1e6d2ee
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792903"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="7dfb8-102">Método ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="7dfb8-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="7dfb8-103">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="7dfb8-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dfb8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7dfb8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7dfb8-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="7dfb8-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="7dfb8-106">[out] Puntero a la dirección de un objeto ICorDebugModule que representa el módulo de combinación que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="7dfb8-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dfb8-107">Notas</span><span class="sxs-lookup"><span data-stu-id="7dfb8-107">Remarks</span></span>  
 <span data-ttu-id="7dfb8-108">Puede llamar al método [GetEventKind](icordebugdebugevent-geteventkind-method.md) para determinar si el módulo se ha cargado o descargado.</span><span class="sxs-lookup"><span data-stu-id="7dfb8-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7dfb8-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7dfb8-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dfb8-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7dfb8-110">Requirements</span></span>  
 <span data-ttu-id="7dfb8-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dfb8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dfb8-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7dfb8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7dfb8-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7dfb8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7dfb8-114">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dfb8-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dfb8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dfb8-115">See also</span></span>

- [<span data-ttu-id="7dfb8-116">ICorDebugModuleDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7dfb8-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="7dfb8-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7dfb8-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
