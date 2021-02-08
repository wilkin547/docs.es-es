---
description: 'Más información sobre: ICorDebugThread4:: Getcurrentcustomdebuggernotification ((método)'
title: ICorDebugThread4::GetCurrentCustomDebuggerNotification (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
ms.openlocfilehash: 20d9449e98b9ab91dbdec84ba026e91514d5b3cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800947"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="7e099-103">ICorDebugThread4::GetCurrentCustomDebuggerNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="7e099-103">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="7e099-104">Obtiene el objeto [ICorDebugManagedCallback3 (:: customnotification (](icordebugmanagedcallback3-customnotification-method.md) actual en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="7e099-104">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="7e099-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e099-105">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="7e099-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e099-106">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="7e099-107">enuncia Puntero al `ICorDebugManagedCallback3::CustomNotification` objeto actual en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="7e099-107">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e099-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7e099-108">Remarks</span></span>

<span data-ttu-id="7e099-109">El valor de `ppNotificationObject` es NULL si no se llama al método desde una `ICorDebugManagedCallback3::CustomNotification` devolución de llamada o si no existe ningún objeto de notificación actual.</span><span class="sxs-lookup"><span data-stu-id="7e099-109">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="7e099-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e099-110">Requirements</span></span>

<span data-ttu-id="7e099-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e099-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="7e099-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e099-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="7e099-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e099-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="7e099-114">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e099-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7e099-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e099-115">See also</span></span>

- [<span data-ttu-id="7e099-116">ICorDebugThread4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e099-116">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="7e099-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7e099-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7e099-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="7e099-118">Debugging</span></span>](index.md)
