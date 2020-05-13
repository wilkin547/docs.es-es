---
title: Método ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 1df71ddbf1ee76cc8202d8f9e263b9d95b4aaa09
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213366"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="31126-102">Método ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="31126-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="31126-103">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="31126-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31126-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31126-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31126-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="31126-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="31126-106">[out] Puntero a la dirección de un objeto ICorDebugModule que representa el módulo de combinación que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="31126-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31126-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="31126-107">Remarks</span></span>  
 <span data-ttu-id="31126-108">Puede llamar al método [GetEventKind](icordebugdebugevent-geteventkind-method.md) para determinar si el módulo se ha cargado o descargado.</span><span class="sxs-lookup"><span data-stu-id="31126-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="31126-109">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="31126-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31126-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31126-110">Requirements</span></span>  
 <span data-ttu-id="31126-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31126-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31126-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31126-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31126-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31126-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31126-114">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31126-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31126-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="31126-115">See also</span></span>

- [<span data-ttu-id="31126-116">Interfaz ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="31126-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="31126-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="31126-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
