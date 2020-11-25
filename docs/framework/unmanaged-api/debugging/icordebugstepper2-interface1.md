---
title: Interfaz ICorDebugStepper2
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2
helpviewer_keywords:
- ICorDebugStepper2 interface [.NET Framework debugging]
ms.assetid: 7a191c2a-95ea-4d47-83b0-44de2b632d63
topic_type:
- apiref
ms.openlocfilehash: ecbedfbca37a3630fc6d40c173f8a6cd05b4d3fb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727645"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="5a52c-102">Interfaz ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="5a52c-102">ICorDebugStepper2 Interface</span></span>

<span data-ttu-id="5a52c-103">Proporciona compatibilidad con la depuración solo mi código (JMC).</span><span class="sxs-lookup"><span data-stu-id="5a52c-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a52c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5a52c-104">Methods</span></span>  
  
|<span data-ttu-id="5a52c-105">Método</span><span class="sxs-lookup"><span data-stu-id="5a52c-105">Method</span></span>|<span data-ttu-id="5a52c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a52c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a52c-107">Método SetJMC</span><span class="sxs-lookup"><span data-stu-id="5a52c-107">SetJMC Method</span></span>](icordebugstepper2-setjmc-method.md)|<span data-ttu-id="5a52c-108">Establece un valor que especifica si esta ICorDebugStepper solo se realiza a través del código creado por el desarrollador de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="5a52c-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a52c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a52c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a52c-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5a52c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a52c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a52c-111">Requirements</span></span>  

 <span data-ttu-id="5a52c-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a52c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a52c-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a52c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a52c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a52c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a52c-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a52c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a52c-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5a52c-116">See also</span></span>

- [<span data-ttu-id="5a52c-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5a52c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
