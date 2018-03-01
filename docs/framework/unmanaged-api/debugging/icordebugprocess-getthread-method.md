---
title: "ICorDebugProcess::GetThread (Método)"
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
- ICorDebugProcess.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 996003f254c5150dfd39ca62d7cadf07282596c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="ce038-102">ICorDebugProcess::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="ce038-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="ce038-103">Obtiene el subproceso de este proceso con el identificador de subproceso de sistema de operativo (SO) especificado.</span><span class="sxs-lookup"><span data-stu-id="ce038-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce038-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce038-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce038-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce038-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="ce038-106">[in] Identificador del subproceso va a recuperar del subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="ce038-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="ce038-107">[out] Un puntero a la dirección de un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="ce038-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce038-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce038-108">Requirements</span></span>  
 <span data-ttu-id="ce038-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce038-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce038-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce038-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce038-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce038-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce038-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce038-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
