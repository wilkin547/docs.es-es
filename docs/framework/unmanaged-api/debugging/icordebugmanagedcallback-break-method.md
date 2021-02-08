---
description: 'Más información acerca de: ICorDebugManagedCallback:: Break (método)'
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
ms.openlocfilehash: 2ef273a693291685c4c3a0ce2b20ed45613e3376
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801220"
---
# <a name="icordebugmanagedcallbackbreak-method"></a><span data-ttu-id="141bf-103">ICorDebugManagedCallback::Break (Método)</span><span class="sxs-lookup"><span data-stu-id="141bf-103">ICorDebugManagedCallback::Break Method</span></span>

<span data-ttu-id="141bf-104">Notifica al depurador cuando <xref:System.Reflection.Emit.OpCodes.Break> se ejecuta una instrucción en la secuencia de código.</span><span class="sxs-lookup"><span data-stu-id="141bf-104">Notifies the debugger when a <xref:System.Reflection.Emit.OpCodes.Break> instruction in the code stream is executed.</span></span>

## <a name="syntax"></a><span data-ttu-id="141bf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="141bf-105">Syntax</span></span>

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a><span data-ttu-id="141bf-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="141bf-106">Parameters</span></span>

`pAppDomain`\
<span data-ttu-id="141bf-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la instrucción break.</span><span class="sxs-lookup"><span data-stu-id="141bf-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the break instruction.</span></span>

`thread`\
<span data-ttu-id="141bf-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene la instrucción break.</span><span class="sxs-lookup"><span data-stu-id="141bf-108">[in] A pointer to an ICorDebugThread object that represents the thread that contains the break instruction.</span></span>

## <a name="requirements"></a><span data-ttu-id="141bf-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="141bf-109">Requirements</span></span>

<span data-ttu-id="141bf-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="141bf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="141bf-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="141bf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="141bf-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="141bf-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="141bf-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="141bf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="141bf-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="141bf-114">See also</span></span>

- [<span data-ttu-id="141bf-115">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="141bf-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
