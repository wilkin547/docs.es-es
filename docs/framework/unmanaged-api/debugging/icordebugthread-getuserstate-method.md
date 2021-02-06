---
description: 'Más información acerca de: ICorDebugThread:: Getuserstate ((método)'
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
ms.openlocfilehash: b63b474525534f9e934954ebe660691db90b8b67
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658872"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="140a0-103">ICorDebugThread::GetUserState (Método)</span><span class="sxs-lookup"><span data-stu-id="140a0-103">ICorDebugThread::GetUserState Method</span></span>

<span data-ttu-id="140a0-104">Obtiene el estado de usuario actual de esta ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="140a0-104">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="140a0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="140a0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="140a0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="140a0-106">Parameters</span></span>  

 `pState`  
 <span data-ttu-id="140a0-107">enuncia Un puntero a una combinación bit a bit de los valores de enumeración de CorDebugUserState (que describen el estado de usuario actual de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="140a0-107">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="140a0-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="140a0-108">Remarks</span></span>  

 <span data-ttu-id="140a0-109">El estado de usuario del subproceso es el estado del subproceso cuando lo examina el programa que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="140a0-109">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="140a0-110">Un subproceso puede tener varios bits de estado establecidos.</span><span class="sxs-lookup"><span data-stu-id="140a0-110">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="140a0-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="140a0-111">Requirements</span></span>  

 <span data-ttu-id="140a0-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="140a0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="140a0-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="140a0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="140a0-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="140a0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="140a0-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="140a0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
