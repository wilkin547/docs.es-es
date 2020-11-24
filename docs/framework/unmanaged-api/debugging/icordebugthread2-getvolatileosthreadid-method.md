---
title: ICorDebugThread2::GetVolatileOSThreadID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetVolatileOSThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetVolatileOSThreadID
helpviewer_keywords:
- GetVolatileOSThreadID method [.NET Framework debugging]
- ICorDebugThread2::GetVolatileOSThreadID method [.NET Framework debugging]
ms.assetid: f0922545-c2cf-40c8-9ef6-ca033563e682
topic_type:
- apiref
ms.openlocfilehash: 177c6057432912c402c379c70a22506d9bde261e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678615"
---
# <a name="icordebugthread2getvolatileosthreadid-method"></a><span data-ttu-id="8b405-102">ICorDebugThread2::GetVolatileOSThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="8b405-102">ICorDebugThread2::GetVolatileOSThreadID Method</span></span>

<span data-ttu-id="8b405-103">Obtiene el identificador del subproceso del sistema operativo para este ICorDebugThread2.</span><span class="sxs-lookup"><span data-stu-id="8b405-103">Gets the operating system thread identifier for this ICorDebugThread2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b405-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b405-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVolatileOSThreadID (  
    [out] DWORD    *pdwTid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b405-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b405-105">Parameters</span></span>  

 `pdwTid`  
 <span data-ttu-id="8b405-106">enuncia Identificador del subproceso del sistema operativo para este subproceso.</span><span class="sxs-lookup"><span data-stu-id="8b405-106">[out] The operating system thread identifier for this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b405-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b405-107">Requirements</span></span>  

 <span data-ttu-id="8b405-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b405-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b405-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b405-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b405-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b405-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b405-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b405-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
