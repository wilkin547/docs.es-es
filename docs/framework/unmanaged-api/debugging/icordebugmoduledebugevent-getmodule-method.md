---
title: Método ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c0cc1305f47f03c8c9b35bab5c980cb23d1b157
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138442"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="f90a8-102">Método ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="f90a8-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="f90a8-103">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="f90a8-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f90a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f90a8-104">Syntax</span></span>  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f90a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f90a8-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="f90a8-106">[out] Un puntero a la dirección de un objeto ICorDebugModule que representa el módulo combinado que solo se carga o descarga.</span><span class="sxs-lookup"><span data-stu-id="f90a8-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f90a8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f90a8-107">Remarks</span></span>  
 <span data-ttu-id="f90a8-108">Puede llamar a la [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) método para determinar si el módulo se carga o descarga.</span><span class="sxs-lookup"><span data-stu-id="f90a8-108">You can call the [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f90a8-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f90a8-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f90a8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f90a8-110">Requirements</span></span>  
 <span data-ttu-id="f90a8-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f90a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f90a8-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f90a8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f90a8-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f90a8-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f90a8-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f90a8-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f90a8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f90a8-115">See also</span></span>

- [<span data-ttu-id="f90a8-116">Interfaz ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="f90a8-116">ICorDebugModuleDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="f90a8-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f90a8-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
