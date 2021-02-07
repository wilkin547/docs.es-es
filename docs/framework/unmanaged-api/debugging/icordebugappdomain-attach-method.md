---
description: 'Más información acerca de: ICorDebugAppDomain:: Attach (método)'
title: ICorDebugAppDomain::Attach (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.Attach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::Attach
helpviewer_keywords:
- ICorDebugAppDomain::Attach method [.NET Framework debugging]
- Attach method [.NET Framework debugging]
ms.assetid: 0358b84a-4236-4c34-945b-4babff7df570
topic_type:
- apiref
ms.openlocfilehash: 94448937a735b30d0403a207992dae29920a93bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754282"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="3c17f-103">ICorDebugAppDomain::Attach (Método)</span><span class="sxs-lookup"><span data-stu-id="3c17f-103">ICorDebugAppDomain::Attach Method</span></span>

<span data-ttu-id="3c17f-104">Asocia el depurador al dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c17f-104">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c17f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c17f-105">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3c17f-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3c17f-106">Remarks</span></span>  

 <span data-ttu-id="3c17f-107">El depurador se debe asociar al dominio de aplicación para recibir eventos y habilitar la depuración del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c17f-107">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c17f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c17f-108">Requirements</span></span>  

 <span data-ttu-id="3c17f-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c17f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c17f-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c17f-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c17f-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c17f-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c17f-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c17f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
