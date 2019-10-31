---
title: ICorDebugModuleBreakpoint (Interfaz)
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
ms.openlocfilehash: 2bc5c21d2e1256d0e79390bea10aafcdefbed0d3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110337"
---
# <a name="icordebugmodulebreakpoint-interface"></a><span data-ttu-id="31dbf-102">ICorDebugModuleBreakpoint (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="31dbf-102">ICorDebugModuleBreakpoint Interface</span></span>

<span data-ttu-id="31dbf-103">Proporciona acceso a módulos específicos.</span><span class="sxs-lookup"><span data-stu-id="31dbf-103">Provides access to specific modules.</span></span> <span data-ttu-id="31dbf-104">Esta interfaz es una subclase de la interfaz ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="31dbf-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="31dbf-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="31dbf-105">Methods</span></span>  
  
|<span data-ttu-id="31dbf-106">Método</span><span class="sxs-lookup"><span data-stu-id="31dbf-106">Method</span></span>|<span data-ttu-id="31dbf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="31dbf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="31dbf-108">GetModule (método)</span><span class="sxs-lookup"><span data-stu-id="31dbf-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="31dbf-109">Obtiene un puntero de interfaz a una ICorDebugModule que hace referencia al módulo donde se establece este punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="31dbf-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31dbf-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="31dbf-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="31dbf-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="31dbf-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31dbf-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31dbf-112">Requirements</span></span>  
 <span data-ttu-id="31dbf-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31dbf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31dbf-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31dbf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31dbf-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31dbf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31dbf-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31dbf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31dbf-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="31dbf-117">See also</span></span>

- [<span data-ttu-id="31dbf-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="31dbf-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
