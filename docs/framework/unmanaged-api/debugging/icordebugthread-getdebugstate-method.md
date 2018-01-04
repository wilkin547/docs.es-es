---
title: "ICorDebugThread::GetDebugState (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetDebugState
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b9d310cdc088e4b2fc9c6850accc3576a6147ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="de27b-102">ICorDebugThread::GetDebugState (Método)</span><span class="sxs-lookup"><span data-stu-id="de27b-102">ICorDebugThread::GetDebugState Method</span></span>
<span data-ttu-id="de27b-103">Obtiene el estado de depuración actual de este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="de27b-103">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de27b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de27b-104">Syntax</span></span>  
  
```  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de27b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de27b-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="de27b-106">[out] Un puntero a una combinación bit a bit de valores de enumeración CorDebugThreadState que describe el estado de depuración actual de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="de27b-106">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de27b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de27b-107">Remarks</span></span>  
 <span data-ttu-id="de27b-108">Si actualmente se detiene el proceso, `pState` representa el estado de depuración que existiría para este subproceso si el proceso puede continuar, no el estado actual real de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="de27b-108">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de27b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de27b-109">Requirements</span></span>  
 <span data-ttu-id="de27b-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de27b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de27b-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de27b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de27b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de27b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de27b-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de27b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
