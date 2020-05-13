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
ms.openlocfilehash: f70a88df00d15729a6bde06b49417b6439f7c0ec
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212482"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="7d22e-102">ICorDebugManagedCallback::Break (Método)</span><span class="sxs-lookup"><span data-stu-id="7d22e-102">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="7d22e-103">Notifica al depurador cuando <xref:System.Reflection.Emit.OpCodes.Break> se ejecuta una instrucción en la secuencia de código.</span><span class="sxs-lookup"><span data-stu-id="7d22e-103">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d22e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d22e-104">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="7d22e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d22e-105">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="7d22e-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la instrucción break.</span><span class="sxs-lookup"><span data-stu-id="7d22e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="7d22e-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene la instrucción break.</span><span class="sxs-lookup"><span data-stu-id="7d22e-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d22e-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d22e-108">Requirements</span></span>

<span data-ttu-id="7d22e-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d22e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="7d22e-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d22e-110">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="7d22e-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d22e-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="7d22e-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d22e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7d22e-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d22e-113">See also</span></span>

- [<span data-ttu-id="7d22e-114">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d22e-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
