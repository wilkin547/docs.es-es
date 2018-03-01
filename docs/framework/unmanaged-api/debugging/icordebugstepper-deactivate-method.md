---
title: "ICorDebugStepper::Deactivate (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1541c6fa838115655c3ff176a0cb29f803733daa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="8850a-102">ICorDebugStepper::Deactivate (Método)</span><span class="sxs-lookup"><span data-stu-id="8850a-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="8850a-103">Hace que esta ICorDebugStepper cancelar el último comando de paso que recibió.</span><span class="sxs-lookup"><span data-stu-id="8850a-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8850a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8850a-104">Syntax</span></span>  
  
```  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8850a-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8850a-105">Remarks</span></span>  
 <span data-ttu-id="8850a-106">Puede emitir un nuevo comando de ejecución paso a paso tiempo después de que se ha cancelado el comando de paso recibido más recientemente.</span><span class="sxs-lookup"><span data-stu-id="8850a-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8850a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8850a-107">Requirements</span></span>  
 <span data-ttu-id="8850a-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8850a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8850a-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8850a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8850a-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8850a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8850a-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8850a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
