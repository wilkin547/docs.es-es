---
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
ms.openlocfilehash: fcf725ea98fa4351e72cf592f92968ee2233ecb0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213587"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="c91fc-102">Interfaz ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="c91fc-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="c91fc-103">Proporciona compatibilidad para el control de ejecución fuera de proceso.</span><span class="sxs-lookup"><span data-stu-id="c91fc-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="c91fc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c91fc-104">Methods</span></span>

| <span data-ttu-id="c91fc-105">Método</span><span class="sxs-lookup"><span data-stu-id="c91fc-105">Method</span></span>                                                                 | <span data-ttu-id="c91fc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c91fc-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="c91fc-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="c91fc-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="c91fc-108">Notifica a la canalización ICorDebug que el depurador fuera de proceso está continuando la ejecución del depurador.</span><span class="sxs-lookup"><span data-stu-id="c91fc-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c91fc-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c91fc-109">Remarks</span></span>

<span data-ttu-id="c91fc-110">Esta interfaz reside dentro del tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c91fc-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="c91fc-111">Sin embargo, es una interfaz COM que se deriva de `IUnknown` con `E930C679-78AF-4953-8AB7-B0AABF0F9F80` el GUID que se puede obtener a través de los mecanismos com habituales.</span><span class="sxs-lookup"><span data-stu-id="c91fc-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="c91fc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c91fc-112">Requirements</span></span>

<span data-ttu-id="c91fc-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c91fc-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c91fc-114">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="c91fc-114">**Header:** None</span></span>

<span data-ttu-id="c91fc-115">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="c91fc-115">**Library:** None</span></span>

<span data-ttu-id="c91fc-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c91fc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c91fc-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c91fc-117">See also</span></span>

- [<span data-ttu-id="c91fc-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c91fc-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c91fc-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="c91fc-119">Debugging</span></span>](index.md)
