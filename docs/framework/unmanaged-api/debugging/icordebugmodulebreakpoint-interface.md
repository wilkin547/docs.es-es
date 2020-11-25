---
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
ms.openlocfilehash: 14f2b6822744070e649cf9a6722272992c0bf1c8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709523"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="20a28-102">Interfaz ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="20a28-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="20a28-103">Proporciona acceso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="20a28-103">Provides access to specific modules.</span></span> <span data-ttu-id="20a28-104">Esta interfaz es una subclase de la interfaz ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="20a28-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="20a28-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="20a28-105">Methods</span></span>  
  
|<span data-ttu-id="20a28-106">Método</span><span class="sxs-lookup"><span data-stu-id="20a28-106">Method</span></span>|<span data-ttu-id="20a28-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="20a28-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="20a28-108">GetModule (Método)</span><span class="sxs-lookup"><span data-stu-id="20a28-108">GetModule Method</span></span>](icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="20a28-109">Obtiene un puntero de interfaz a una ICorDebugModule que hace referencia al módulo donde se establece este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="20a28-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20a28-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20a28-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20a28-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="20a28-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20a28-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="20a28-112">Requirements</span></span>  

 <span data-ttu-id="20a28-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20a28-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20a28-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20a28-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20a28-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20a28-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20a28-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20a28-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20a28-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20a28-117">See also</span></span>

- [<span data-ttu-id="20a28-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="20a28-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
