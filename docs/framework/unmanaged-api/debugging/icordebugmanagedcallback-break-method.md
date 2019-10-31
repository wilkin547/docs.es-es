---
title: ICorDebugManagedCallback::Break (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
ms.openlocfilehash: efc9de050e34867c14f8e85e091e2b959c30f213
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122584"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="b3a0d-102">ICorDebugManagedCallback::Break (Método)</span><span class="sxs-lookup"><span data-stu-id="b3a0d-102">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="b3a0d-103">Notifica al depurador cuando se ejecuta una instrucción <xref:System.Reflection.Emit.OpCodes.Break> en la secuencia de código.</span><span class="sxs-lookup"><span data-stu-id="b3a0d-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="b3a0d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3a0d-104">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="b3a0d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3a0d-105">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="b3a0d-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la instrucción break.</span><span class="sxs-lookup"><span data-stu-id="b3a0d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="b3a0d-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene la instrucción break.</span><span class="sxs-lookup"><span data-stu-id="b3a0d-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="b3a0d-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3a0d-108">Requirements</span></span>

<span data-ttu-id="b3a0d-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3a0d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="b3a0d-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3a0d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="b3a0d-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3a0d-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b3a0d-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3a0d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b3a0d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3a0d-113">See also</span></span>

- [<span data-ttu-id="b3a0d-114">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b3a0d-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
