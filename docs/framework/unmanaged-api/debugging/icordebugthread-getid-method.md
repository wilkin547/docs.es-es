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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11e21e913e4749705ba6c7f91016be21b4de1712
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769971"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="70d06-102">ICorDebugThread::GetID (Método)</span><span class="sxs-lookup"><span data-stu-id="70d06-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="70d06-103">Obtiene el identificador de sistema operativo actual de la parte activa del este ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="70d06-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70d06-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="70d06-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70d06-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="70d06-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="70d06-106">[out] El identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="70d06-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70d06-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="70d06-107">Remarks</span></span>  
 <span data-ttu-id="70d06-108">Identificador del sistema operativo puede cambiar durante la ejecución de un proceso y puede ser un valor diferente para las distintas partes del subproceso.</span><span class="sxs-lookup"><span data-stu-id="70d06-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70d06-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70d06-109">Requirements</span></span>  
 <span data-ttu-id="70d06-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70d06-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70d06-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70d06-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70d06-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70d06-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70d06-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70d06-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
