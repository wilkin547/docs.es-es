---
description: 'Más información acerca de: ICorDebugStepper::D método eactivate'
title: ICorDebugStepper::Deactivate (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 039c52f5bc237506dcc648ace70789c8eb7ef8c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794668"
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="e64c6-103">ICorDebugStepper::Deactivate (Método)</span><span class="sxs-lookup"><span data-stu-id="e64c6-103">ICorDebugStepper::Deactivate Method</span></span>

<span data-ttu-id="e64c6-104">Hace que este ICorDebugStepper cancele el último comando de paso que recibió.</span><span class="sxs-lookup"><span data-stu-id="e64c6-104">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e64c6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e64c6-105">Syntax</span></span>  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e64c6-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e64c6-106">Remarks</span></span>  

 <span data-ttu-id="e64c6-107">Es posible que se emita un nuevo comando de paso A paso después de que se haya cancelado el comando de paso recibido más recientemente.</span><span class="sxs-lookup"><span data-stu-id="e64c6-107">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e64c6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e64c6-108">Requirements</span></span>  

 <span data-ttu-id="e64c6-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e64c6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e64c6-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e64c6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e64c6-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e64c6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e64c6-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e64c6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
