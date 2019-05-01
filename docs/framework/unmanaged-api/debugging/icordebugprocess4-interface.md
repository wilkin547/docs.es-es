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
ms.openlocfilehash: 1bdc958f2516bcd7c2eb74312fbf478e6d49535a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948813"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="4d924-102">Interfaz ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="4d924-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="4d924-103">Proporciona compatibilidad para fuera del control de ejecución del proceso.</span><span class="sxs-lookup"><span data-stu-id="4d924-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="4d924-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="4d924-104">Methods</span></span>

| <span data-ttu-id="4d924-105">Método</span><span class="sxs-lookup"><span data-stu-id="4d924-105">Method</span></span>                                                                 | <span data-ttu-id="4d924-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d924-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="4d924-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="4d924-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="4d924-108">Notifica a la canalización ICorDebug que fuera del depurador de proceso continúa la ejecución del depurado.</span><span class="sxs-lookup"><span data-stu-id="4d924-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="4d924-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d924-109">Remarks</span></span>

<span data-ttu-id="4d924-110">Esta interfaz reside en el tiempo de ejecución y no se expone a través de los encabezados o archivos de biblioteca.</span><span class="sxs-lookup"><span data-stu-id="4d924-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="4d924-111">Sin embargo, es una interfaz COM que deriva de `IUnknown` con GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` que puede obtenerse a través de los mecanismos de COM habituales.</span><span class="sxs-lookup"><span data-stu-id="4d924-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="4d924-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d924-112">Requirements</span></span>

<span data-ttu-id="4d924-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d924-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="4d924-114">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="4d924-114">**Header:** None</span></span>

<span data-ttu-id="4d924-115">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="4d924-115">**Library:** None</span></span>

<span data-ttu-id="4d924-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d924-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4d924-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d924-117">See also</span></span>

- [<span data-ttu-id="4d924-118">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="4d924-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="4d924-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="4d924-119">Debugging</span></span>](index.md)
