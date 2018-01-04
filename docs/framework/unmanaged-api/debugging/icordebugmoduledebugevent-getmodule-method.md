---
title: "Método ICorDebugModuleDebugEvent::GetModule"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b11ab8991a9f44cf2868474a8a0f6dcc1c3308c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="7b326-102">Método ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="7b326-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="7b326-103">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="7b326-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b326-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b326-104">Syntax</span></span>  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b326-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b326-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="7b326-106">[out] Un puntero a la dirección de un objeto ICorDebugModule que representa el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="7b326-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b326-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b326-107">Remarks</span></span>  
 <span data-ttu-id="7b326-108">Puede llamar a la [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) método para determinar si se ha cargado o sin cargar el módulo.</span><span class="sxs-lookup"><span data-stu-id="7b326-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7b326-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7b326-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b326-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b326-110">Requirements</span></span>  
 <span data-ttu-id="7b326-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b326-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b326-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b326-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b326-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b326-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b326-114">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b326-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b326-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b326-115">See Also</span></span>  
 [<span data-ttu-id="7b326-116">ICorDebugModuleDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b326-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 [<span data-ttu-id="7b326-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7b326-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
