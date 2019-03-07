---
title: ICorDebugProcess::GetThread (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36070d5374a11daf4b7800481c86d61057989631
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470086"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="d46d6-102">ICorDebugProcess::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="d46d6-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="d46d6-103">Obtiene el subproceso de este proceso con el identificador de subproceso de sistema de operativo (SO) especificado.</span><span class="sxs-lookup"><span data-stu-id="d46d6-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d46d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d46d6-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d46d6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d46d6-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="d46d6-106">[in] Identificador del subproceso va a recuperar del subproceso el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d46d6-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="d46d6-107">[out] Un puntero a la dirección de un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="d46d6-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d46d6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d46d6-108">Requirements</span></span>  
 <span data-ttu-id="d46d6-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d46d6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d46d6-110">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d46d6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d46d6-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d46d6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d46d6-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d46d6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
