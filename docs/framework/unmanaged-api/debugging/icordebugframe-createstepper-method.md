---
title: "ICorDebugFrame::CreateStepper (Método)"
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
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 93f6741a030e72406fb8099c6373896d14cb9332
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="47768-102">ICorDebugFrame::CreateStepper (Método)</span><span class="sxs-lookup"><span data-stu-id="47768-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="47768-103">Obtiene un motor paso a paso que permite al depurador realizar operaciones de ejecución paso a paso en relación con este ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="47768-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47768-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47768-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="47768-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47768-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="47768-106">[out] Un puntero a la dirección de un objeto ICorDebugStepper que permite al depurador realizar operaciones de ejecución paso a paso en relación con el marco actual.</span><span class="sxs-lookup"><span data-stu-id="47768-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47768-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47768-107">Remarks</span></span>  
 <span data-ttu-id="47768-108">Si el marco no está activo, el objeto de paso a paso desencadene normalmente tendrá que regrese al marco antes de que finalice el paso.</span><span class="sxs-lookup"><span data-stu-id="47768-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47768-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47768-109">Requirements</span></span>  
 <span data-ttu-id="47768-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47768-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47768-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47768-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47768-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47768-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47768-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47768-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
