---
title: "ICorDebugThread::GetID (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cab889761c204204e7eda46fde0df42f31b89fbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="fc2a2-102">ICorDebugThread::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="fc2a2-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="fc2a2-103">Obtiene el identificador de sistema operativo actual de la parte activa de esta instancia de ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="fc2a2-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc2a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc2a2-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc2a2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc2a2-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="fc2a2-106">[out] El identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="fc2a2-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc2a2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc2a2-107">Remarks</span></span>  
 <span data-ttu-id="fc2a2-108">Identificador del sistema operativo puede cambiar durante la ejecución de un proceso y puede ser un valor diferente para las distintas partes del subproceso.</span><span class="sxs-lookup"><span data-stu-id="fc2a2-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc2a2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc2a2-109">Requirements</span></span>  
 <span data-ttu-id="fc2a2-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc2a2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc2a2-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc2a2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc2a2-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc2a2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc2a2-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc2a2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
