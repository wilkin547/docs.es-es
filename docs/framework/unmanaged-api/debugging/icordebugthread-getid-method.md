---
description: 'Más información acerca de: ICorDebugThread:: GetID (método)'
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
ms.openlocfilehash: d089201527da67299b64cdf074bdd331f22375a1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659093"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="0f2e1-103">ICorDebugThread::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="0f2e1-103">ICorDebugThread::GetID Method</span></span>

<span data-ttu-id="0f2e1-104">Obtiene el identificador del sistema operativo actual de la parte activa de esta ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="0f2e1-104">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f2e1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f2e1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f2e1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f2e1-106">Parameters</span></span>  

 `pdwThreadId`  
 <span data-ttu-id="0f2e1-107">enuncia Identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="0f2e1-107">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f2e1-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0f2e1-108">Remarks</span></span>  

 <span data-ttu-id="0f2e1-109">El identificador del sistema operativo puede cambiar durante la ejecución de un proceso y puede ser un valor diferente para distintas partes del subproceso.</span><span class="sxs-lookup"><span data-stu-id="0f2e1-109">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f2e1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f2e1-110">Requirements</span></span>  

 <span data-ttu-id="0f2e1-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f2e1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f2e1-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f2e1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f2e1-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f2e1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f2e1-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f2e1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
