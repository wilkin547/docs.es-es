---
title: "ICorDebugThread::GetHandle (Método)"
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
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c7a932d04fef438e19176af565c92e0673339e02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="03f0d-102">ICorDebugThread::GetHandle (Método)</span><span class="sxs-lookup"><span data-stu-id="03f0d-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="03f0d-103">Obtiene el identificador actual para la parte activa de esta instancia de ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="03f0d-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03f0d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03f0d-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="03f0d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03f0d-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="03f0d-106">[out] Un puntero a HTHREAD que es el identificador de la parte activa de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="03f0d-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03f0d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03f0d-107">Remarks</span></span>  
 <span data-ttu-id="03f0d-108">El identificador puede cambiar mientras se ejecuta el proceso y puede ser diferente para las distintas partes del subproceso.</span><span class="sxs-lookup"><span data-stu-id="03f0d-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="03f0d-109">Este identificador es propiedad de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="03f0d-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="03f0d-110">El depurador debería duplicarlo antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="03f0d-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03f0d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03f0d-111">Requirements</span></span>  
 <span data-ttu-id="03f0d-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03f0d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03f0d-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03f0d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03f0d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03f0d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03f0d-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03f0d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
