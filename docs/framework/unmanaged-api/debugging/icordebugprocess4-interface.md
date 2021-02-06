---
description: 'Más información acerca de: interfaz ICorDebugProcess4'
title: Interfaz ICorDebugProcess4
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4
helpviewer_keywords:
- ICorDebugProcess4 interface [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 16c7f3fbd1a79b1406fe0c19a9d922964667a2a4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650006"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="78a0f-103">Interfaz ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="78a0f-103">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="78a0f-104">Proporciona compatibilidad para el control de ejecución fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="78a0f-104">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="78a0f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="78a0f-105">Methods</span></span>

| <span data-ttu-id="78a0f-106">Método</span><span class="sxs-lookup"><span data-stu-id="78a0f-106">Method</span></span>                                                                 | <span data-ttu-id="78a0f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="78a0f-107">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="78a0f-108">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="78a0f-108">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="78a0f-109">Notifica a la canalización ICorDebug que el depurador fuera de proceso está continuando la ejecución del depurador.</span><span class="sxs-lookup"><span data-stu-id="78a0f-109">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="78a0f-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="78a0f-110">Remarks</span></span>

<span data-ttu-id="78a0f-111">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="78a0f-111">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="78a0f-112">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `E930C679-78AF-4953-8AB7-B0AABF0F9F80` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="78a0f-112">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="78a0f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78a0f-113">Requirements</span></span>

<span data-ttu-id="78a0f-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78a0f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="78a0f-115">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="78a0f-115">**Header:** None</span></span>

<span data-ttu-id="78a0f-116">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="78a0f-116">**Library:** None</span></span>

<span data-ttu-id="78a0f-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78a0f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="78a0f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="78a0f-118">See also</span></span>

- [<span data-ttu-id="78a0f-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="78a0f-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="78a0f-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="78a0f-120">Debugging</span></span>](index.md)
