---
title: Método ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: ec23cda02ff689a3365fe96fb5280054a9795caa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709510"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="53288-102">Método ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="53288-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>

<span data-ttu-id="53288-103">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="53288-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53288-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53288-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53288-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53288-105">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="53288-106">[out] Puntero a la dirección de un objeto ICorDebugModule que representa el módulo de combinación que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="53288-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53288-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53288-107">Remarks</span></span>  

 <span data-ttu-id="53288-108">Puede llamar al método [GetEventKind](icordebugdebugevent-geteventkind-method.md) para determinar si el módulo se ha cargado o descargado.</span><span class="sxs-lookup"><span data-stu-id="53288-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53288-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="53288-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53288-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53288-110">Requirements</span></span>  

 <span data-ttu-id="53288-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53288-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53288-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53288-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53288-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53288-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53288-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53288-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53288-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53288-115">See also</span></span>

- [<span data-ttu-id="53288-116">Interfaz ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="53288-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="53288-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="53288-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
