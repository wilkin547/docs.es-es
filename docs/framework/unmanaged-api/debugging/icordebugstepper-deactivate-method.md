---
title: "ICorDebugStepper::Deactivate (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.Deactivate
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 056d60a56c37126163361166e16da5d7949e2dbc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="3d480-102">ICorDebugStepper::Deactivate (Método)</span><span class="sxs-lookup"><span data-stu-id="3d480-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="3d480-103">Hace que esta ICorDebugStepper cancelar el último comando de paso que recibió.</span><span class="sxs-lookup"><span data-stu-id="3d480-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d480-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d480-104">Syntax</span></span>  
  
```  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3d480-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d480-105">Remarks</span></span>  
 <span data-ttu-id="3d480-106">Puede emitir un nuevo comando de ejecución paso a paso tiempo después de que se ha cancelado el comando de paso recibido más recientemente.</span><span class="sxs-lookup"><span data-stu-id="3d480-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d480-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d480-107">Requirements</span></span>  
 <span data-ttu-id="3d480-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d480-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d480-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d480-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d480-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d480-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d480-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d480-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
