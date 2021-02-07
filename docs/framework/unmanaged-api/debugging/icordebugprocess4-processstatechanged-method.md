---
description: 'Más información acerca de: ICorDebugProcess4::P rocessStateChanged (método)'
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
ms.openlocfilehash: 35a76b3c6dd9b37d3f06f23bc2ffea82f125a29e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746482"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="f2194-103">ICorDebugProcess4::P método rocessStateChanged</span><span class="sxs-lookup"><span data-stu-id="f2194-103">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="f2194-104">Notifica a la canalización ICorDebug que el depurador fuera de proceso está continuando la ejecución del depurador.</span><span class="sxs-lookup"><span data-stu-id="f2194-104">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="f2194-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2194-105">Syntax</span></span>

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="f2194-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2194-106">Parameters</span></span>

 `eChange`\
<span data-ttu-id="f2194-107">de Miembro de la [enumeración CorDebugStateChange](cordebugstatechange-enumeration.md) que describe un cambio en el estado de ejecución del proceso.</span><span class="sxs-lookup"><span data-stu-id="f2194-107">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2194-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f2194-108">Remarks</span></span>

<span data-ttu-id="f2194-109">El método proporcionado forma parte de la `ICorDebugProcess4` interfaz y corresponde a la cuarta ranura de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="f2194-109">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="f2194-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2194-110">Requirements</span></span>

 <span data-ttu-id="f2194-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2194-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="f2194-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="f2194-112">**Header:** None</span></span>

 <span data-ttu-id="f2194-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="f2194-113">**Library:** None</span></span>

 <span data-ttu-id="f2194-114">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2194-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f2194-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2194-115">See also</span></span>

- [<span data-ttu-id="f2194-116">Interfaz ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="f2194-116">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="f2194-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f2194-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f2194-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="f2194-118">Debugging</span></span>](index.md)
