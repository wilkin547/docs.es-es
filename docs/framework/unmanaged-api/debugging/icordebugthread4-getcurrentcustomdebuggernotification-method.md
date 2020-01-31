---
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
ms.openlocfilehash: a8a377074ca1005ad8089dfd8e2a6a464bb86f60
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791367"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="0153d-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification (Método)</span><span class="sxs-lookup"><span data-stu-id="0153d-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="0153d-103">Obtiene el objeto [ICorDebugManagedCallback3 (:: customnotification (](icordebugmanagedcallback3-customnotification-method.md) actual en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="0153d-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="0153d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0153d-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="0153d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0153d-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="0153d-106">enuncia Puntero al objeto `ICorDebugManagedCallback3::CustomNotification` actual en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="0153d-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="0153d-107">Notas</span><span class="sxs-lookup"><span data-stu-id="0153d-107">Remarks</span></span>

<span data-ttu-id="0153d-108">El valor de `ppNotificationObject` es NULL si no se llama al método desde dentro de una devolución de llamada de `ICorDebugManagedCallback3::CustomNotification` o si no existe ningún objeto de notificación actual.</span><span class="sxs-lookup"><span data-stu-id="0153d-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="0153d-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0153d-109">Requirements</span></span>

<span data-ttu-id="0153d-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0153d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="0153d-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0153d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="0153d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0153d-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0153d-113">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0153d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0153d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0153d-114">See also</span></span>

- [<span data-ttu-id="0153d-115">ICorDebugThread4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0153d-115">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="0153d-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0153d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0153d-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="0153d-117">Debugging</span></span>](index.md)
