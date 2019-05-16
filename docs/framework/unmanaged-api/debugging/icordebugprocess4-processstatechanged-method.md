---
title: Método ICorDebugProcess4::ProcessStateChanged
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
ms.openlocfilehash: 5e3a6714489e2051a09b5855ab9f911ef2f57450
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632282"
---
# <a name="icordebugprocess4processstatechanged-method"></a><span data-ttu-id="8f96d-102">Método ICorDebugProcess4::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="8f96d-102">ICorDebugProcess4::ProcessStateChanged Method</span></span>

<span data-ttu-id="8f96d-103">Notifica a la canalización ICorDebug que fuera del depurador de proceso continúa la ejecución del depurado.</span><span class="sxs-lookup"><span data-stu-id="8f96d-103">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f96d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f96d-104">Syntax</span></span>

```
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a><span data-ttu-id="8f96d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f96d-105">Parameters</span></span>

 `eChange`\
<span data-ttu-id="8f96d-106">[in] Un miembro de la [enumeración CorDebugStateChange](cordebugstatechange-enumeration.md) que describe un cambio de estado de ejecución del proceso.</span><span class="sxs-lookup"><span data-stu-id="8f96d-106">[in] A member of the [CorDebugStateChange enumeration](cordebugstatechange-enumeration.md) describing a change in the process's execution state.</span></span>

## <a name="remarks"></a><span data-ttu-id="8f96d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f96d-107">Remarks</span></span>

<span data-ttu-id="8f96d-108">El método proporcionado forma parte de la `ICorDebugProcess4` interfaz y corresponde a la cuarta ranura de la tabla de métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="8f96d-108">The provided method is part of the `ICorDebugProcess4` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="8f96d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f96d-109">Requirements</span></span>

 <span data-ttu-id="8f96d-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f96d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="8f96d-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="8f96d-111">**Header:** None</span></span>

 <span data-ttu-id="8f96d-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="8f96d-112">**Library:** None</span></span>
 
 <span data-ttu-id="8f96d-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f96d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8f96d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f96d-114">See also</span></span>

- [<span data-ttu-id="8f96d-115">Interfaz ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="8f96d-115">ICorDebugProcess4 Interface</span></span>](icordebugprocess4-interface.md)
- [<span data-ttu-id="8f96d-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8f96d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8f96d-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="8f96d-117">Debugging</span></span>](index.md)
