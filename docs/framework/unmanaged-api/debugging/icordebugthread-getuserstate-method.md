---
title: ICorDebugThread::GetUserState (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type:
- apiref
ms.openlocfilehash: d1ff3427feb5dc8395bbb2fda78e3e93e1a1a8f0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378856"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="00ee2-102">ICorDebugThread::GetUserState (Método)</span><span class="sxs-lookup"><span data-stu-id="00ee2-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="00ee2-103">Obtiene el estado de usuario actual de esta ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="00ee2-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00ee2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00ee2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00ee2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="00ee2-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="00ee2-106">enuncia Un puntero a una combinación bit a bit de los valores de enumeración de CorDebugUserState (que describen el estado de usuario actual de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="00ee2-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00ee2-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="00ee2-107">Remarks</span></span>  
 <span data-ttu-id="00ee2-108">El estado de usuario del subproceso es el estado del subproceso cuando lo examina el programa que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="00ee2-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="00ee2-109">Un subproceso puede tener varios bits de estado establecidos.</span><span class="sxs-lookup"><span data-stu-id="00ee2-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00ee2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00ee2-110">Requirements</span></span>  
 <span data-ttu-id="00ee2-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00ee2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00ee2-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00ee2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00ee2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00ee2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00ee2-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00ee2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
