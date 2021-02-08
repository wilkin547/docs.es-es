---
description: 'Más información acerca de: interfaz Icordebugvaluebreakpoint ('
title: Interfaz ICorDebugValueBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
ms.openlocfilehash: ff53b1f6e1557a3e98cc642f80eaaa2feaeac473
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790690"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="e4e91-103">Interfaz ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="e4e91-103">ICorDebugValueBreakpoint Interface</span></span>

<span data-ttu-id="e4e91-104">Extiende la interfaz ICorDebugBreakpoint para proporcionar acceso a valores específicos.</span><span class="sxs-lookup"><span data-stu-id="e4e91-104">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e4e91-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e4e91-105">Methods</span></span>  
  
|<span data-ttu-id="e4e91-106">Método</span><span class="sxs-lookup"><span data-stu-id="e4e91-106">Method</span></span>|<span data-ttu-id="e4e91-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e4e91-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4e91-108">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="e4e91-108">GetValue Method</span></span>](icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="e4e91-109">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa el valor del objeto en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="e4e91-109">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4e91-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e4e91-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4e91-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e4e91-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4e91-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e4e91-112">Requirements</span></span>  

 <span data-ttu-id="e4e91-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4e91-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4e91-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4e91-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4e91-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4e91-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4e91-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4e91-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e91-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4e91-117">See also</span></span>

- [<span data-ttu-id="e4e91-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e4e91-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
