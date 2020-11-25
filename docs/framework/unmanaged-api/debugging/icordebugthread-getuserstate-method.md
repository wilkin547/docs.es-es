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
ms.openlocfilehash: dd3936656ce1c9482b7f07a5780fcf651356b4be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727970"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="b4bc4-102">ICorDebugThread::GetUserState (Método)</span><span class="sxs-lookup"><span data-stu-id="b4bc4-102">ICorDebugThread::GetUserState Method</span></span>

<span data-ttu-id="b4bc4-103">Obtiene el estado de usuario actual de esta ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="b4bc4-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4bc4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4bc4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4bc4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4bc4-105">Parameters</span></span>  

 `pState`  
 <span data-ttu-id="b4bc4-106">enuncia Un puntero a una combinación bit a bit de los valores de enumeración de CorDebugUserState (que describen el estado de usuario actual de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="b4bc4-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4bc4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4bc4-107">Remarks</span></span>  

 <span data-ttu-id="b4bc4-108">El estado de usuario del subproceso es el estado del subproceso cuando lo examina el programa que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="b4bc4-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="b4bc4-109">Un subproceso puede tener varios bits de estado establecidos.</span><span class="sxs-lookup"><span data-stu-id="b4bc4-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4bc4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4bc4-110">Requirements</span></span>  

 <span data-ttu-id="b4bc4-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4bc4-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4bc4-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4bc4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4bc4-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4bc4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4bc4-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4bc4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
