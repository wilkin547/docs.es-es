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
ms.openlocfilehash: 6bf73a4be40f1fbd8e9d37477907001604e8e4a6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128821"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="92975-102">ICorDebugProcess::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="92975-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="92975-103">Obtiene el subproceso de este proceso que tiene el identificador de subproceso del sistema operativo (SO) especificado.</span><span class="sxs-lookup"><span data-stu-id="92975-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92975-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92975-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92975-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="92975-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="92975-106">de IDENTIFICADOR del subproceso del sistema operativo que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="92975-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="92975-107">enuncia Puntero a la dirección de un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="92975-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92975-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92975-108">Requirements</span></span>  
 <span data-ttu-id="92975-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92975-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92975-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92975-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92975-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92975-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92975-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92975-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
