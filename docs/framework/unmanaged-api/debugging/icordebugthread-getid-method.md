---
title: ICorDebugThread::GetID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
ms.openlocfilehash: 85cfd7ba648f21721f1a9689843eac232489cb42
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728022"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="639a9-102">ICorDebugThread::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="639a9-102">ICorDebugThread::GetID Method</span></span>

<span data-ttu-id="639a9-103">Obtiene el identificador del sistema operativo actual de la parte activa de esta ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="639a9-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="639a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="639a9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="639a9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="639a9-105">Parameters</span></span>  

 `pdwThreadId`  
 <span data-ttu-id="639a9-106">enuncia Identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="639a9-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="639a9-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="639a9-107">Remarks</span></span>  

 <span data-ttu-id="639a9-108">El identificador del sistema operativo puede cambiar durante la ejecución de un proceso y puede ser un valor diferente para distintas partes del subproceso.</span><span class="sxs-lookup"><span data-stu-id="639a9-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="639a9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="639a9-109">Requirements</span></span>  

 <span data-ttu-id="639a9-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="639a9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="639a9-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="639a9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="639a9-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="639a9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="639a9-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="639a9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
