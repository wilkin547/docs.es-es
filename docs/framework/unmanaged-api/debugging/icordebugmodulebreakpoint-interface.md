---
description: 'Más información acerca de: interfaz ICorDebugModuleBreakpoint ('
title: Interfaz ICorDebugModuleBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint
helpviewer_keywords:
- ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type:
- apiref
ms.openlocfilehash: c864850400471c9a3580de9bb94262c62656edf0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790755"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="f5512-103">Interfaz ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="f5512-103">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="f5512-104">Proporciona acceso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="f5512-104">Provides access to specific modules.</span></span> <span data-ttu-id="f5512-105">Esta interfaz es una subclase de la interfaz ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="f5512-105">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f5512-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="f5512-106">Methods</span></span>  
  
|<span data-ttu-id="f5512-107">Método</span><span class="sxs-lookup"><span data-stu-id="f5512-107">Method</span></span>|<span data-ttu-id="f5512-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f5512-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f5512-109">GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="f5512-109">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="f5512-110">Obtiene un puntero de interfaz a una ICorDebugModule que hace referencia al módulo donde se establece este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="f5512-110">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5512-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f5512-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5512-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f5512-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5512-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5512-113">Requirements</span></span>  

 <span data-ttu-id="f5512-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5512-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5512-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5512-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5512-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5512-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5512-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5512-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5512-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5512-118">See also</span></span>

- [<span data-ttu-id="f5512-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f5512-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
