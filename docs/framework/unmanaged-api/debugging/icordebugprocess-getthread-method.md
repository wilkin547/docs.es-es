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
ms.openlocfilehash: e70204aa555ed9411d1d2cd5ad8cde7e0c53de2a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695002"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="5b406-102">ICorDebugProcess::GetThread (Método)</span><span class="sxs-lookup"><span data-stu-id="5b406-102">ICorDebugProcess::GetThread Method</span></span>

<span data-ttu-id="5b406-103">Obtiene el subproceso de este proceso que tiene el identificador de subproceso del sistema operativo (SO) especificado.</span><span class="sxs-lookup"><span data-stu-id="5b406-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b406-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b406-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b406-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5b406-105">Parameters</span></span>  

 `dwThreadId`  
 <span data-ttu-id="5b406-106">de IDENTIFICADOR del subproceso del sistema operativo que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="5b406-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="5b406-107">enuncia Puntero a la dirección de un objeto ICorDebugThread que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="5b406-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b406-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b406-108">Requirements</span></span>  

 <span data-ttu-id="5b406-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b406-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b406-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b406-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b406-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b406-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b406-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b406-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
