---
title: ICorDebugProcess4::P método rocessStateChanged
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
ms.openlocfilehash: 910c411d2c63ce2c6cf262e28e08546657dc2a4c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213574"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="5bbb7-102">ICorDebugProcess4::P método rocessStateChanged</span><span class="sxs-lookup"><span data-stu-id="5bbb7-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="5bbb7-103">Notifica a la canalización ICorDebug que el depurador fuera de proceso está continuando la ejecución del depurador.</span><span class="sxs-lookup"><span data-stu-id="5bbb7-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="5bbb7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5bbb7-104">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="5bbb7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5bbb7-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="5bbb7-106">de Miembro de la [enumeración CorDebugStateChange](cordebugstatechange-enumeration.md) que describe un cambio en el estado de ejecución del proceso.</span><span class="sxs-lookup"><span data-stu-id="5bbb7-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="5bbb7-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5bbb7-107">Remarks</span></span>

<span data-ttu-id="5bbb7-108">El método proporcionado forma parte de la `ICorDebugProcess4` interfaz y corresponde a la cuarta ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="5bbb7-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5bbb7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5bbb7-109">Requirements</span></span>

 <span data-ttu-id="5bbb7-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bbb7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="5bbb7-111">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="5bbb7-111">**Header:** None</span></span>

 <span data-ttu-id="5bbb7-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="5bbb7-112">**Library:** None</span></span>

 <span data-ttu-id="5bbb7-113">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bbb7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5bbb7-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5bbb7-114">See also</span></span>

- [<span data-ttu-id="5bbb7-115">Interfaz ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="5bbb7-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="5bbb7-116">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5bbb7-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5bbb7-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="5bbb7-117">Debugging</span></span>](index.md)
