---
description: 'Más información acerca de: ICorDebugThread:: Getdebugstate ((método)'
title: ICorDebugThread::GetDebugState (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
ms.openlocfilehash: 86534dded9b8e931fe2a7e44f1c95dc2ec7b6f0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659158"
---
# <a name="icordebugthreadgetdebugstate-method"></a><span data-ttu-id="bdb87-103">ICorDebugThread::GetDebugState (Método)</span><span class="sxs-lookup"><span data-stu-id="bdb87-103">ICorDebugThread::GetDebugState Method</span></span>

<span data-ttu-id="bdb87-104">Obtiene el estado de depuración actual de este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="bdb87-104">Gets the current debug state of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdb87-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdb87-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdb87-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bdb87-106">Parameters</span></span>  

 `pState`  
 <span data-ttu-id="bdb87-107">enuncia Un puntero a una combinación bit a bit de valores de enumeración de CorDebugThreadState (que describe el estado de depuración actual de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="bdb87-107">[out] A pointer to a bitwise combination of CorDebugThreadState enumeration values that describes the current debug state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdb87-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bdb87-108">Remarks</span></span>  

 <span data-ttu-id="bdb87-109">Si el proceso está detenido actualmente, `pState` representa el estado de depuración que existirá para este subproceso si el proceso tuviera que continuar, no el estado actual real de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="bdb87-109">If the process is currently stopped, `pState` represents the debug state that would exist for this thread if the process were to be continued, not the actual current state of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdb87-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bdb87-110">Requirements</span></span>  

 <span data-ttu-id="bdb87-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdb87-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdb87-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdb87-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdb87-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdb87-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdb87-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdb87-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
