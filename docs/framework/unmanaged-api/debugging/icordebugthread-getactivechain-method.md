---
title: ICorDebugThread::GetActiveChain (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b05f5a3f29c7b72ed83c1456175f68ef9b986e3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987199"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="f7f4d-102">ICorDebugThread::GetActiveChain (Método)</span><span class="sxs-lookup"><span data-stu-id="f7f4d-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="f7f4d-103">Obtiene un puntero de interfaz a la cadena de pila activa (más reciente) en este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7f4d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7f4d-104">Syntax</span></span>  
  
```  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7f4d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7f4d-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="f7f4d-106">[out] Un puntero a la dirección de un objeto ICorDebugChain que representa la cadena de la pila.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7f4d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7f4d-107">Remarks</span></span>  
 <span data-ttu-id="f7f4d-108">El `ppChain` parámetro es null si ninguna cadena de la pila está activa actualmente.</span><span class="sxs-lookup"><span data-stu-id="f7f4d-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7f4d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7f4d-109">Requirements</span></span>  
 <span data-ttu-id="f7f4d-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7f4d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7f4d-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7f4d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7f4d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7f4d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7f4d-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7f4d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
