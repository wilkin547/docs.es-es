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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7d3325c8aee44849ff1fb7a6cc06a0ed7c2c6f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769103"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="0e3a2-102">ICorDebugThread::GetUserState (Método)</span><span class="sxs-lookup"><span data-stu-id="0e3a2-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="0e3a2-103">Obtiene el estado de usuario actual de esta instancia de ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="0e3a2-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e3a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e3a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e3a2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e3a2-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="0e3a2-106">[out] Un puntero a una combinación bit a bit de valores de enumeración CorDebugUserState que describen el estado de usuario actual de este subproceso.</span><span class="sxs-lookup"><span data-stu-id="0e3a2-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e3a2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e3a2-107">Remarks</span></span>  
 <span data-ttu-id="0e3a2-108">El estado de usuario del subproceso es el estado del subproceso cuando lo examina el programa que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="0e3a2-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="0e3a2-109">Un subproceso puede tener varios bits de estado establecida.</span><span class="sxs-lookup"><span data-stu-id="0e3a2-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e3a2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e3a2-110">Requirements</span></span>  
 <span data-ttu-id="0e3a2-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e3a2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e3a2-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e3a2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e3a2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e3a2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e3a2-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e3a2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
