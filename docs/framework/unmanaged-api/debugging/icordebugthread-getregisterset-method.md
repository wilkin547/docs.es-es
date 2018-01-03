---
title: "ICorDebugThread::GetRegisterSet (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetRegisterSet
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3eb4acd546a2a87f7844a442110dc15343cc218
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="f7091-102">ICorDebugThread::GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="f7091-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="f7091-103">Obtiene un puntero de interfaz al conjunto de registros que está asociado a la parte activa de este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="f7091-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7091-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7091-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7091-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7091-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="f7091-106">[out] Un puntero a la dirección de un [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) establece objeto de interfaz que representa el registro para la parte activa de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="f7091-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7091-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7091-107">Requirements</span></span>  
 <span data-ttu-id="f7091-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7091-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7091-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7091-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7091-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7091-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7091-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7091-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
