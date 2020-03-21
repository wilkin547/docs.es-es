---
title: ICorDebugProcess4::ProcessStateChanged Método
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: a6f36f5b86b4fa58ce2a4ef4aa23d527f797a5a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178628"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="943a4-102">ICorDebugProcess4::ProcessStateChanged Método</span><span class="sxs-lookup"><span data-stu-id="943a4-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="943a4-103">Notifica a la canalización ICorDebug que el depurador fuera de proceso continúa la ejecución del depurador.</span><span class="sxs-lookup"><span data-stu-id="943a4-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="943a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="943a4-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="943a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="943a4-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="943a4-106">[en] Miembro de la [corDebugStateChange enumeración](cordebugstatechange-enumeration.md) que describe un cambio en el estado de ejecución del proceso.</span><span class="sxs-lookup"><span data-stu-id="943a4-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="943a4-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="943a4-107">Remarks</span></span>

<span data-ttu-id="943a4-108">El método proporcionado forma `ICorDebugProcess4` parte de la interfaz y corresponde a la cuarta ranura de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="943a4-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="943a4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="943a4-109">Requirements</span></span>

 <span data-ttu-id="943a4-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="943a4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="943a4-111">**Encabezado:** Ninguno</span><span class="sxs-lookup"><span data-stu-id="943a4-111">**Header:** None</span></span>

 <span data-ttu-id="943a4-112">**Biblioteca:** Ninguno</span><span class="sxs-lookup"><span data-stu-id="943a4-112">**Library:** None</span></span>

 <span data-ttu-id="943a4-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="943a4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="943a4-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="943a4-114">See also</span></span>

- [<span data-ttu-id="943a4-115">Interfaz ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="943a4-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="943a4-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="943a4-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="943a4-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="943a4-117">Debugging</span></span>](index.md)
