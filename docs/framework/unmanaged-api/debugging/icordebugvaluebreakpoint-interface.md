---
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
ms.openlocfilehash: 1183f9f6d1ac221b20767f0a1bab15b3e9665a61
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396612"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="aec70-102">Interfaz ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="aec70-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="aec70-103">Extiende la interfaz ICorDebugBreakpoint para proporcionar acceso a valores específicos.</span><span class="sxs-lookup"><span data-stu-id="aec70-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="aec70-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="aec70-104">Methods</span></span>  
  
|<span data-ttu-id="aec70-105">Método</span><span class="sxs-lookup"><span data-stu-id="aec70-105">Method</span></span>|<span data-ttu-id="aec70-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="aec70-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="aec70-107">Método GetValue</span><span class="sxs-lookup"><span data-stu-id="aec70-107">GetValue Method</span></span>](icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="aec70-108">Obtiene un puntero de interfaz a un objeto ICorDebugValue que representa el valor del objeto en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="aec70-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aec70-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aec70-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aec70-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="aec70-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aec70-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aec70-111">Requirements</span></span>  
 <span data-ttu-id="aec70-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aec70-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aec70-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aec70-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aec70-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aec70-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aec70-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aec70-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec70-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="aec70-116">See also</span></span>

- [<span data-ttu-id="aec70-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="aec70-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
