---
title: "ICorDebugThread::CreateStepper (Método)"
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
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 869b1862e479c42c1ea43c90a276e95adcd5c321
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="ae666-102">ICorDebugThread::CreateStepper (Método)</span><span class="sxs-lookup"><span data-stu-id="ae666-102">ICorDebugThread::CreateStepper Method</span></span>
<span data-ttu-id="ae666-103">Crea un objeto ICorDebugStepper que permite recorrer el marco activo de esta instancia de ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="ae666-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae666-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae666-104">Syntax</span></span>  
  
```  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae666-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae666-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="ae666-106">[out] Un puntero a la dirección de un `ICorDebugStepper` objeto que permite recorrer el fotograma activo de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="ae666-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae666-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae666-107">Remarks</span></span>  
 <span data-ttu-id="ae666-108">El marco activo puede ser código no administrado.</span><span class="sxs-lookup"><span data-stu-id="ae666-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="ae666-109">El `ICorDebugStepper` interfaz se debe usar para realizar el recorrido en Sí.</span><span class="sxs-lookup"><span data-stu-id="ae666-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae666-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae666-110">Requirements</span></span>  
 <span data-ttu-id="ae666-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae666-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae666-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae666-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae666-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae666-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae666-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae666-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
