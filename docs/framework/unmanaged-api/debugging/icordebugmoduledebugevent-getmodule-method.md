---
description: 'Más información acerca de: ICorDebugModuleDebugEvent:: GetModule (método)'
title: Método ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: c6d7171da231576ff90f54aaefe4b473af0afd40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790742"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="f8987-103">Método ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="f8987-103">ICorDebugModuleDebugEvent::GetModule Method</span></span>

<span data-ttu-id="f8987-104">Obtiene el módulo combinado que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="f8987-104">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8987-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8987-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8987-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f8987-106">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="f8987-107">[out] Puntero a la dirección de un objeto ICorDebugModule que representa el módulo de combinación que se acaba de cargar o descargar.</span><span class="sxs-lookup"><span data-stu-id="f8987-107">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8987-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f8987-108">Remarks</span></span>  

 <span data-ttu-id="f8987-109">Puede llamar al método [GetEventKind](icordebugdebugevent-geteventkind-method.md) para determinar si el módulo se ha cargado o descargado.</span><span class="sxs-lookup"><span data-stu-id="f8987-109">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8987-110">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="f8987-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8987-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8987-111">Requirements</span></span>  

 <span data-ttu-id="f8987-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8987-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8987-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8987-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8987-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8987-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8987-115">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8987-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8987-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8987-116">See also</span></span>

- [<span data-ttu-id="f8987-117">Interfaz ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="f8987-117">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="f8987-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f8987-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
